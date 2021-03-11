---
layout: post
title: Setting Up Your Business Website - Part 2  
---
*We walk you through Scribal's own process for setting up its  website. Choose your approach based on your specific business requirements. For us that means a Jekyll-based static site. Part two of two.*
<!--excerpt-->

[In the previous post in this set]({{ site.baseurl }}{% post_url 2021-02-03-WebsiteforBizpt1 %}), I discussed the considerations faced by business organizations needing to create or establish a web presence. I also examined, at a high level, how we at Scribal analyzed those considerations for our own business. In this post, I will walk you through what we actually decided and discuss the steps we took to implement the technology.

At this stage of our business's development, we required: 
- a place to publish our analysis and views on various technological and business-related questions. 
- we also need a way to identify ourselves, to let people know that we are open for business to contact us if they wish to do so.

These are our (simplified) functional requirements. We do not need to transact business, authenticate (sign-in) users, send a newsletter or perform any other interactive task. We may very well want to do some of these things in the future, but not now. We are being very careful with our resources, but still want to present a professional face to the world. As mentioned in the previous post we also have a small set of "non-functional" requirements: 
- retain control over the functionality of the site, not just the content;
- use open source software as much as possible
- learn and use technologies that others in our field are also using.

There are a number of available commercial services mentioned in the last post which enable small businesses to set up professional-quality websites faster and cheaper than ever before. In a larger corporation, the group that manages the company websites may have tools such as WordPress or Drupal that include content management systems that enable smaller non-technical teams to set up "mini-sites."  In any event, the most important step is for a team to query itself as to what functionality it really needs in a website, to get those requirements down on "paper," and then to analyze the goals and select the simplest way to accomplish them.

For Scribal, the fact that we did not need much, if any, interactivity led us toward static site generators which use Markdown files to deploy HTML pages to a hosting provider. There are a number of open-source static site generating systems - Jekyll is one of the most widely used. You can deploy Jekyll sites to any hosting provider, but Github automates deployments through its Github Pages feature. And Github Pages are free to set up and maintain.

We did spend time selecting and deploying a specific Jekyll theme - Lanyon - which gave us some elements missing in other themes. Github Pages and Jekyll are DYI tools, created and beloved by developers. They require a certain code savvy and willingness to modify configurations at the command line. So this set-up probably doesn't work for every corporate team or business, but for us it meets both our functional and non-functional requirements.


