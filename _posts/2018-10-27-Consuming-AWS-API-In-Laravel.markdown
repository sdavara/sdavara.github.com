---
layout: post
date:   2018-10-27 12:00:10
title:  "How to consume AWS API in laravel"
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

Amazon web services provide many services such as SQS, SNS, S3 which can be very useful for managing application nicely. Many applications rely on those services and also we can have our own API/contract on top of AWS services. For that matter, we require to consume the AWS API in our application.

Thanks to the vibrant community of PHP and Laravel, we have a package for consuming AWS API.

Package name : *[aws/aws-sdk-php-laravel](https://packagist.org/packages/aws/aws-sdk-php-laravel)* 

Read me contains everything about how to setup in laravel applicaiton. You should also refer [aws/aws-sdk-php](https://packagist.org/packages/aws/aws-sdk-php) package specifically built for consuming AWS API in php. *[aws/aws-sdk-php-laravel](https://packagist.org/packages/aws/aws-sdk-php-laravel)* written on top of *[aws/aws-sdk-php](https://packagist.org/packages/aws/aws-sdk-php)*, you can write your own package too.

You will require the following details to get started, which can be created by system admin who is managing your AWS infrastructure.
* AWS_SECRET_ACCESS_KEY 
* AWS_SECRET_ACCESS_KEY 
* AWS_REGION (i.e us-east-1, us-west-1 etc) 
