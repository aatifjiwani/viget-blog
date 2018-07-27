---
layout: post
title:  More Voting and iOS
date:   2018-07-26
category: eighth
comments: true
---

First off, sorry I haven't made a blog update for the past two days. Tuesday I was pretty swamped and the same goes for Wednesday since I had the Boulder TTT (which, by the way, was awesome!!!!). Today, Peyton and I grinded on the web app, specifically on the voting feature. We both were trying to figure out how to properly display the percentage of votes. Not only when a user clicks on the poll for the first time, but also whether or not if the user has already voted. We needed to account for all these possibilities otherwise the user would be confused as to whether or not they have already voted on the poll or not. 
One thing I learned while helping Peyton out is that when you have the CSS: `last-child`, `first-child`, or `nth-last-child(x)`, the HTML will think any type of element within the parent is a child. So the `last-child` etc. selectors can select a `<script>` tag even though it's not a real element that can be necessarily styled. So we had to come up with a kinda clever or hacky way to be able to account for that issue. We got that fixed though which is really good!

Next, I worked on the iOS app. Specifically on making API calls so I can create or login a user. At first, I was having a lot of troubles because the parameters weren't parsing properly. Instead of being `{ "user": {"username":...}, ....}` like I want it, iOS for some reason was putting the expected hash inside of another empty hash like `\{\{ "user": {"username":...}, ....}}`. Because of that, my API wasn't able to read the parameters like I wanted it to. So then I tried looking it up and as it turns out, I needed to add the line: `request.setValue("application/json; charset=utf-8", forHTTPHeaderField: "Content-Type")` where `request` is a `NSMutableURLRequest` object. When I got this issue figured out, I was able to easily complete user login and user signup. 

This is pretty much all I did today! See ya tomorrow!