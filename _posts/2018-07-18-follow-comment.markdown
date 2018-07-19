---
layout: post
title:  Follows and Comments
date:   2018-07-18
category: seventh
comments: true
---

Today was pretty cool! I learned a couple new things while working on the group project!
First, I started to work on the comments feature and I'll admit, it was pretty difficult at first. What happened was that Peyton didn't have a form on his frontend template so I had to go in and add one. Then, I tried submitting the form with AJAX and for some reason it just was not working. I was using Javascript to submit the form and I had `remote: true` set and the page was still refreshing. So then I looked up why and I saw that because I'm submitting the form with Javascript, the app isn't sending an AJAX request to the backend. In order to do so, I needed to add some more code:

{% highlight javascript %}
$('#form').submit(function() {
    $.ajax({
        type: //POST, PUT, DELETE, etc,
        url: $(this).attr('action'),
        data: $(this).serialize()
    }).success(function(json){
        // do stuff
    }).error(function(json){
        //do more stuff
    });
    return false;
});
{% endhighlight %}

This script allows you to send an AJAX request to the backend!!
Then, after I finished the comments, I started to work on Follows. The one thing that I learned while working on that is that you can put multiple parameters into a path in order to match the exact route. That probably just made no sense so let me show you. Say you have a route `/articles/:article_id/follows/:id`. You can specify an exact route with the exact IDs using `article_follows_path(@article, @follow)`. This method constructs the entire route for you which is sweet!! After I figured that out, completing the feature wasn't very hard. 

Well, tomorrow I'm probably going to add Follow specs and after that, we'll see what I can work on.