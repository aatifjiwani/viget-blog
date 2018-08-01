---
layout: post
title:  Almost Done!
date:   2018-08-01
category: ninth
comments: true
---

I know, I know, I've been lacking a little bit when it comes to blogging. BUT I have a pretty good reason. This week is the last week to work on the web app for the group project. Therefore, we literally have to finish and fix everything by thus upcoming Friday. On Monday, I was completely swarmed with new QA tickets that addressed random things that I didn't even knew happened. On Tuesday, I worked from home because of the Playboi Carti concert but I still wasn't able to finish everything. 

So today, I came into the office with the mentality that I have to finish almost everything today or I'm screwed. First, I started to address the problem where AWS was being super dumb. Apparently, the client key and secret app key were both invalid and for some reason, everything just dissapeared from my AWS S3 bucket. This was extremeley odd and Pat and I were trying to figure out the problem for so long. It wasn't until David B. helped me out and realized the problem. The HTML and embedded ruby structure was messed up. All the HTML code was embedded within a `<style>` tag which is clearly not what we want. 

After I fixed that issue, I started working on the feature where a user can see interim voting results of his/her own poll but also cannot vote on his/her own poll. This wasn't too hard as I used the same logic for expired poll voting and just refactored it hella to fit this new feature. 

Finally, I started to work on the feature that visitors can vote on polls. At first, I didn't really want to implement this because there would be hella tradeoffs and a lot of security vulnerability. However, this was a feature that was discussed at the beginning of the group project. So after listening to all the interns speak their opinions about this feature, I just sucked it up and implemented it. Honestly, this wasn't really that difficult. It was just long. I had to create a new model (something I haven't done in like a month), new controllers, new tests, and refactor existing code. In all, it took me about 2 hours and now I have a PR up. Eli already commented and approved it but I have some questions to ask him about how to better organize the code I just wrote. 

Welp, I finished today successfully. I think tomorrow will be a tad easier since there aren't really many more tickets coming in. 