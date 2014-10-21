---
layout: post
date:   2014-10-21 18:11:10
title:  "Set Timezone in Laravel"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

Now a days, I'm working with PHP and particularly with Laravel framework. I have worked in MS stacks for 5+ years and last year or so I moved in open-source technologies. Since then, I got a chance to work with Laravel framework.

Though I am learning, I'd love to share what I learn. PHP Laravel is getting attention from the community due to it's easy to set up and powerful features. In earlier, it was quite a tedious process to change time zone in an application by passing an argument in datetime constructor or need to set in php.ini.

Laravel allows to set timezone in an application via configuration. I have been using the framework, but I have not come across any need of timezone yet. After looking at it, just one word 'awesome'.

We can set timezone in config file app/config/app.php or any app/config/environment/app.php at below section.


<pre>
    /*
    |--------------------------------------------------------------------------
    | Application Timezone
    |--------------------------------------------------------------------------
    |
    | Here you may specify the default timezone for your application, which
    | will be used by the PHP date and date-time functions. We have gone
    | ahead and set this to a sensible default for you out of the box.
    | 
    */

    // Default value of timezone is 'UTC', I have changed it to 'Asia/Kolkata'
    
    'timezone'  => 'Asia/Kolkata',
</pre>


Enjoy!!