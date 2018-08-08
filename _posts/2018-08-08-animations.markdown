---
layout: post
title:  Animations!
date:   2018-08-08
category: tenth
comments: true
---

Today was a pretty normal day. Not many meetings and just time to work on the iOS app. Yesterday, I left off in the middle of creating the popular/recent tab. In order to animate it, I had to figure out how the heck I can change the position, corner radius, and the border color all in one shot. After doing some research, I learned about `CABasicAnimation`s. "CA" stands for Core Animations and this class is awesome. All you have to do is:

{% highlight c %}
let animation = CABasicAnimation(keyPath: "borderColor")
animation.fromValue = UIColor.blue
animation.toValue = UIColor.red
animation.duration = 1
animation.repeat = 1

view.layer.add(animation, forKey: "borderColor")
{% endhighlight %}

The line where you add the animation is actually when the animation executes. That's pretty cool!
Also, I was working on the loading poll cell because I don't want the entire Poll View to be blank while the app is gathering data. I wanted to mimic the Facebook Post loading design and how it shimmers. After doing some more research, I found out that the animation is done by repeatedly moving an angled gradient across the view. That's such a simple thing to do to produce such a cool animation. 

After implementing that, it was time to start writing Unit Tests. Unit Tests for iOS are pretty confusing and the structure and syntax are kinda weird. Prayash gave me some resources on how to write Unit tests and at first, I was pretty confused. To be honest, I'm still a little confused because I haven't really written verbose Unit tests. All that I can test right now are my models (Poll, User, Comment) because my app is pretty much all API based. I don't get anything from a stored database and I don't have any hard data. So really, the trustworthiness of my app comes down to UITests which, at first glance, looks horribly confusing and I'm going to need a lot of help with that. 

Hopefully I'll learn how to write basic UI tests before I leave in a couple days. 

Tomorrow, it's all voting time. I have a crap ton of meetings but hopefully I can finish making the Voting API and get started on implementing the feature within the app. Cya!