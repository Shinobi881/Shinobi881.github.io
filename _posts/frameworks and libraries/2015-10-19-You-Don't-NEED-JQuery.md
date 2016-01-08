---
layout: post
title: "You don't NEED Jquery"
modified:
categories: Libraries and Frameworks
excerpt:
tags: [jquery, angularjs, reactjs, backbonejs, angular, react, backbone, libraries, frameworks, javascript]
image:
  feature: JQuery_logo1.png
  teaser: 
  thumb: 
ads: false
date: 2015-10-19T13:43:58-07:00
---

## I keep on hearing "You don't JQuery!!!"

Truth be told, you don't really NEED anything but vanilla JavaScript to engineer in JavaScript. But we've done some things to make it faster and eaiser for to be more productive with JS. The ongoing mission to improve user experience but most importanly, maximize for developer time. Enter JS libraries, frameworks and such. Or really just the concept of code reuse. I'm really just going to start rambling with out any specific examples but simple enough concepts, in the attempt to prove that: "No longer should JQuery be used in a shipped product." 

##The questions I'd ask: 

- What are you using JQuery for?
- Are you using JQuery on top of another framework?
- Are you using enough JQuery to include a whole library?
- Is JQuery a library or framework (I'm still trying to figure this out. If I put much though to it I could prob make a good case for both. It probably is both with consideration to context of use)?

I do believe that JQ is fundamental to JS development. There are some moments when you have to just maximize for dev time and JQ is helpful for that. But let's be real, these days, you're likley working Angular, React or Backbone (let's not even talk about React Native and/or Ionic). Some version of these has JQ or JQlite included. But the frameworks themselves come packaged event listeners and triggers, animations, their own DOM manipulation tools... Bottom line, if your app is well built with the framework you're using there is no need for JQuery at least in the shipped version. I should say that DON'T use JQ in the shipped version (or get it out in future realeases). 

I'm just starting to dabble in React and I'm seeing that some parts of it are intentionally left open for use with JQ, if you choose. In which case, use it! I'm curous as to whether or they will continue with this pattern in future versions. But in Angular, most of the ways that you'd use JQ - which I've stated above - are mostly built in. Use those. 

The battle here, is what is maximizing dev time? Just using JQ to get the job done now or possibly spending more time debugging later, why what should work, doesn't?

I said all that just to really say, using JQ these days is like mixing inline styles and stylesheets, Eventually, something is going to mess up and you need to account for it. 

##So in summary: 

- When you're just checking "real quick" just to see if that one thing works, make sure to account for it or just use DevTools.

- Check first to see if your framework already has something for that

- Make sure you account for where and how you're using (a case for good documentation) and keep in clear mind potential conflicts.

- Are you using it enough to include the library (yeah, even JQLite)

But even with all this, JQ is still very relevant and useful. Just be careful in how you use it.
