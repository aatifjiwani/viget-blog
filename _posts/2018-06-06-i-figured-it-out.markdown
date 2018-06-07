---
layout: post
title: I figured it out.
date:   2018-06-06
category: first
comments: true
---

Well, this is my third day at Viget and everything is going pretty well. Today I had a meeting at 8:30 AM for the Intro to Business Dev and that sucked. Not the content or the people in the meeting, just the fact that I had to pull myself out of bed at 6:00 AM to get to the meeting on time. I don't really like waking up early because I'm a night owl and not a morning riser but sometimes you gotta do what's expected of you. It's all good. 

After playing around with Jekyll for a little while, I finally have the entire framework down. I know how to override the default layouts given by Jekyll and I figured out how the templating works. Jekyll uses Liquid templating which sounds dumb and horrible and the mathematical operations are absolutely wack. Instead of writing 


{% highlight ruby %}
12 % 7 #5
{% endhighlight %}

you have to write

{% highlight ruby %}
12 | modulo:7 #5
{% endhighlight %}

Isn't that dumb? 

Welp, that's it for this post. Cya tomorrow. 

