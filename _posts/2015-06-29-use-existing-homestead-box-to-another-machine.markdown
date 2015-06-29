---
layout: post
date:   2015-06-29 19:0:10
title:  "Use Existing homestead box into another machine"
status: publish
categories:
- Laravel
- Programming
tags:
- Laravel
- Programming
---

Laravel homestead box is an easy to use VM for any of the PHP projects. Most of the time, it works out of the box and we need to configure a little bit of it. The recent update of the homestead is a wrapper on the vagrant box and you can see a vagrant file located in Homestead folder. Earlier, we used 'homestead' command, underlying it was using the same vagrant boxes, but it was not the clear and clean way.

Depends on the project requirement, we may modify an existing copy of homestead box. It's not a good practice to repeat the same steps again and again when we try to setup a new machine. Thanks to 'package' of vagrant box, we can use existing modified homestead in a new machine.

Let me walk you through the procedure of use existing box into another machine:

**Step 1 : Go to the Homestead folder (usually, that's located in to home folder)**

<pre>
    cd ~/Homestead
</pre>

**Step 2 : Prepare your package, a new box**

<pre>
    vagrant package --output mynew.box
</pre>

**Step 3 : Copy this mynew.box to a new machine and import this as a laravel/homestead box**
(If you wish to manage your projects via homestead configuration.)

<pre>
    vagrant box add homestead/laravel mynew.box
</pre>

Now, you don't need to download a homestead VM from a lower bandwidth server. You also don't need to modify your VM as per your need. You are ready to rock with existing box configuration.

Happy virtualization :)
