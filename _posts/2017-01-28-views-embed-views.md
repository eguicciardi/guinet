---
title: "Drupal views_embed_view()"
description: 'Views are great, period'
taxonomy:
    tag:
        - drupal
        - views
visible: true
---

Views is the module responsible for the 80% of Drupal greatness. Let’s be fair, if you haven’t used it once probably you have never made a Drupal worth site.

But don’t let’s waste time chattering! The first function of the function Thursday is the excellent:



<pre><code>views_embed_views()</code></pre>



As the name may suggests this function is used to embed a views programmatically in your template. I find myself using it in almost every project.



It accepts as parameters the machine name of the view and optionally the display id and an array of arguments. Such arguments are used as the contextual filters of the invoked view. It’ really important to remember to order the arguments in the same way as you set it the administrations page otherwise it’s won’t work.



Here is a real use case:



<pre><code>print views_embed_view('blog_posts','block_1', $node->nid);</code></pre>


##References


<a href=“https://api.drupal.org/api/views/views.module/function/views_embed_view/7” target=“_blank”>views_embed_views on Drupal API</a>
