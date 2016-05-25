---
layout: post
title: JS Nuggets - Difference between `call()` and `apply()`
description: A quick explanation about the difference between `.call` and `.apply`
comments: true
category: programming
---

A first glance, Javascript's built in `call()` and `apply()` methods can look similar and often confuse programmers. But they're actually pretty simple and an indispensable tool once you know how to use them. This short post aims to clear up any confusion.

# The Similarities

To put it succinctly, `call()` and `apply()` can indirectly invoke Javascript functions.

Javascript functions are objects, and because of this, they have methods like any other Javascript object. Functions have a few built in methods including `call()` and `apply()`.

The first argument to `call()` and `apply()` is the object on which the function is to be invoked. This object becomes the value of the `this` pointer in this context. To make this clearer, look at the example below:

    var color = 'red';
    var foo = { color: 'green' };

    function goblin() {
      console.log("This goblin is " + this.color);
    }

    goblin()              // "This goblin is red"

    goblin.call(foo)      // "This goblin is green"

    goblin.apply(foo)     // "This goblin is green"

The invocation of `goblin()` prints out "The goblin is red" because the `this` keyword references the <i>global</i> object. And because `var color` is a global variable, `this.color` references this variable.

The `call()` and `apply()` methods take `foo` as its first argument, thus making it become the value of the `this` keyword. As a result `this.color` will now refer to `foo`'s `color` property instead of the global variable `color`.

To sum up, `call()` and `apply()` are methods we can use to assign the `this` pointer for the duration of a method invocation.

# The Differences

`call()` and `apply()` differ on how they handle function arguments.

After the first argument, `call()` takes any other further arguments and passes them to the function like so:

    var foo = { mood: 'hungry' };

    function goblin( message ) {
      console.log( message + this.mood );
    }

    goblin.call(foo, 'The small goblin is ')  // The small goblin is hungry



`apply()` on the other hand, takes arguments to be passed to the function as an <i>array</i> :

    var foo { mood: 'sick', color: 'yellow' };

    function goblin( message1, message2 ) {
      console.log( message1 + this.mood + message2 + this.color );
    }

    goblin.apply(foo, ['The ', ' goblin is really '] )
      // "The sick goblin is really yellow"

And that's all there is to it! Remember the little mnemonic 'An A for Array and C for comma' when you forget which one is which. For a more in-depth info and better examples, check out [MDN's](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) [page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call).
