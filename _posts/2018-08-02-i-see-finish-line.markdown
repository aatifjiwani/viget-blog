---
layout: post
title:  I See The Finish Line
date:   2018-08-02
category: ninth
comments: true
---

We're almost there!!! This is the last day we get to work on the intern group project before we present it in front of the entire company during FLF. There isn't much to blog about besides the little tickets I worked on yesterday. 

One error that popped up was that AWS wasn't connecting and it was like `cannot verify the request signature. please check your key and id`. And I'm just super confused because there's no way I edited the credentials and this error hasn't been happening from the beginning because I've uploaded files before. So Pat and I went on a journey into AWS to figure this whole thing out. When we looked in the bucket, there was NOTHING THERE. It's like someone went in, deleted everything, and revoked my access. But I don't think anyone would do such a thing so it was pretty weird. However, Pat and I created a new AWS user for the organization and I got a new app key and access key. This did resolve some stuff because I was able to upload files but for some reason, there was a glitch and the images were not loading. So then, I talked to David B. and he helped me realize a silly mistake. Apparently, the `<style>` tags for the images were inside the `erb` conditional and that screwed everything up. Thankfully, that was an easy fix. 

The next major thing I worked on was that Safari didn't want to submit a poll if the file field didn't have a file attached. This so weird and honestly really dumb because everything worked fine on other browsers. So I decided to search it up and thankfully a lot of people had problems where Safari wasn't sending an AJAX request if the file input fields didn't have something attached to it. The solution was pretty easy to implement because someone out there created a script that allowed Safari to submit the form without files attached. THe solution, the script itself, is confusing and I don't think I will ever understand what is going on. 

Tomorrow is the big day and I'm really hoping everything goes well and in our favor.