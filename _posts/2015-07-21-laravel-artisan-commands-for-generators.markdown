---
layout: post
date:   2015-07-21 19:38:10
title:  "Laravel artisan commands for Generators"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

I got sometime to play with laravel's new version 5.1. There are lots of artisan commands for productivity and creating a code stub of laravel components from the command line.

I'm going to discuss make commands that generate a file in the laravel application with basic code stub

We can see all make command in the make section of the artisan command list:
{% highlight bash %}
  php artisan list
{% endhighlight %}

**Generate a command class**
{% highlight bash %}
  php artisan make:command nameofcommand
{% endhighlight %}
This command will generate new command file at app/Commands/nameofcommand.php

**Generate a console command class**
{% highlight bash %}
  php artisan make:console nameofclass
{% endhighlight %}
This command will generate new console command file at app/Console/Commands/nameofclass.php

**Generate a resource controller class**
{% highlight bash %}
  php artisan make:controller mycontroller
{% endhighlight %}
This command will generate new resource controller file at app/Http/Controllers/mycontroller.php

**Generate an event class**
{% highlight bash %}
  php artisan make:event myevent
{% endhighlight %}
This command will generate new event file at app/Events/myevent.php

**Generate a job class**
{% highlight bash %}
  php artisan make:job myjob
{% endhighlight %}
This command will generate new job file at app/Jobs/myjob.php

**Generate an event listener class**
{% highlight bash %}
  php artisan make:listener mylistener
{% endhighlight %}
This command will generate new event listener file at app/Listeners/mylistener.php

**Generate a middleware class**
{% highlight bash %}
  php artisan make:middleware mymiddleware
{% endhighlight %}
This command will generate new middleware file at app/Http/Middleware/mymiddleware.php

**Generate a migration class**
{% highlight bash %}
  php artisan make:migration newmigration
{% endhighlight %}
This command will generate new migration file at database/migrations/timestamp_newmigration.php
(timestamp will be actual timestamp :) )

**Generate a model class**
{% highlight bash %}
  php artisan make:model mymodel
{% endhighlight %}
This command will generate new model file at app/mymodel.php

**Generate a model class**
{% highlight bash %}
  php artisan make:model mymodel
{% endhighlight %}
This command will generate new model file at app/mymodel.php

**Generate a provider class**
{% highlight bash %}
  php artisan make:provider myprovider
{% endhighlight %}
This command will generate new provider file at app/Providers/myprovider.php

**Generate a request class**
{% highlight bash %}
  php artisan make:request myrequest
{% endhighlight %}
This command will generate new request file at app/Http/Requests/myrequest.php

**Generate a seeder class**
{% highlight bash %}
  php artisan make:seeder myseeder
{% endhighlight %}
This command will generate new request file at database/seeds/myseeder.php

Few of the commands were available in the 4.2 version and few of them are introduced in the 5.1. Apart from this, you can get more info about command by following:

{% highlight bash %}
php artisan help commandname
{% endhighlight %}

Enjoy!!