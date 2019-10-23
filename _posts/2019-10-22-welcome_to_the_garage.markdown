---
layout: post
title:      "Welcome to The Garage"
date:       2019-10-23 03:20:41 +0000
permalink:  welcome_to_the_garage
---


I created an app that is a database for the cars you own. I got the general platform down to CRUD (Create. Read. Update. Delete) the items associated with the user in the database, and while building it, I thought of so many ways to improve it. Since I am behind on life, I had to go bare bones with the project. Overall, it was an intense learning experience. 

I think the hardest part about starting this project was; 1. What should I build? I really wanted to build something that I could use in the real world, but unfortunately one of the lessons leading up to the project had my idea (recipes). Another thing that I struggled with was actually setting up the project. Then I remembered that Avi would look at his old projects and just steal his set up for other projects that he's worked on. It seems that this is a standard practice that I should have implemented sooner, instead of going to stack overflow too many times. 

Another thing that I struggled the most with, was the authentications to log in. Everything seemed so seamless as far as design decisions went, then it was getting the project to work as requested. 

I remembered that using a helper method "if logged_in" from a different exercise really helped with the user having the ability to see their items. Unfortunately, the user was still able to see EVERYTHING in the database. 

For me to fix this, I had to create an instance variable for the car 

if @car.user == current_use 

then I could show them the things they want to see. I pretty much put that snippet everywhere in my code & viola. I guess I could have used a helper method for that, but at the end of the day "ship it". 
