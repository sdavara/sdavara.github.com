---
layout: post
date:   2015-01-28 17:30:10
title:  "Update application directory in homestead VM"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

Laravel provides a great vagrant package "Homestead". Its a great tool for running application locally across the different machines without worrying about software requirement. 

But recently, I came across a problem of updating my application directory in a default configuration and my site stopped to work. I know that could have been solved with the help of 'vagrant --provision', but I'd like to explore other options.

Finally, I found that I need to update nginx sites inside my Homestead box. 

I have listed below steps for updating your application folder.

Step 1 : Logon to homestead machine 

<pre>
    homestead ssh
</pre>

Step 2 : Navigate to ngnix available sites location

<pre>
    cd /etc/nginx/sites-available/
</pre>

Step 3 : Edit your application

<pre>
    // you need to edit your application 
    vi homestead.app
</pre>

Step 4 : Update your root location

You will see 'root' variable in your application configuration, you'll need to update it.

Please note that, this location should be your VM location.

Step 5 : Important!! Restart nginx

<pre>
    sudo /etc/init.d/nginx restart
</pre>

I hope you enjoyed this.