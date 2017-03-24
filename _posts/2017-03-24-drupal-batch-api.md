---
title: Using the Drupal Batch API
# jekyll-seo-tag
description:  "Process large dataset with Drupal"
#image:        "http://placehold.it/400x200"
author:       "Emanuele"
tags:   drupal, batch, drush, drupal 7.x
---
Drupal [Batch API](https://www.drupal.org/docs/7/api/batch-api) give developer a complete infrastructure to create and process batch operations. 

Its functions provide form processing to be spreaded over many page requests avoiding them to be interrupted by PHP timeouts and at the same time allowing the user to receive feedback on the progress of the ongoing operations.

It was introduced with Drupal 6.x and is primarly designed to be used along the Form API workflow but you can also pair it (at your own risk) to a simple page callback or, that's the best part, with [Drush](https://github.com/drush-ops/drush) via a terminal command.

## Batching the Drush way

In my opinion this is the best way to process vast dataset without worries. You can tie process with a cron job and let Drupal do all the heavy lifting.

In the code example below you can see a very simple setup. We will prepare our data by dividing them in small chunks. Then we will define the atomic operations with which we era going to operate on then. Then it will be time to setup the batch processing and to define a function to handle the ending of it.

<script src="https://gist.github.com/eguicciardi/f4499b9892b5eeda869678861d381b03.js"></script>

With the module setup in that way we can open a termina window and type

```
drush myimport 100 2000
```

to tell our Drupal to start all the operations we defined on a set of nodes or whatever else we want.