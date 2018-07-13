---
layout: post
title:  Today Was Difficult
date:   2018-07-12
category: sixth
comments: true
---

Wow what a day! I had two things I needed to do. One was be able to handle user sessions with the new design because the way Devise does it won't satisfy the specifications. Devise has it so that when the user makes a POST request, the page refreshes and any error that come up appear on the page after reload. However, we can't reload the page because the modal will dissapear and the user will be confused. In order to do this, I had to override the `Registrations#Create` and `Sessions#Create` methods so that they return a JSON response to the browser. Then, the forms have to make an AJAX POST request to the backend and yeah you could probably take it from there. However, figuring out how to override the `Sessions#Create` method was confusing as heck. Devise uses Warden to authenticate their users and trying to figure out where the code flow goes was hard. After a little while, I figured out that invalid credentials returns an HTTP status error and I figured I could check if there was an error when making a request in order to display the error message to the user. This took 3 hours to figure out and boy was it a doozy. 

Next, I continued to work on the chat app for iOS using Firebase and that caused a lot of errors. But I also learned a couple new things. One, I learned that API calls are asynchronous methods and are made on a background thread. I didn't realize this before and I got super frustrated. In order to solve this problem, I learned more about completion handlers and now my code is fixed! There was one part though that was causing a lot of errors and it was where I wanted to retrieve images from the Firebase storage. As I was running my code, I would always get a `EXC_BAD_ACCESS` error or whatever and I really didn't understand why. So instead of using what Firebase says to retrieve images, I just used a `URLSession` in order to get the data from the URL that was given. 

Well that's all for today so see ya.