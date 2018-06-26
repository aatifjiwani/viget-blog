---
layout: post
title:  Bonus Spec
date:   2018-06-25
category: fourth
comments: true
---

Today was a pretty sweet day! I got a lot of feedback on my PR which was really good because it made me think about the various problems or security vulnerabilities there may be. I also learned that it is good to put logic in templates and use querying stuff in helper methods so it reduces the chance of someone finding out how the app functions (without looking at the GitHub lol).

Then, today I also worked on getting the home page to filter articles based on how high its been rated within the past year, month, day, or all-time. Originally, I was just going to use ajax in order to re-filter the current list of articles asynchronously but Eli gave me a better, more logical, and ultimately easier way of doing it. I just simply send a GET request to the index action of the Article controller with a parameter of how I want to filter the articles. Then, I just check that the parameter is there and perform some actions on the Vote model. 

I also learned about scope which is how I perform the databse queries to get the highest rated articles of a given time period. It took a lot of thinking honestly and I still don't believe I have the best way of doing it. But, so far everything works and I'm about done with doing the testing. 

That's it for today!