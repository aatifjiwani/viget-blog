---
layout: post
title:  Mobile Dev Time
date:   2018-07-09
category: sixth
comments: true
---

Today it starts! I am using Lets Build That App on YouTube to help me get jumpstarted on iOS development. As I am going through these lessons, slowly but surely, I've noticed a few things. One is that Swift is a seamless but complicated language. There are so many components to it and so much to keep track of that it can be a little much sometimes. However, Swift looks really cool and XCode is pretty nice so I'm not complaining a whole lot. Next, I've learned that in order to do good mobile dev for iOS, you need to know a LOT of methods. The tutorial I am going through now doesn't use the GUI to outline the UI but instead hardcodes everything, including the constraints. In order to do so, there are so many fricken methods and some of those methods have enormous names. Like the method name itself is like 30 characters long and I'm thinking to myself, "How the heck am I supposed to remember that...?"

I did come across a problem that I still haven't fixed though. Apparently, making API requests and getting the response in a JSON format is more complicated than it seems. I can't follow the tutorial closely because the dude is using Swift 3 while I am using Swift 4. The two versions vary mostly in that the method names are different and there are a lot of deprecated things. So, I've encountered a problem where I get the following error:

{% highlight ruby %}
Cannot subscript a value of type 'Data' with a key of type.
{% endhighlight %}

I get this error because apparently the method `setValuesWithKeys(dict: NSDictionary)` can't read the JSON response properly and can't bind the matching values with the class attributes. This is pissing me off because I can't use the solution the YouTube video has because it is using Swift 3 and not 4. So now, I have to go ahead and find a solution online which I will do tomorrow. 

In terms of the group project, Devise is confusing. As a group, we've decided the sign in/up page will be a modal that pops up on the current page and Devise wasn't made for that type of manipulation by default. So it took a lot of digging around the gem file to figure out how I could redirect the POST request to an overriden method that signs the user in or creates a new one and returns some data to update specific elements. I got it now but it sure was confusing because of all the methods that Devise uses in order to authenticate or create a new user. 

That's all for today, see ya tomorrow. 