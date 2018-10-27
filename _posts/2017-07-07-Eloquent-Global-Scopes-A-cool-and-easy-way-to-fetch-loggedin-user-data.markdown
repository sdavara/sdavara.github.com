---
layout: post
date:   2017-07-07 12:15:10
title:  "Eloquent Global Scopes: A cool and easy way to fetch loggedin user data"
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

Laravel eloquent ORM has come a long way since it's been added in laravel. Today, I'm going to discuss a topic around laravel Eloquent ORM, that is "Global Scopes". Anyone working with laravel must be aware about "scope" keyword in laravel model. It extends query in our model. With the introduction of "Global Scopes", we can attach scope at model level with all the queries executed. That is very similar to that of deleted records, by default we don't get any soft deleted records from the model. We have to explicitly specify.

There are many SAAS built on Laravel. In most of the SAAS, it's very common to work with loggedin user or organization data. For that we have to write query accordingly. Here's the best place where we can take advantage of "Global Scope". There is no particular code folder to place "Global Scopes", I've placed in "App" folder as per the documentation.

Let's take an example of UserScope, where we would like to define a query with loggedin user id. I've assumed that we use "Auth" provider and use "user_id" as a foreign key to user's id.

We can define our "UserScope" as below:

{% highlight php %}
<?php

namespace App\Scopes;

use Illuminate\Database\Eloquent\Scope;
use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\Builder;
use Auth;

class UserScope implements Scope
{
    /**
     * Apply the scope to a given Eloquent query builder.
     *
     * @param  \Illuminate\Database\Eloquent\Builder  $builder
     * @param  \Illuminate\Database\Eloquent\Model  $model
     * @return void
     */
    public function apply(Builder $builder, Model $model)
    {
        $builder->where('user_id', '>', Auth::user()->id);
    }
}
{% endhighlight %}

We can apply UserScope to any of our models like of Product, Invoice etc. In below example, I'm going to use a Product model:

{% highlight php %}
<?php

namespace App;

use App\Scopes\UserScope;
use Illuminate\Database\Eloquent\Model;

class Product extends Model
{
    /**
     * The "booting" method of the model.
     *
     * @return void
     */
    protected static function boot()
    {
        parent::boot();

        static::addGlobalScope(new UserScope);
    }
}
{% endhighlight %}

Now, when we query Product, it will only fetch data of the loggedin user. In query, I assume loggedin user id is "10"

{% highlight sql %}

select * from `products` where `user_id` = 10

{% endhighlight %}

We can query Product without UserScope as below:

{% highlight php %}

Product::withoutGlobalScope(UserScope::class)->get();

{% endhighlight %}

An ideal way of using "Local Scope" is on multiple model via abstract class. We create an abstract class implement "Local Scope" there all other classes derived from, can use it. This will be the huge benefits when writing a SAAS.

Happy coding!!