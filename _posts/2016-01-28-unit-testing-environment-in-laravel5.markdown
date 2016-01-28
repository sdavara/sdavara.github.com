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

<pre><code>

&lt;phpunit backupGlobals="false"
         backupStaticAttributes="false"
         bootstrap="bootstrap/autoload.php"
         colors="true"
         convertErrorsToExceptions="true"
         convertNoticesToExceptions="true"
         convertWarningsToExceptions="true"
         processIsolation="false"
         stopOnFailure="false" &gt;

    // we can define as many testsuite as we want.
    &lt;testsuites&gt;
        &lt;testsuite name="Application Test Suite"&gt;
            &lt;directory&gt;./tests/&lt;/directory&gt;
        &lt;/testsuite&gt;
        &lt;testsuite name="small"&gt;
            &lt;directory&gt;./tests/small&lt;/directory&gt;
        &lt;/testsuite&gt;
        &lt;testsuite name="medium"&gt;
            &lt;directory&gt;./tests/medium&lt;/directory&gt;
        &lt;/testsuite&gt;
        &lt;testsuite name="large"&gt;
            &lt;directory&gt;./tests/large&lt;/directory&gt;
        &lt;/testsuite&gt;
    &lt;/testsuites&gt;
    &lt;filter&gt;
        &lt;whitelist&gt;
            &lt;directory suffix=".php"&gt;app/&lt;/directory&gt;
        &lt;/whitelist&gt;
    &lt;/filter&gt;

    // I'd like to log my test results to tap format.
    &lt;logging&gt;
      &lt;log type="tap" target="results.tap"/&gt;
    &lt;/logging&gt;

    // This is my testing environment variables.
    &lt;php&gt;
       &lt;env name="APP_ENV" value="testing"/&gt;
       &lt;env name="DB_DATABASE" value=":memory:"/&gt;
       &lt;env name="DB_CONNECTION" value="sqlite"/&gt;
       &lt;env name="DB_DEFAULT_CONNECTION" value="sqlite"/&gt;
    &lt;/php&gt;
&lt;/phpunit&gt;

</code></pre>

You may have noticed that I've listed few environment variables in 'php' section. The aplication will try to find all environment variables in this file, if they don't find, it will try to get from .env file of the application. For more configuration options, you can visit unit test [documents](https://phpunit.de/documentation.html).
