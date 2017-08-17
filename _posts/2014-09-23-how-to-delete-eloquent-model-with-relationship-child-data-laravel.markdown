---
layout: post
date:   2014-09-23 11:15:12
title:  "How to delete Eloquent model with related relationship/child data"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

Eloquent, ORM of laravel is very powerful and we can use it for building model relationship. It handles most of CRUD operation with ease, even with relationship. Today, I'm going to discuss DELETE operation with relationship. How to delete related records when we delete any parent record? It's quite possible that we may have orphan records, if we don't delete child records, when deleting a parent record. To prevent, this situation, we can write code accordingly.

Before, we move to our example, there are few things, we need to know about Laravel Eloquent ORM.

* We can enable soft delete on our model. This will set deleted_at field in database and those records will not come when we fetch records with eloquent. There are some way to fetch those records, with use of <b>withTrashed() </b> method.

* We can force delete records in our model. This will delete records from database and we can't get this record any how in our application.


Let's try an example of laravel eloquent model.

{% highlight php %}
    <?php

        class User extends Eloquent
        {
            // this will enable soft delete on model.
            use SoftDeletingTrait;
            protected $dates = ['deleted_at'];

            public function photos()
            {
                return $this->has_many('Photo');
            }

            // override existing delete method.
            // invoke when we call $user->delete(), softdelete.
            public function delete()
            {
                // delete all associated photos
                $this->photos()->delete();

                // delete the user
                return parent::delete();
            }

            // override existing forceDelete method.
            // invoke when we call $user->forceDelete(), force delete
            public function forceDelete()
            {
                // use of withTrashed() to delete all records
                $this->photos()->withTrashed()->forceDelete();

                // delete the user
                return parent::forceDelete();
            }
    }
{% endhighlight %}

Above code will help to delete parent and it's child data gracefully.