---
layout: post
title: CSS Stacking Context
description: A description of z-index and how stacking context is formed
comments: true
category: programming
---

In this short post, I'm going to talk about the `z-index` property in CSS and how the stacking context is formed.

# The Stacking Context

According to MDN, the stacking context is the three-dimensional conceptualization of HTML along an imaginary z-axis. What that means is that when elements are given a z-index or are declared as a specific element (more on that later), a stacking context is formed along with a hierarchy on the web page.

## The z-index

Adding z-index to elements forces them to render in a specific order. Elements that are formed as the root, or positioned as fixed, relative, or absolute also affect the stacking context and the z-index.

## Independency

Stacking contexts can be contained in other stacking contexts; child stacking contexts only have meaning to its parents.
