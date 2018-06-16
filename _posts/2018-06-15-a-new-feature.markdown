---
layout: post
title:  A New Feature
date:   2018-06-15
category: second
comments: true
---

As the second week of my Viget internship comes to a close, I've been able to successfully add a pretty sweet feature that seems mediocre to other people: resetting a password. 

In this process, I learned that it's important to stay away from creating custom routes and instead create a separate controller to handle CRUD actions, even if it doesn't have a model associated with it. I had to create a PasswordReset controller which had the new, create, edit, and update actions to handle a user wanting to reset their password. 

Also, Rails has a nifty thing that allows you to regenerate password tokens so someone doesn't purposely change someone's password by guessing the proper token. Simply make sure that you add:

{% highlight ruby %}
has_secure_token :<whatever-the-column-is-called>
{% endhighlight %}

into the proper model. 

Also, I learned how to properly configure Active Mailer. There's actually a separate kinda controller that handle's all the mailing functions. Also, for your and my reference, again, this is how a sample config should look if you're using gmail to send your email. 

{% highlight ruby %}

config.action_mailer.raise_delivery_errors = true
config.action_mailer.perform_deliveries = true
config.action_mailer.delivery_method = :smtp
# SMTP settings for gmail
config.action_mailer.smtp_settings = {
:address              => "smtp.gmail.com",
:port                 => 587,
:user_name            => "nflkiddo.productions@gmail.com",
<<<<<<< HEAD
:password             => Rails.application.credentials.dig(:mail_pass),
=======
:password             => "xqtuktmwhlqjejlw",
>>>>>>> 84aeea85d82ee79c585508b76ffe20d96f81e074
:authentication       => "plain",
:enable_starttls_auto => true
}

config.action_mailer.perform_caching = false

config.action_mailer.default_url_options = { host: "localhost:3000" }

{% endhighlight %}

My password isn't actually that jumbled mess but instead an app password. If you want to hack into my email, by all means go ahead. I haven't used that email in such a long time and only still exists as kinda a burner email where bots or people can send unwanted emails there. 

Otherwise, that's it for today! I've successfully written feature specs for resetting a password and it all passes! Ahhhh that's relieving. 
