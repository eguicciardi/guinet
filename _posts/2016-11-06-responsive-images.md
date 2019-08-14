---
title: 'Responsive Images'
date: '14:10 14-10-2016'
headline: 'One size does not fit all'
taxonomy:
    tag:
        - responsive images
        - mobile first
visible: true

---

What I consider the main need of an era where we are starting to see and use the web everywhere is a way to serve what we need, to the device we use, in the best way for that device without any over engineered server side solution.

## SRCSET and SIZES

Among other things the HTML 5.1 specification introduces two new attributes to the img element: srcset and sizes.

The former let us declare a set of images sources that the browser will serve according to a series of parameters we define trough descriptors. The x indicates the pixel density, the w the width of the image. The sizes attribute provides the browser with some context on the size of the image elements to be displayed.

So, let’s write some code:

```html
<img src=“one.jpg” alt=“” />
```

and

```html
<img srcset=“two.jpg” src=“one.jpg” alt=“” />
```

The first code is the basic img syntax, the second one instead is a very useless use of srcset. If the browser supports it it will only load the image specified in the srcset.

In order to make it someway useful let’s use it to provide a retina quality image

```html
<img srcset=“two.jpg 2x” src=“one.jpg” alt=“” />
```

To raise the bar even more we can use the w descriptor:

```html
<img srcset=“two-3200.jpg 3200w, three-1600.jpg 1600w” src=“one.jpg” alt=“” />
```

In this example we have chosen to use different images for different width. In this way we can have a taylor made image for every situation.

Let’s take it a little further on introducing the sizes attribute:

```html
<img srcset=“img-480.jpg 480w,

             img-640.jpg 640w,

             img-960.jpg 960w,

             img-1280.jpg 1280w"

     sizes="(max-width: 400px) 100vw,

            (max-width: 960px) 75vw,

            640px"

     src=“img-640.jpg" alt="">
```

The sizes attribute specifies the width of the image depending the media condition. The browser will match srcset set and sizes set to get the best image for a given condition.

## PICTURE

In my opinion srcset is a great solution for a difficult problem. Anyway what I’m really waiting for is the picture element.

its syntax is very similar to the video and audio elements.

You start with:

```html
<picture>

     <img src=“one.jpg” alt=“” />

</picture>
```

But the real power comes when you insert the source element:

```html
<picture>
     <media="orientation:landscape" srcset="two.jpg" />
     <img src=“one.jpg” alt=“” />
</picture>
```

As you can see with the picture element you can have a different image for every layout.

## BUT IN THE REAL WORLD?

As of today picture is supported by all the latest versions of all browser except Safari and Internet Explore. srcset is fully supported by Chrome, Firefox and Opera and partially by Safari ( > 8.0) and Explorer Edge. In these two browser you can use the x descriptor to switch resolutions but not the w one.

While waiting for the standard to be fully implemented by all major browsers there are of course some polyfills to fill the gap. The one I prefer is respimage by Alexander Farkas.
