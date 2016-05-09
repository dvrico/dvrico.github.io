---
layout: post
title: Understanding .clearfix
description: A quick read on how clearfix works.
comments: true
category: programming
---

Have you ever seen this snippet of css and wondered what it did?

    .clearfix:before, .clearfix:after {
      content: " ";
      display: table;
    }

    .clearfix:after {
      clear: both;
    }

`.clearfix` is used to correct the behavior of floated elements that overflow out of its parent's container. `.clearfix` involves three main things: `float`, `clear`, and `table`.

# Floats: The Good, the Bad, and the Ugly

The float property specifies whether or not an element should wrap text around images. Its roots come from printing, where text flowed around <i>floated</i> images.

[ example of print with text wrapping around text ]

It's common to see whole entire layouts made entirely out of floats, because floating elements offers a lot of versatility despite the intent of its creation.

[img of float and non-float]

Floats can cause unseen trouble, though. If a floated element is taller than the element containing it, it will overflow outside of its container.

[img of float breaking out of container]

# Enter the `clear` property

The `clear` property is used to control the behavior of elements flowing around floating elements.

[ Example ]
[ Example 2 ]

# Enter `display: table`

The last ingredient of `.clearfix` is `display: table`. Unlike `display: block` or `display: inline-block`, `display: table` [insert ability and purpose].

[example]

# Putting it all together

Let's take a look at `.clearfix` again:

    .clearfix:before, .clearfix:after {
      content: " ";
      display: table;
    }

    .clearfix:after {
      clear: both;
    }

Now we can see this class first inserts empty content (but still content!) in the form of a table `:before` our parent element containing the floated element.

Second, it inserts the same thing after the parent element, thus containing the floated element in the parent by forcing the parent to generate a height other than 0 (Remember that parent `div`s generate a height that is equal to the content it contains. A floated element, does not contribute to this height, thus giving the parent a height of 0).

Finally, anything `:after` the parent element is cleared, giving us a little more control over the float.

That's all there is to it! Now you can go ahead and use it in your own code!
