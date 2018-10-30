---
layout: post
date:   2018-10-30 13:34:10
title:  "Consuming custom format JSON SQS with Laravel"
status: publish
categories:
- Article
- Programming
- Laravel
- PHP
tags:
- Article
- Programming
- Laravel
- PHP
---

Laravel provides many ways to scale our application. Queuing up time consuming task is one the best way. Laravel has the best integration with AWS SQS, we can just queue up our job and everything will be taken care by following laravel's configuraiton. Laravel has very nice documentation on [queue](https://laravel.com/docs/5.6/queues)

We don't face any issue in queuing and process from laravel application. But, when there is a need to process queue which contains custom JSON format data(other than laravel format), it doesn't work out of the box as described in laravel's documentation. We can either create one command and read queue or use some package to read custom format JSON queue.

Most of the time AWS SQS queue is used in any application. We have a package to work with custom JSON format SQS data.

Package name : *[dusterio/laravel-plain-sqs](https://packagist.org/packages/dusterio/laravel-plain-sqs)* 

As per documentation of package, we have to change the queue driver in our environment file. But, it will stop the default behaviour of laravel queue process. So, there is a solution for it. We will need to add the following lines in our config/queue.php file:

{% highlight php %}
 'sqs-plain' => [
            'driver' => 'sqs-plain',
            'key'    => env('SQS_KEY', ''),
            'secret' => env('SQS_SECRET', ''),
            'prefix' => env('SQS_PREFIX', ''),
            'queue'  => env('SQS_QUEUE', ''),
            'region' => env('SQS_REGION', ''),
        ],
{% endhighlight %}

We will require to set those variables in our `.env` file. Along with that we will also need to implement `sqs-plain.php` default handler class.

{% highlight php %}
return [
    'handlers' => [
        'base-integrations-updates' => App\Jobs\HandlerJob::class,
    ],

    'default-handler' => App\Jobs\HandlerJob::class
];
{% endhighlight %}

Now, we can process our custom JSON format SQS with below commanad:
{% highlight php %}
php artisan queue:work sqs-plain --queue=https://sqs.us-west-2.amazonaws.com/userid/queuename"
{% endhighlight %}

To handle normal laravel format JSON SQS, we can use below command:
{% highlight php %}
php artisan queue:work sqs --queue=https://sqs.us-west-2.amazonaws.com/userid/queuename"
{% endhighlight %}

Let me know, if you have found any other way for working with custom format JSON SQS. 
