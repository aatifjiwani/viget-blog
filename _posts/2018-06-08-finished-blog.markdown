---
layout: post
title: Started A New Project!
date:   2018-06-08
category: first
comments: true
---

Today I finished my blog in its entirety (if that's spelled correctly). I've added a photo of myself to the about page to add some more pizzaz. 

Now, I have a new project. Yay!! I get to build a recreation of <a href="http://news.ycombinator.com"> Hacker News</a> which is pretty sweet. I started to work on deploying the app and getting the preliminary design of the home page finished. 

Whilst doing so, I learnt a couple things. First, Heroku is a PAIN IN THE ASS!!!!!! Just trying to deploy the app on Heroku took like an hour or so because I was getting so many errors. There is just so many things you have to configure before your app is working successfully on Heroku. 

Next, I learnt more things about Ruby on Rails. I figured out (with the help of Eli) that each HTML page is actually a template that is passed into the application.html.erb file. I also learned that in the application controller, you can write:

{%  highlight ruby %}
def some_method
    ...
end

helper_method :some_method
{% endhighlight %}

and you can use the given method inside your view. That's so cool!!

Tomorrow, I am going to work on creating a model for the posts and allowing visitors to be able to create and view a list of the most recent posts. 

See ya tomorrow!!