Goal of article: To briefly explain the basics of css positioning and demystify
  the topic.

Keypoints
=========
+ If CSS positioning is the pb, then CSS directions is the jam. These two are
  directly related to each other
+ The four directions: top, left, right, bottom. Pretty self explanatory.
+ First CSS position: static
    + The default state of most elements
    + CSS directions do not apply to this position
+ Second CSS position: relative
    + This adjusts the position of the element *relative* to its original
      position.
    + The original position is still maintained by the DOM (shown usually by
      a missing gap where the element should be).
    + This lays out the element as if it weren't position (pops it out of the
      '2D' DOM space).
+ Third CSS position: absolute
    + This adjusts the position of the element relative to its closest *declared*
      positioned ancestor. Ancestors with the default static position will be
      ignored.
    + The original position of the element is not maintained, so no gap will be
      shown.
+ Fourth CSS position: fixed
    + The element is positioned relative to the screen's viewport and does not
      move when the user scrolls. Is is really like popping out the element out of
      its '2D' space and letting it hover over top of the DOM.
    + No space is left for the original position of the element.
+ Conclusion: Understanding the basics of css positioning can help you start
  to understand how elements are laid out and can help you demystify other CSS
  code you see on the web. Some neat tricks can be done with these powerful tools.
  
