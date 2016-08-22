---
layout: post
date:   2015-05-13 12:20:10
title:  "SEO friendly URL in AngularJs application"
status: publish
categories:
- AngularJs
- Programming
tags:
- AngularJs
- Programming
---

You have built a beautiful site using AnguluarJs and have a bunch of cool stuff on your site. Your site contains quality content and you wonder, why don't you see any user on your site from search engines?

That is a little issue with your AngularJs application, it uses '#' for url routes. Search engine crawler doesn't parse data of that url, you will need to find an alternative.

There are different options, you can use. We will go ahead with 'hasbang'. In this option, we will replace '#' with '#!'.

Below are steps to configure your AngularJs application

**Step 1 : Add $locationProvider and prefix**

{% highlight javascript %}
	angular.module('myApp').config([
	    '$locationProvider',
	    function($locationProvider) {
	        $locationProvider.hashPrefix('!');
	    }
	]);
{% endhighlight %}

You will see your default route is changed to, http://yourdomain/#!/

In some cases, it doesn't work for that you may need to turn off html5Mode, as below:

{% highlight javascript %}
	angular.module('myApp').config([
	    '$locationProvider',
	    function($locationProvider) {
	        $locationProvider.html5Mode(false).hashPrefix('!');
	    }
	]);
{% endhighlight %}

**Step 2 : Update AngularJs link url**

You have set your application to use '#!'. Now, it's time to update all your internal links of AngularJs application.

{% highlight html %}
	href="#!/"
{% endhighlight %}

You can check, if the search engine is able to crawl your site or not.