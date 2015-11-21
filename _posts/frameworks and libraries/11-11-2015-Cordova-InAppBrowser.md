---
layout: post
title: "Streaming Media with Ionic Cordova"
modified: 2015-11-19
categories: Ionic, Cordova, Angular, Native
excerpt: Streaming media with the Ionic, Cordova InAppBrowserPlugin
tags: [Ionic, Cordova, Angular, Native]
image:
  feature: cordova-ng-ionic.png
  teaser: 
  thumb: 
ads: false
date: 2015-10-02T13:43:58-07:00
---

This post is specifically about my usage of the Cordova, InAppBrowser plugin. I did a considerable amount of searching to find answers to the problems I had and if I can help just one person get down to the root of their problem faster I'm more than happy with the time spent on this.

####First off, benefits of the InAppBrowser plugin:

  **Case: Accessing streaming media API's such as Soundcloud, Youtube, Vimeo...**
  
  - Instead of actually embedding iFrames/widgets or even making frequent API calls, I just want to go straight to the media the sites link to using the oembed links (or not). I don't want to have to load all this stuff when my app loads. I may not need EVERY link. I don't want to have to manage the API's plugin options (turning off autoplay/autoload...) so that it doesn't steal resources from my app while loading. I just want to get the user to the content they need and I want the freedom (as much as possible) to determine how that content is displayed.

  - Essentially, I want to create list items that the user clicks on, it opens the browser, they view the content (or not) which only then is it loading/streaming, hit the done or close button, and they're right back in the app where they left off.

####Using the Plugin

Let's assume a few things:
- You're using Ionic/Angular version 1.x
- You've installed the InAppBrowserPlugin: `cordova plugin add cordova-plugin-inappbrowser`
- You've injected `$cordovaInAppBrowser` into your controller as a dependency

Assuming that you've completed the steps above everything else is simple enough. The first thing you'll need to do is to set the options for the InAppBrowser which I reccommend doing as such:
`var options = {`

      `location: 'no', // Whether you want to display the url`
      `clearcache: 'yes',`
      `toolbar: 'yes', // Must be set to yes in order view the 'done' button`
      `closebuttoncaption: 'close', // (ios) Must be set but you can choose the caption` 
      `hardwareback: 'yes' // (Android) Enable the Android back button`
    `};`

The next thing you'll need to do is capture the URL **Note: You'll need to have the `cordova-plugin-whitelist` installed in order to resolve http to https**
I personally like to set the url to a variable and pass it in to make my function call cleaner: `var url = https://www.soundclou.com/[name of the stream]`
Finally, you'll want to call the the browser open function and pass in the paramenter like so: `$cordovaInAppBrowser.open(url, `_blank`, options)`. 

This should allow you open your streaming media without embedding iFrames/widgets, and making API calls, and you'll be able to close the browser with the `done` button and return directly to your app.

Another important note: make sure to test these in device emulation. Running it in the desktop browser is not reliable in terms of testing.

**Update: the InAppBrowser plugin works differenty in Ionic v2(alpha)**


