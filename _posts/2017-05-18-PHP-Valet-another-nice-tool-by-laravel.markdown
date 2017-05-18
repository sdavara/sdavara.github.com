---
layout: post
date:   2017-05-18 19:15:10
title:  "PHP Valet: Another nice tool by laravel"
status: publish
categories:
- Article
- Programming
tags:
- Article
- Programming
---

It is almost 4+ Years, I'm working with the Laravel PHP framework. When I first started, it was all about a new way of writing PHP applications. I was quite impressed with the structure and I have not looked back since then. It was laravel 4.x version of my first laravel PHP application.

Laravel has a vibrant ecosystem. Laravel has not only provided just a framework, we got a whole new development toolset for the PHP development. We can name it as Eloquent, Forge, Envoyer, Homestead, Middleware, Composer, Lumen, Blade Templates, etc. You can see these growth around your development too.

I still remember, it was quite a challenge to run PHP laravel on OSx. It took a while to get up with a system. Earlier version of Laravel had a dependency of mcrypt extension. Later, homestead box came and it made development easier. With the help of homestead box, you can run any of your PHP projects in a same box. You just have to configure once. There were a few issues with it, due to virtualbox. After all, we were running our projects inside guest OS with the help of a Vagrant box (Homestead).

I'm a bit late in Laravel [Valet](https://laravel.com/docs/5.4/valet). I wanted to write more about it when I first saw it, but I could not able to do it. Finally, after a long wait, I'm writing here about it.

I don't need to say much about it, as documentation has covered most of the things which I had to tell. I'll list a few points while using Valet:

** Valet runs in your native OS, so you get the power of your CPU and memory.
** Valet only works with OSx as per the documentation. But, I really want to try Linux and it should work there.
** Valet is a Composer package. Make sure that you have the latest version of composer installed in your machine.
** Valet is using ngrock in the underlying for sharing your url. It will be very good for showing a demo work.
** Valet setup custom domain with the default '.dev' extension without any configuration.

You may face following errors while working with PHP Valet:
** If you have nginx or apache installed, it may interrupt to Valet. Please stop all those services.

{% highlight bash %}
sudo nginx -s stop
{% endhighlight %}

{% highlight bash %}
sudo /usr/sbin/apachectl stop
{% endhighlight %}

** Due to older version of composer packages, it doesn't work. Please update all your global composer packages.

{% highlight bash %}
cd ~/.composer
rm -rf vendor
composer global update
valet install
{% endhighlight %}

I've tried Valet for Wordpress projects, laravel 3.x, laravel 4.x, laravel 5.x, angular web applications and as a static website server. It worked nice all the time. What are you waiting for? Try and share your experience with others.

All the best!!