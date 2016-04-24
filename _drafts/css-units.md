---
layout: post
title: CSS Lengths - px vs em vs percentages?
description: An overview on CSS units and their usefulness
comments: true
category: programming
---

CSS Lengths come in all different shapes and sizes. They all derive their units of measurement from different sources and it can be difficult to know when to use which one for your project. This article is an broad overview of  CSS Lengths and tips on when to use them.

# Relative vs. Absolute

CSS Units come in two flavors: Absolute and Relative. Absolute units include inches, centimeters, millimeters, points, picas, and, of course, pixels. They meet these criteria:

  * These units are self-regulating
  * These units are based off of real-world measurements

Relative units are much different and include percentages (%), em's, rem's, ex's, ch's, vmax, and vmin. These units are base their units off of one or more of these three criteria:

  * Units are based off of parents' own dimensions
  * Units are based off currently declared font-attributes
  * Units are based off viewport dimensions

As you can probably guess, relative lengths derive their units of measurement
from places already on the site or in the code. Let's take a closer look...

# Relative Units

## Percentages

Aside from pixels, percentages are units commonly seen in stylesheets and tend to be used a lot for responsive design. Percentages base their units of measurement off their parent container. For example, if the parent element is 400px wide and the child element is 50% wide, then the child element will render 200px wide in the browser. This can be seen below:

(Gif: HTML/CSS files - div containing two child elements. Browser being scaled down and percentages taking effect)

The `.parent` div contains two `.child` elements that take up 50% of the parent's container. Scaling down the parent container causes the children elements to shrink as well.

(Insert: When to use percentages)

## Font-attribute based units (ex, ch, em, rem)

Font-attribute based units are commonly used with fonts, as the title implies. Some are uncommon, but all are relative units.

### > ex unit

The ex unit is a uncommon CSS unit. To put it succinctly, 1ex is equal to the visible height of the letter 'x' (Yes, the actual letter 'x'). The actual dimensions of the letter 'x' can change too depending on the font-size and font-family of 'x', which, in turn, would change the dimensions of the ex unit as well.

(Gif: HTML/CSS files - div assigned to ex's. Changing the font-size of 'x' to show the browser ex dimensions changing)

When the font-size and font-family of 'x' is changed the ch unit adjusts itself accordingly.

### > ch unit

The ch unit, like its sister length above, is another uncommon CSS unit. 1ch is equal to the *width* of the '0' character. A better way to grasp this is if you turn that little guy sideways and stack multiples of '0' on top of each other, you find yourself with a nifty ch ruler. Again, the dimensions of the ch unit will change depending on the font-size and font-family of the '0' character.

(Gif: HTML/CSS files - div assigned to ch's. Changing the font-size of '0' to show the browser ch dimensions changing)

When the font-size and font-family of '0' is changed the ch unit adjusts itself accordingly.

(Insert: When to use ex's and ch's)

### > em unit

The em unit is notorious for being popular and misunderstood at the same time. That's because, like percentages, its unit of measurement is based off the parents' dimensions. However, the difference is that its based off of its parents' font-size. This means that if the font-size of the parent container is 10px and the child container is assigned a size of 2em, the child will render at 20px in the browser.

(Gif: Of the above example)

 The em unit also cascades, meaning if you had a grandchild within that child element, and the grandchild was set at 2em, it would render at 40px (10px x 2em = 20px x 2em = 40px (...or something like that)).

(Gif: Of the above example)

(Insert: when to use em's)

### > rem unit

The rem unit is very similar to the em unit, however it derives its units from the *root* element's font-size (usually declared in the stylesheet) and is *not* cascading.

(Gif: of root element being assigned and rem being used)

(Insert: when to use rem's)

## Viewport Dimensions

The vw, vh, vmin, and vmax units divides the viewport up into 100 units. When the viewport shrinks or grows in size the elements assigned these units will respond to shrink or grow as well.

### > vw and vh units

The vw and vh units stand for view-width and view-height, respectively. If an element is assigned 50vw, it will render as 50 parts of the viewport width dimension. Likewise with the vh unit.

(Gif: of vw and vh being used)

(Insert: when to use vw and vh)

### > vmin and vmax units

The vmin and vmax units of length are a little bit trickier. They still get their units from the viewport, however, they respond only to the largest (or smallest, if vmin) of the two viewport dimensions (width or height) in that moment. In other words, setting an element to 50vmax will render as 50 parts of the viewport dimension that is the largest.

(Gif: of vmax in action)

When the largest dimension begins to scale down (width in this example), the element will respond accordingly. As you can see, the element ignores the height because it is the smallest viewport dimension, *until* it becomes larger than the width. These principles apply to vmin as well, just in reverse:

(Gif: of vmin in action)

Things can get very mind-bending if you assign element's widths to view-heights and vice versa:

(Gif: of above example)

(Insert: when to use vmax and vmin)

# Absolute Units

Now we head back to some familiar territory! Absolute lengths are... well, just that - absolute. They are self-regulating and are based on real-world measurements. These include inches, centimeters, millimeters, points, picas, and, of course, pixels.

(Image: Browser 'chart' of all absolute units)

(Insert: when to use absolute units)

### A Word About Pixels

The most common unit seen on the web. Most people find themselves thinking in pixels when determining the dimensions of an element because its the easiest. However, a thing to note is the difference between pixel-density of screen devices and screen-pixels.

Screens come in all shapes and size *densities*. Text can look huge on a low density monitor, only to shrink immensely when you open up the same site on an iPhone, despite the iPhone having a physically smaller screen. Browsers render the pixels dimensions you assign them in screen-pixels, not physical pixels. This allows for a bit more 'even-ness' throughout all the physical screens your site will come across.

# Conclusion

As we now know, CSS lengths fall into two categories -- relative and absolute. From here, you can determine which you use in your projects depending if the site is responsive it or not. Hopefully you can now answer the question in the title for yourself! Until next time!
