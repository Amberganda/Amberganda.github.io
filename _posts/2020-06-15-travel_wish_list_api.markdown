---
layout: post
title:      "Travel Wish List API"
date:       2020-06-15 04:12:43 +0000
permalink:  travel_wish_list_api
---


Another project in the books. Although there was much less code for this project, it is much more powerful and robust due to using Javascript and Rails as an API. 

While creating this project, I really wanted to come up with something that I could build up functionally, as well as having those functions as something that I actually need. Whenever I travel, I always write out itineraries of what I'd like to do to optimally get as much out of my trips as possible. This is why I created the Travel Wish List Project. 

Starting the project off, I took some more time to plan out my project. Functionality, what my API should look like, etc. This was very helpful with the foundation of the project. I drew out this association before I started coding with draw.io: (https://drive.google.com/file/d/1Uq-pOcaCxAx7tqjTr0c0caE2fspQ8IHH/view?usp=sharing). 

Once I created the diagram, I built up the architectural features across the frontend & backend using the documentation that was provided to me by Flatiron. My backend was a API only Rails App so it only had some controllers (application, activities, and itinereries), empty models (activity and itinerary), and my serializers, cors. Most importantly, it did not have ANY views. That was going to be handled by my front end. My front end was also where most of the logic and data is coming from. More specifically my index.js file. 

My schema was pretty easy to ascertain. Since my Itinerary had many Activities, I needed to make the appropriate associations. Luckily, this was not a convoluted association with many-to-many associations. The [Rails Associations](https://guides.rubyonrails.org/association_basics.html#the-has-many-association) always comes in handy for the set up.

A handy tip I used this time around was when setting up my routes. I really stripped down a lot of my routes when setting up my project. Removing the following lines in my backend/config/application.rb really helped me with the noisy routes that I will never use: 
1. require "active_storage/engine"
2. require "action_mailbox/engine"

Once those were freed up, it was much easier to view my routes. This is another tip that I will use in the future while building projects. 

When I created this project, I had a lot of code all over the place in index.js. My final day, I had to create classes, and group stuff up in a more Object Oriented sort of way. I then created a class for Itinerary and passed objects to my constructor. 

I really struggled with the concept of *this* because it was always show up as undefined when I would bind to an object. To get over that obstacle, I had to  this.*instance-variable* & use the ES6 arrow syntax. Once using the newer ES6 arrow syntax, I was able to fix my issue.

I think my programming style has evolved a little bit more by using the arrow syntax. I was more comfortable with function syntax for readability, but knowing now the usefulness of arrow syntax, I just have to evolve.

Using [Materialize](https://materializecss.com/) was interesting, and surprisingly quite easy to utilize than Bootstrap. I chose Materialize over Bootstrap because a) it was recommended by my cohort lead & b) Materialize had exactly the type of buttons and cards that I was looking for. 

Overall, this project was challenging, but I feel like I learned a lot more about functionality of apps in general. There are so many handling issues that I could have worked on, put some graphics on, etc. It's amazing how interactive any small little page has with the user! 


