---
layout: post
date:   2015-03-03 17:30:10
title:  "Solve CORS issue in the Laravel API(a dirty way)"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

I've been developing an API in my favourite framework Laravel. It went very well. When I tried to consume that API in an another application, I come to a very known issue of CORS. I should also tell you that I was consuming this API in an Angular application.

Many of you have experienced below error, when you try to consume API.
<pre>
XMLHttpRequest cannot load [weburl] No 'Access-Control-Allow-Origin' header is present on the requested resource. Origin '[API hosted domain url]' is therefore not allowed access.
</pre>

To overcome above error, I come to a temporary solution in Laravel 4.2. Add below lines on the top of **routes.php** file and the error will go.

<pre>
	header("Access-Control-Allow-Origin: *");
	header("Access-Control-Allow-Methods: GET, POST, OPTIONS");
</pre>

I know above solution is not efficient, but till we go into production, It works and solve our issue.