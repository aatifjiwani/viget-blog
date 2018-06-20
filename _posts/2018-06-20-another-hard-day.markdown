---
layout: post
title:  Another Hard Day.
date:   2018-06-20
category: third
comments: true
---

Not gonna lie but today was pretty challenging. I finished up the comments feature and now it was time to write some tests, both model and feature. 

The model specs were not that hard actually. They were pretty simple and not too challenging. 

However, the real doozy came down to the feature specs. At first, I thought it was going to be pretty simple like the model specs but I was WRONG. One thing I forgot about Capybara is that it doesn't fricken render the javascript. That's a problem because in order to reply to another comment, I use javascript to make the textarea appear when a button is clicked so the page isn't littered with like tons of big textarea boxes. So, I had to figure out how the heck I was going to render javascript. At first, my methods didn't work so I had to ask Eli. Eli recommended using the chromedriver-helper gem and he gave me the configuration he used for it. But, my tests were still not working. It wasn't finding elements that were CLEARLY on the page and I had no idea wtf was going on. 

After about a half-hour or so, Eli and I figured it out but then I ran into another problem. When the javascript renders, so does the CKEditor textareas. This is a problem because using the plain fill_in command wasn't working anymore because it wasn't finding the textbox. Sooooo, I had to figure out how to enter text within the CKEditor textarea and that took a whole-nother gosh darn hour. 

After that, I ran into another problem. The <a> element that when clicked renders the textarea wasn't showing as a clickable link through Capybara. This was because I didn't define a href attribute which I guess is necessary. When I set the href to #, my javascript was messing up because the page kept reloading and resetting the textboxes. So after digging around the internet, apparently you can define href to be `javascript:void(0)` and clicking the <a> tag does absolutely nothing!!!!!!
    
Once figuring all that out, I got my feature specs to work and now all my tests pass. YAY! But despite that, these problems hurt my brain and I had to dig around Google for so long because it is rare that people come across the type of problems I have. 

Tomorrow, I am going to finalize my blog and start working on the Week 4 specs which is the ability to upvote/downvote articles and filter the articles based on whatever the user chooses. 