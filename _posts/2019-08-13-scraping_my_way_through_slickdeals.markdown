---
layout: post
title:      "scraping my way through slickdeals"
date:       2019-08-13 22:51:40 -0400
permalink:  scraping_my_way_through_slickdeals
---


Scraping is the second project I've ever worked on that wasn't entering code with prewritten tests. I had a hard time, but I also enjoyed  seeing the tools that I have developed through this cohort & putting them to use. 

First, I thought of a website that I visit frequently. Since I work full time, I don't really have time to go shopping. I also enjoy finding a good deal, so when I need a new pair of running shoes, Slickdeals.net is my go to. 

Getting familiar with the Chrome developer tools was interesting. I've stumbled up some the developer tools before, but I never though I'd actually be doing something with them. 

One hiccup I encountered which I'm sure is common with scrapers is converting the scraped data to something readable. After all, that is the objective of scraping. I ran through 3 different gems to read files, chose the best ones with the highest rating. When Nokogiri didn't format the data I needed correctly, it was time to move on. That was an easy decision. When I used another gem that wasn't pulling the data and converting special characters directly, I had to search for another gem.  Maybe that's the toughest part of using gems that I've encountered thus far in ruby. We have this conception of gems, and if the one you chose didn't work, do you keep searching for one that does, look for various other examples, search stackoverflow back & forth, or just make your own? I think at this point, I was most frustrated with this project! 

Nokogiri was defintely not working, neither had another gem I had installed. Then I tried *htmlentites*. I hate to admit that it didn't work at first, and I used another gem because it wasn't encoding & decoding the entities as it had suggested it would. I was trepedatious to go back to it especially since the last update was on July 05, 2015. Kind of out of date... Maybe technology had changed since? It was back to the drawing board. I found an article on [github](https://github.com/threedaymonk/htmlentities), and at the very bottom of the page, there was my solution, like the holy grail full of the finest belgian ale!

**coder = HTMLEntities.new(:expanded)**

An override message was all it took. I completely understand why they call these tools gems now! 

Another hurdle that was challenging was again formatting, because of course, it is the nature of the beast known as scraping. I must have spent 2 hours trying to format my pricing that I was pulling from the website because some of the prices were "2 for $20". I wanted to keep the dollar amount after the $. I tinkered with various types of numbers;  $integers, 2 for $20, $floats, invalid data, etc. I finally came up with the following: 

/(.*\$\d*\.?\d{0,2})/

What does it do? Well, simply put it gets the number after the $ sign & up to 2 decimal places. I could have accommplished this task with /(.*\$\d*\.?\d\d)/  as well, but I am trying to get fancy with my regex. 



