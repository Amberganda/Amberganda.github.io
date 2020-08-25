---
layout: post
title:      "Programming with React"
date:       2020-08-25 01:31:01 +0000
permalink:  programming_with_react
---


I just finished my final project. Going through all of the steps to get there was pretty intense. I feel like I learned a lot, but I still have some work to do to become more comfortable with the components and connections, etc. Working on this project definitely helped me grasp the key concepts. Now I am going to write about my project, what resources I used, and overall what I learned. 

From my previous project, I realized that it is a LOT easier to work on any project with a plan. With this project, I didn't necessarily do the flow chart like I previously did, but I did do more visual drawing to plan how my project would look & interact with the user. I also used a README.md file to document what I would need in my project (backend, my get requests, and my front end). This was a new technique that I adopted after watching [this](https://instruction.learn.co/student/video_lectures#/498) setup. 

After I followed along with the setup, I referred to a drawing that I made: https://imgur.com/VGg46pY.jpg
I wanted to have a single page application that once loaded Locations on the main page, I could click tabs from the nav bar & have a subset of items that I wanted to be sort of a filter using react, so it wouldn't reload every time I navigated to another page. 

Since I had so much fun doing travel apps, and I'm looking forward to travelling once this pandemic is over, I used another travel app idea. This time I wanted to use an API. [UNESCO](https://whc.unesco.org/en/list/) had just thing I needed. I built out the backend, then started working on the front end. After I followed along with installing the dependencies needed to fulfill this project (react-redux, react-router-dom, & react-thunk), I was ready to get my front end together. 

My nav-bar was pretty simple to set up, but I needed to use the React Router to handle my routes in my nav-bar. I followed along with [this](https://www.youtube.com/watch?v=Law7wfdg_ls) tutorial to get the basis down. After that, I wanted to render a LocationsList on my main page. Once I had my main page "/locations" or /, I could filter what people clicked on. There are 3 buttons for the user; like a location (icon: heart), want to go (icon: + ) & been there (icon: check mark). Those clicks change the state of the location and will change the filter that the user is on.  The nav-bar had the filters for /favorites, /destinations, and /visited. If the user is in the /favorites tab, only the cards that they clicked the heart on will display.

Finally, my Actions.js file needed to handle the 3 buttons. Once I was done with my actions, I had to get the data with an outside API. (Un)fortunately, I realized that I had to pay for an API, but found a couple of online APIs with the data I needed, so I used this [link](https://unesco-api.herokuapp.com/sites). Once that was set up with from index.js, I used 1 item initially seeded from the original unesco website, but it wasn't in the other API that I used. I think this was kind of cool because the one that wans't there didn't have a picture to pull from, but I was able to use broken data from my seeds file that didn't have an image & load it. 

Ideally my idea of this project came from a story that my coworker told me. He went to a church in Norway that was closed, but he met a guy outside the church that said his hobby is travelling to Unesco sites. I thought it would be such a great idea, to have a database that you can click that you've been there, you like it, or that you want to go there. Now that I think about it, I believe Google has some of those features, but it their setup isn't a card. In the age of Facebook and Instagram with thir reusable components, we (as users) are used to seeing things in card form. Overall, I am proud of the outcome of this project. I think there are areas that I can improve on, as far as optimalizing the time it takes to load, and more features I'd like to add. But overall I think it does exactly waht I wanted it to do. 
