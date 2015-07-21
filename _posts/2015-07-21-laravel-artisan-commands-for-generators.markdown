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
<pre>
  php artisan list
</pre>

** Generate a command class**
<pre>
  php artisan make:command nameofcommand
</pre>
This command will generate new command file at app/Commands/nameofcommand.php

** Generate a console command class**
<pre>
  php artisan make:console nameofclass
</pre>
This command will generate new console command file at app/Console/Commands/nameofclass.php

** Generate a resource controller class**
<pre>
  php artisan make:controller mycontroller
</pre>
This command will generate new resource controller file at app/Http/Controllers/mycontroller.php

** Generate an event class**
<pre>
  php artisan make:event myevent
</pre>
This command will generate new event file at app/Events/myevent.php

** Generate a job class**
<pre>
  php artisan make:job myjob
</pre>
This command will generate new job file at app/Jobs/myjob.php

** Generate an event listener class**
<pre>
  php artisan make:listener mylistener
</pre>
This command will generate new event listener file at app/Listeners/mylistener.php

** Generate a middleware class**
<pre>
  php artisan make:middleware mymiddleware
</pre>
This command will generate new middleware file at app/Http/Middleware/mymiddleware.php

** Generate a migration class**
<pre>
  php artisan make:migration newmigration
</pre>
This command will generate new migration file at database/migrations/timestamp_newmigration.php
(timestamp will be actual timestamp :) )

** Generate a model class**
<pre>
  php artisan make:model mymodel
</pre>
This command will generate new model file at app/mymodel.php

** Generate a model class**
<pre>
  php artisan make:model mymodel
</pre>
This command will generate new model file at app/mymodel.php

** Generate a provider class**
<pre>
  php artisan make:provider myprovider
</pre>
This command will generate new provider file at app/Providers/myprovider.php

** Generate a request class**
<pre>
  php artisan make:request myrequest
</pre>
This command will generate new request file at app/Http/Requests/myrequest.php

** Generate a seeder class**
<pre>
  php artisan make:seeder myseeder
</pre>
This command will generate new request file at database/seeds/myseeder.php

Few of the commands were available in the 4.2 version and few of them are introduced in the 5.1. Apart from this, you can get more info about command by following:

<pre>
php artisan help commandname
</pre>

Enjoy!!