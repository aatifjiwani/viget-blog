---
layout: post
title:  I Found a Cool New Thing
date:   2018-06-14
category: second
comments: true
---

Heyo, today was pretty productive. I was able to figure out how to link users to posts and make that relational functionality work. Now, my app allows visitors to sign up, login and create a post. Also, I've added functionality that prevents visitors from creating posts and prevents users from deleting posts that are not there. 

Also, I changed the way my Active Storage credentials are stored. Instead of having them stored in a .json file in another folder, Rails 5.2 has a new, unique way to do it. Unlike Rails 5.1 and below, you had to store your credentials in a file called secret.yml. Now, Rails secrets is deprecated in 5.2 and instead, credentials are stored in an encrypted file called credentials.yml.enc. 

I am going to post a Viget blog all about this but for your and my reference, this is how it goes. To start fresh, delete the credentials.yml.enc and master.key file in your config/ folder. Then, in a command line interface, write

{% highlight ruby %}
EDITOR='subl --wait' bin/rails credentials:edit
{% endhighlight %}

The reason there we are setting 'EDITOR' to a specific text editor is because when you run the credentials:edit command, Rails opens up the decrypted credentials file in the specified text editor. This way, you can quickly add/edit/delete any credentials, save, and quit the editor and Rails will automatically re-encrypt the credentials file. It's actually pretty sweet. 

Also, DO NOT remove master.key. Rails automatically adds this file in .gitignore so it isn't going to be pushed to a repo but this file contains the decryption key for your credentials. So whatever you do, don't lose it. 

If you're deploying your app via Heroku, you can add a config variable named RAILS_MASTER_KEY and set it equal to the decryption key. 

And that's it for today!