#Project4 - Web Optimization

![](http://progressed.io/bar/90?title=Progress)


##Project Objective:

Optimize a provided website with a number of optimization- and performance-related issues so that it achieves a target PageSpeed score and runs at 60 frames per second.

##Running Instruction:

1. Go to Google PageSpeed Insights, input 'jonathanzhong.github.io', then you will get the analysis of the page.
2. Scroll down to the protfolio page, click on the 'Yonglin's Pizzeria', you will be nagvigated to the pizza page, open the dev too to the console, you will get the rendering speed.


##Approaches to Optimization Web Performance:
- index.html
  * Using inline CSS to avoid default CSS rendering blocking
  * Minify style.css file, utilize media query to 'print.css' to a*void needless download
  * Minify JavaScript file, moving the script section to bottom of HTML
  * @import url(http://fonts.googleapis.com/css?family=Open+Sans);
- main.js
  * First stage optimization: move the below code outside the for loop
`var elem = document.createElement('img')
`
  * Second Stage Optimization: reducing the scripting time by using `document.getElementByClassName()` instead of `document.querySelectorAll()`, which is the slowest way to access DOM; reducing layout time by `transform: translateX()`
  * Third Stage Optimization: reducing painting time by adding the following code to`views\css\style.css`
```
.randomPizzaContainer {
  float: left;
  display: flex;
  backface-visibility: hidden
  transform: translateZ(0);
  transform: translate3d(0,0,0);

}
```

##Result:
- Achieving 94/100 for mobile and 92/100 for laptop from pagespeed

![pageSpeed-mobile](pageSpeed-mobile0.png)
![pageSpeed-laptop](pageSpeed-laptop0.png)
- Achieving 60FPS

![60fps](60fps.png)

##Useful Reference:
  https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById
  - Comments in JS files:
  http://usejsdoc.org
  https://jashkenas.github.io/docco/
  http://www.hongkiat.com/blog/source-code-comment-styling-tips/
  - Documentation in README:
  http://stackoverflow.com/questions/2304863/how-to-write-a-good-readme
  https://robots.thoughtbot.com/how-to-write-a-great-readme
  http://www.wikihow.com/Write-a-Read-Me
  http://docs.writethedocs.org/writing/beginners-guide-to-docs
  - Built Toos(Gulp & Grunt):
  Gulp:
  http://yeoman.io/blog/performance-optimization.html
  https://parall.ax/blog/view/3003/grunt-vs-gulp-js-a-comparison
  https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md
  https://markgoodyear.com/2014/01/getting-started-with-gulp/
  http://alistapart.com/blog/post/getting-started-with-gulp
  https://isimmons.github.io
  Grunt:
  http://gruntjs.com/getting-started
  https://scotch.io/tutorials/a-simple-guide-to-getting-started-with-grunt
  http://24ways.org/2013/grunt-is-not-weird-and-hard/
  - CSS:
  https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery
  https://developers.google.com/speed/docs/insights/InlineCSS
  https://developers.google.com/speed/pagespeed/module/filter-css-inline-google-fonts
  https://developer.mozilla.org/en/docs/Web/HTML/Element/link
  - Images:
  https://developers.google.com/speed/docs/insights/OptimizeImages
  https://kraken.io
  https://compressor.io
  http://www.giftofspeed.com/optimize-images/



