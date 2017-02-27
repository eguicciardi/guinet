---
title:        "Drupal Mail System Module"
# jekyll-seo-tag
description:  "Drupal HTML emails the way they should be"
#image:        "http://placehold.it/400x200"
author:       "Emanuele"
---

<p class="lead">Working everyday with Drupal and give support to webmarketing things one of the most hideous things about Drupal is managing and sending HTML emails.</p>

## Third party modules to the rescue

As almost always luckily there's no need to reinvent the wheel to make Drupal send emails the way they should be. My preferred solution is using two modules.
The first one is [Mail System](https://www.drupal.org/project/mailsystem) and it provides an administration UI to manage the mail backend used by the site. The second one is [HTML Mail](https://www.drupal.org/project/htmlmail) and it's great because it lets you theme email messages with templates like the theme's one.
Sometimes it's incredible how little it takes to make a designer happy!

## Now what?!

By installing **Mail System** by itself you won't notice anything but a new admin page with some options that let's you choose a *sending backend* for you transactional email. HTML Mail adds the power to define in your theme or your module a custom HTML template and design it like you'll do for a normal page:

1. **htmlmail.tpl.php** is the default template
2. **htmlmail--module_name--key.tpl.php** is custom one you can use in a specific module with a specific action

Installing HTML Mail in your system will add *HTMLMailSystem* in the *Mail System* option. By selecting it all the emails sent through the site will be wrapped in HTML.

## Taking it further

But what will happen if your designers want to theme all the emails but you want to send them via an external delivery system like [Mandrill](http://www.mandrill.com) or [Sendgrid](https://sendgrid.com)?
It should sound a little tricky but it's just few clicks away: install the module (thanks Drupal Community!) and then go back to the Mail System Module configurationa page.
Here just add a *New Class* and choose HTML Mail as the **format()** method and let's say SendgridMailSystem ad the **mail()** one.

From now on all the outbound email you want will be wrapped in HTML before being send via and external service.

## People who installed this modules also downloaded

HTML Emails are not easy. If you want to be almost sure to get them right on every device out there besides hard and long testing be sure to get this module called [Emogrifer](https://www.drupal.org/project/emogrifier).

It use the homonymous library to transfer all the CSS styles inline to permit the correct display by all the clients that do not support the use of externale resources.
