---
layout: post
title:  You Can Vote!
date:   2018-06-21
category: third
comments: true
---

Ahh, today was a much better day. I didn't struggle as much as I did yesterday but I still was challenged as I was expecting. 
Today, I worked on implementing the voting scheme on just the articles. In order to do that, I had to learn about ajax and how you can assign
background tasks, essentially, within your app. At first it was pretty hard because I was just trying to learn from the internet. But turns out, I didn't have the right resources. All the things I was looking at rendered a javascript file after a remote link is clicked but that javascript never did anything. 
Nothing was working!!!!

So I talked to Eli and he told me another way to do it. Instead of doing:

{% highlight ruby %}
#controller.rb
...
respond_to do |format|
  format.js 
end
{% endhighlight %}

I did:

{% highlight ruby%}
#controller.rb
...
render json: {key: value}
{% endhighlight %}

And this would send the browser a response with a hash. In order to retrieve that response, you need to bind the link to an ajax callback method. For getting the response after successful execution, you should run:

{% highlight javascript %}
$('#button').bind('ajax:success', function(evt, data, status, xhr) {
    //the response is in the 'evt' parameter
    response = evt['detail']
    //do stuff with the response. 
}
{% endhighlight %}

Also, Patrick gave me guidance to how I should create a vote model to keep track of all the votes any user has made on any article. This would help ensure that no user can vote the same value multiple times. I still have yet to implement a feature where the user can take back their vote if they accidentally clicked something. But that's fore later, let's just get the core functionality down. 