---
layout: post
title:      "Sinatra’s “My Way” Was Much Better Than My Way"
date:       2020-07-06 23:57:55 +0000
permalink:  sinatra_s_my_way_was_much_better_than_my_way
---


I’ve always spent a fair amount of time researching topics that interest me. And whenever I found an article or information source that I wanted to keep, I usually emailed it to myself. Over time, I ended up with hundreds of emails and no idea what they were. It was a mess. I always wanted a way to store and organize that info. And I wanted it to be online, as I would often find things at work and home.

So for my Sinatra project, I decided to finally create the tool I wanted. The end result is Sourcerer. It’s a basically a more robust bookmark manager. It focuses more on saving specific pages (vs. entire sites) and allows for multiple categorization to make it easier to reference back to an unlimited number of sources for any custom defined topic. In addition, optional sharing capabilities allow a user to see what sources others have found on the same topic. 

And as I found with my first school project, you never know as much as you think you do. I learned some valuable lessons during this project, especially about how to approach and work through a dev project. And because I was always the type of person that needs to touch that hot stove to see what hot feels like, I learned it all the hard way.

So here are the lessons I learned.

I will never do a project again without developing my own tests. I think I spent as much time manually testing as I did actual coding. And of course, due to the associations between models, you can never just change one thing. So you make one thing better and it breaks the program somewhere else. Without the automated tests, you end up re-testing everything again and again and again and again and again and again…  But what’s worse, I found that to even keep track of all the possible issues, I essentially wrote the tests anyway. So, never again. Time to master rspec.

Secondly, I definitely learned the value of getting your models and specific features nailed down completely at the beginning. I made the mistake of working across the board, simply because the code was so similar, and I though the copying and pasting would make things faster. What ended up happening is that when I started working beyond the basics, I had six places to refactor instead of one. So get that first model working perfectly. Get the views and controller for that model working perfectly. Then move one. I could have saved myself a couple days.

Despite my bitching (it’s still professional to use that word, right?), I’m still happy overall with the result. As I mentioned, I created a tool I’ve always wanted. It works well, but could use some fine tuning. But as I continue on this course, I’ve got some good groundwork laid to make this app everything I really want it to be as I continue to learn.

