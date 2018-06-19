---
layout: post
title:  I'm Exhausted
date:   2018-06-19
category: third
comments: true
---

Holy moly what an exhausting day I just had. 

First, I started working on a blog for Viget that explained how Rails 5.2 stored secret credentials in a different way than previous versions. I sent the finished blog to be looked over by 3 devs and a writer to look over and there were a lot of comments haha. Not that I don't mind but it just reinforces that thankfully I am not a writer myself. I've always been pretty bad at writing good sentence structures and that stuff but hurray, I'm a software developer so it doesn't matter a whole lot. 

Next, I started working on implementing comments on articles. Eli's Haxxor News specs said that comments could be nested within eachother and there really is not a limit to how deep the layers go. This was really confusing at first and I knew right off the bat that I couldn't simply use 'has_many' and 'belongs_to' because a comment could belong to either a post or an article, you won't know which. So today, I learned about polymorphism and that concept is how you attack the idea that comments could belong to other comments or an article. It's actually pretty sweet that you could do that and I'm kinda interested in the other kind of manipulations you can do with models. 

After I figured out polymorphism, I actually had to embed the functionality within my html code. Now that was a real pain in the booty. As of this moment, it took me almost 3 hours just to design the page that allowed adding comments. A part of the three hours were spent trying to figure out why CKEditor was being stupid and wasn't creating a formatting toolbar on my textareas. While trying to figure out a solution, I found out that CKEdtior, the library that creates the formatting toolbar, actually has a rails gem that I could use. So instead of using a script to replace the textareas, I could just use:

{% highlight ruby %}
<%= form.cktext_area :body, class: 'blah', ckeditor: {ui_color: #123456,...}
{% endhighlight %}

where I could configure the textarea box using a hash of options, as kinda highlighted above. Although this seems awesome, this took me like fricken 2 hours to figure out because there's just so much that you need to do in order to get the rails gem to actually work. 

Then, it took me another hour or so to design the comments area and that was kinda also a pain in the booty because I wanted to go a little farther and have cool user interaction where you could choose to reply to a comment and a textarea will show up. The javascript was pretty simple but just organizing everything was pretty exhausting. 

Tomorrow, I'm going to continue to work on the comments feature. I still have to write tests to make sure that everything works the way it is meant to be without going in and doing QA tests. 