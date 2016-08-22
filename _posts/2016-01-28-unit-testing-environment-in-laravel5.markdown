---
layout: post
date:   2016-01-28 17:30:10
title:  "Unit Testing environment set in laravel 5.1"
status: publish
categories:
- Laravel
- Programming
- Testing
tags:
- Laravel
- Programming
- Testing
---

Laravel comes with many good features. One of the best feature, I liked a lot is 'testing' inside a framework. We don't need to add any new package. It comes out of the box. There are few points for a good testing likes of having a separate database, run migrations and impersonate development environment etc. Laravel allows you to cover all those points in your testcases.

From laravel 5, it introduces .env file. That is a plain text file with the key value pair. We can have different .env file inside an application for the different environment. When we run testcases, laravel runs it under 'testing' environment. To alter testing environment variables, we can edit 'phpunit.xml' file in the root folder of our application.


Below is my 'phpunit.xml' file.

{% highlight xml %}
<phpunit backupGlobals="false"
         backupStaticAttributes="false"
         bootstrap="bootstrap/autoload.php"
         colors="true"
         convertErrorsToExceptions="true"
         convertNoticesToExceptions="true"
         convertWarningsToExceptions="true"
         processIsolation="false"
         stopOnFailure="false" >

    // we can define as many testsuite as we want.
    <testsuites>
        <testsuite name="Application Test Suite">
            <directory>./tests/</directory>
        </testsuite>
        <testsuite name="small">
            <directory>./tests/small</directory>
        </testsuite>
        <testsuite name="medium">
            <directory>./tests/medium</directory>
        </testsuite>
        <testsuite name="large">
            <directory>./tests/large</directory>
        </testsuite>
    </testsuites>
    <filter>
        <whitelist>
            <directory suffix=".php">app/</directory>
        </whitelist>
    </filter>

    // I'd like to log my test results to tap format.
    <logging>
      <log type="tap" target="results.tap"/>
    </logging>

    // This is my testing environment variables.
    <php>
       <env name="APP_ENV" value="testing"/>
       <env name="DB_DATABASE" value=":memory:"/>
       <env name="DB_CONNECTION" value="sqlite"/>
       <env name="DB_DEFAULT_CONNECTION" value="sqlite"/>
    </php>
</phpunit>
{% endhighlight %}

You may have noticed that I've listed few environment variables in 'php' section. The aplication will try to find all environment variables in this file, if they don't find, it will try to get from .env file of the application. For more configuration options, you can visit unit test [documents](https://phpunit.de/documentation.html).
