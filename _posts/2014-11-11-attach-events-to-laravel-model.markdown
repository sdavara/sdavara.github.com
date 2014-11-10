---
layout: post
date:   2014-11-11 12:40:10
title:  "Attach events to Laravel Eloquent model"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

In my earlier post of laravel [eloquent](http://www.sdavara.com/delete-eloquent-model-laravel/), I told you that it's a very powerful ORM. It comes with many functionalities that we could imagine to have with any ORM.

One of the feature, we need is to have any way to hookup with model events.(i.e save, update etc.). Thankfully, It provides a set of methods to work with like of creating, created, updating, updated, saving, saved, deleting, deleted, restoring, restored.

These methods can be hooked up with model event and we can take a certain action. Below code will show, how to implement it. I've done that with help of boot method of the model.

<pre>
    class Account extends Eloquent {

    public static function boot()
    {
        parent::boot();

        // Setup event bindings...

        //In case of new object,
        //It's useful to track before a sucessful save in the database
        static::creating(function($account){
            // write any code.
        });

        //In case of new object,
        //It's useful to track after a sucessful save in the database
        static::created(function($account){
            // write any code.
        });

        //In case of existing object,
        //It's useful to track before a sucessful save in the database
        static::updating(function($account){
            // write any code.
        });

        //In case of existing object,
        //It's useful to track after a sucessful save in the database
        static::updated(function($account){
            // write any code.
        });

        //It's useful to track before a sucessful save in the database
        static::saving(function($account){
            // write any code.
        });

        //It's useful to track after a sucessful save in the database
        static::saved(function($account){
            // write any code.
        });

        //It's useful to track before successful delete
        static::deleting(function($account){
            // write any code.
        });

        //It's useful to track after successful delete
        static::deleted(function($account){
            // write any code.
        });

        //Incase of soft delete, 
        //It's useful to track before successfully restored.
        static::restoring(function($account){
            // write any code.
        });

        //Incase of soft delete, 
        //It's useful to track after successfully restored.
        static::restored(function($account){
            // write any code.
        });
    }

}
</pre>
