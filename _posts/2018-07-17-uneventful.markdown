---
layout: post
title:  Wow I'm Dumb
date:   2018-07-17
category: seventh
comments: true
---

Today was pretty uneventful. There wasn't enough FED stuff done for me to go in and do my backend stuff. So today all I did was iOS development. YAY!!!!!!!! Except I've been doing the same tutorial for like a week and a half now and honestly I'm kinda getting bored by listening to that guy just ramble on and me trying to follow along.

There wasn't much that I learned either besides what an `inputAccessoryView` is and how to build it.

However, I did get caught on one thing. Last week, I was struggling because for some reason, the tap gestures on my images wouldn't work. I don't know why they didn't work but for some reason they just didn't. Today, I came across the same gosh darn problem. I tried all the ways to fix my problem by refactoring the code, moving definitions elsewhere, etc. It just wasn't working. So, I decided to give up and finally create an account on Stack Overflow and ask the question. Here is the link if you want it. <a href="https://stackoverflow.com/questions/51391053/uiimageview-tap-gesture-not-recognizing-user-interaction-is-enabled">Click here</a>

Surprisingly, somebody answered within like 5 minutes and solved my problem. And the solution really made me look stupid. Instead of setting the `target` of the gesture to `self` like it's supposed to be, I accidentally set it to `nil`. What kinda ticks me off the most is how I never caught that error. I was literally staring at my code for like 10 minutes and still didn't realize it until I used Stack Overflow. 

Well that's it today. Tomorrow imma work on the group project more. 