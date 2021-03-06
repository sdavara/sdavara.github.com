---
layout: post
date:   2016-11-08 11:15:10
title:  "Don't go for the single page framework in public facing web application"
status: publish
categories:
- Article
- Programming
tags:
- Article
- Programming
---

I've been heavily involved in the development of front-end application with Angualr.js for 3+ years. During all these times, we have been using angular.js for one of the SAAS, we have come across many issues and solved it successfully. We never get to move into another framework when we see other front-end framework. We had our own issue in the moving to another framework, we have been writing our application for more than 2+ years and small time to learn the new framework. We have all things fulfilled in our framework in a way or two.

In a spare time, we explored other framework and enjoyed working with the new framework.

Due to the rich experience of angular.js, we have started to build a new application inside it. That was a public facing web application. Our development went nicely and soon our web application was ready to use. Again, I remind that it was a public facing web application, we were expecting to see the user has come and use our application. We have done possible SEO thing and we were pretty confident with our product. But, our assumption was wrong. When we checked our analytics report, it was a bit shocking as nobody found us in the organic search. Results were almost zero. We assumed search engine would understand angular.js application and show us in the results set. After checking all, we needed to find some solution to this situation. We used third party services for SEO purpose. Basically, that service returns the html markup when requested the angular url and finally, it started to show us in the results.

From this experience, we concluded that for the consumer facing application never advisable to go for the single page framework. That's always painful to go back and rewrite. When we know anything better, we tend to go for that over other things, but sometimes that lead us to a point where we regret our decision the most. Every shiny framework is not useful as we think so. I had a personal feeling of not to use angular.js, but considering the complexity involved we choose it and regretted it.

P.S: When I say public facing web application, I mean to say our landing page application that doesn't ask for the user credential. The user can freely use it without any registration or logon.
