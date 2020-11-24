---
layout: post
title:      "ES5 vs ES6: bind, this, context..."
date:       2020-11-24 06:56:37 +0000
permalink:  es5_vs_es6_bind_this_context
---


*this: Inside a function, this is the Object that represents the function's execution context*
It is important to talk about [context](https://towardsdatascience.com/javascript-context-this-keyword-9a78a19d5786); 
> Context is always the value of the this keyword which is a reference to the object that "owns' the currently executing code or function where it's looked at. 

When I was learning how to code in JS, they taught you how to code using Ecmascript 5 (ES5) syntax. Further down the ciriculum, I began to learn ES6 syntax, which was released in 2015. Initially, I found it difficult to transition from ES5 to ES6, but all the tutorials online said it was more beneficial to code with ES6. 

Of course when I was working on an increment button for my app, I instinctively used ES6, which I am much more comfortable with now. But what is the benefit of ES6? The truth is, I couldn't remember why it's beneficial aside for less typing! Having that said, I'm going to break down my button increment code & explain why ES6 is more beneficial. 

Here is a snippet of my code initially; 

```
import React, { Component } from "react";

class Button extends Component {
  constructor(props) {
    super(props);
    this.state = {
      click_count: 0,
    };
  }
	
  handleOnClick = () => {
    this.setState({ click_count: this.state.click_count + 1 });
  };

  render() {
    return (
      <div>
        <button onClick={this.handleOnClick}> On Click </button>
        {this.state.click_count}
      </div>
    );
  }
}

export default Button;
```


My Button class consists of my constructor, my event handler in ES6 & my render with return. The most important part about this is my event handler handleOnClick. This is where my fancy ES6 syntax is coming into play. Under the hood though, my ES6 is binding "this" for me so I don't have to explicitly bind it.  Syntactical magic! 

If I changed my code event handler to the code below, I get a *TypeError: Cannot read property 'setState' of undefined.* 

```
  handleOnClick() {
    this.setState({ click_count: this.state.click_count + 1 });
  }
```

**this** is triggering the error. But why? Well, as stated in [react.js documents](https://reactjs.org/docs/handling-events.html), 
> you have to be careful about the meaning of this in JSX callbacks. In JavaScript, class methods are not bound by default. If you forget to bind this.handleClick and pass it to onClick, this will be undefined when the function is actually called.

Undefined you say? Well that is EXACTLY WHAT MY ERROR ABOVE SAID! 

To fix this error in ES5, I could use Bind in the Constructor like so:
```
class Button extends Component {
  constructor(props) {
    super(props);
    this.state = {
      click_count: 0,
    };
    this.handleOnClick = this.handleOnClick.bind(this);
  }
```

So to answer the Why do I need to bind? Again, according to the [react.js docs](https://reactjs.org/docs/faq-functions.html),
> If you need to have access to the parent component in the handler, you also need to bind the function to the component instance (see below).

I think the best summary of "this" in a regular ES5 function vs an arrow ES6 function is summarized [here](https://www.freecodecamp.org/news/when-and-why-you-should-use-es6-arrow-functions-and-when-you-shouldnt-3d851d7f0b26/): 
> In classic function expressions, the this keyword is bound to different values based on the context in which it is called. With arrow functions however, this is lexically bound. It means that it uses this from the code that contains the arrow function.

Since ES6 is still relatively new, and the actual react documentation calls the way I initially coded my event handler, with a *// Note: this syntax is experimental and not standardized yet.*, I believe learning both ways; ES5 & ES6 ,are beneficial especially if you're working with code that is barely 5 years old! Regardless, I will have to be more mindful of both ways to get my this context, but I am sick fo typing, so it's going to be back to ES6 once this is over. 


additional references: 

https://medium.com/@thejasonfile/es5-functions-vs-es6-fat-arrow-functions-864033baa1a
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind
https://reactjs.org/docs/faq-functions.html
https://reactjs.org/docs/handling-events.html
https://www.freecodecamp.org/news/when-and-why-you-should-use-es6-arrow-functions-and-when-you-shouldnt-3d851d7f0b26/


