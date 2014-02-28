Knockout.LazyLoad
===================

Knockout.LazyLoad is a plugin for [Knockout.js](http://knockoutjs.com) that provides support for lazy loading of content.  Currently, it supports lazy loading of images.  Set the ```src``` attribute of your images to whatever loading image you wish to display.  Each image ```src``` attribute will be replaced with the bound data once it is visible in the viewport.

It's still fairly fresh, and you'll hit some strange behavior if your images don't have a defined size since I'm not currently waiting for the image load to complete (hopefully fixed soon).  However, it should support lazy load scrolling vertically as well as horizontally.

*Pull requests are welcome!*

Usage Example:
--------------
###Html:
``` html
<ul data-bind="foreach: images">
  <li><img src="mySpinner.gif" data-bind="lazyload: $data" /></li>
</ul>

<script src="knockout.js"></script>
<script src="ko.lazyload.js"></script>
```
###Script:
``` javascript
var viewModel = {
  images: ko.observableArray([
    'image1.png'),
    'image2.png'),
    'image3.png')
  ])
};

ko.applyBindings(viewModel);
```
