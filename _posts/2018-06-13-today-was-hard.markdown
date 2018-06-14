---
layout: post
title:  Today I Struggled...
date:   2018-06-13
category: second
comments: true
---

Today was hard holy cow. I started and finished working on user creation and authentication and boi was that hard. 

In terms of user creation, it wasn't hard to setup the front-end and make sure that my form submits properly. However, when it came to user authentication, that's when stuff got real hard. 

I ran into a lot of problems when trying to figure out password encryption. I used the bcrypt gem, which is what Viget uses in their rails apps, and the guide I was using was absolute trash. It did not go over how to decrypt the password once it was encrypted and stored into the database. 

Once I ran into that problem, I had to pretty much start all over. I had to change the user table schema because apparently bcrypt needs a column labeled 'password_digest'. This was NOT expressed in the guide I was using before. I also had to import certain methods that bcrypt uses to automatically authenticate a user when given the right password. 

Then, I had to create a session controller which was kinda tricky because it doesn't necessarily have a model associated with it. So everytime you go to a new route, it does nothing with my db. All it does it simply keep track of the user ID in the session hash that is bundled up into a cookie that is brought to every page you navigate to. 

After all that, I decided to install FactoryBot which was another challenge on its own. There were a lot of configurations that I had to add to certain files which kinda confused the living heck outta me. But finally, I figured it out and FactoryBot got installed. 