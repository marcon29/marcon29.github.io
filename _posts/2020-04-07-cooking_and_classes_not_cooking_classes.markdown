---
layout: post
title:      "Cooking and Classes, Not Cooking Classes"
date:       2020-04-07 19:29:39 +0000
permalink:  cooking_and_classes_not_cooking_classes
---


When you’re first learning something, it’s easy to think you’ve got it handled. You start out knowing nothing, and within a short time, you’re doing things you couldn’t before. You think you’ve got it. In reality, you’re so new, that you don’t know what you don’t know. So I was looking forward to my first solo project, a CLI Data Gem,  to see if I actually understood things as well as I thought I did.  Turns out, I did…and I didn’t.

The full premise of the app is that it’s a pain in the ass when, after a long day of coding, you decide to relax by trying a new meal and, after you’re already home, you find out you don’t have the right ingredients. I don’t know about you, but when I get home, I don’t want to go back out to the grocery store. So, this app lets you look up some recipes on Allrecipes.com via your CLI, and compile all the ingredients you need. Then you can use that list as a grocery list, and hit the store on the way home.

I originally conceived of the app as allowing the user to type in the name of a recipe, and then the app would go find it. Using the URL structure of the site made this relatively easy. However, it created one big problem – the user needed to know the exact name of the recipe. And as I thought some more, that’s not really the best use of the site. Part of the fun is finding new recipes. To solve both issues, I decided to add some browsing functionality. The app could scrape multiple pages, based on the user input, and allow them to browse the site itself (limited to the most popular dinner options) from their CLI.

As I’m sure is common with all projects, some parts went smoothly, some tied me up. I lucked out in that scraping the site proved relatively easy. All the information I needed was organized under a single CSS selector, so I didn’t have to dig through the Nokogiri objects much. Within a few hours I had a perfectly working program. But it was long, repetitive, and procedurally based. The main problem was that it worked with limited test data but didn’t allow for easy extension (i.e. looking up different types of recipes).  I needed to make the browsing functionality more modular. It needed to create multiple categories on demand, AND in a hierarchical structure. 

Needless to say (and to keep this short), I did work this problem out. The key, for me at least, was understanding a class as a role. I originally conceived of my category class as nothing more than something that made scraped data available to the rest of the app. It was a data processor. What it needed to be was a class that controlled categorization itself. This means it’s role was to create the categorical structure, not just process category-level data. 

What makes something a category (instead of any other object) is its relation to other things. Categories needed to know if they were parent or child categories or both.  This reminded me of the basis of the Ruby language itself – a bunch of independent objects communicating with each other. Once I thought of a category as more than a collection of data, and instead as sending signals about how to move within that structure, everything fell into place. 

In the end, each instance was a separate category. Each one knew its place in the hierarchy (provided by class-level tracking) and could communicate what categories a user could move to. Then the CLI class, which acts as the app controller, could use those signals to direct the app on what to do next – either move from one category to another, or get some recipe data. 

My categories (and their associated user menus) became modular. When I was done testing and it was time to add some more categories, all I needed to do was add a single entry into an array. Ok, a couple required some other tweaks, but they were due to inconsistency of the Allrecipes website. If this app was using a more consistent data source, like a database, a simple array addition is all it would take to create infinite categorization. And I think that’s pretty cool.

So anyway, I succeeded overall. But at the same time, if I had a better understanding of what classes should really be and how they should really function, this probably could have been done in half the time, which would have allowed me to add more functionality. Hell, for all I know, this is child’s play. And anyway, I’m pretty I’m missing something else that could make this app even better. 

We’ll see what the judges think.

