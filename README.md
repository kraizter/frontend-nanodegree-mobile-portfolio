## Website Performance Optimization portfolio project

####Part 1: Optimize PageSpeed Insights score for index.html
- https://kraizter.github.io/frontend-nanodegree-mobile-portfolio/

### index.html
* disable open-sans font which is not used (really defect alot in loading)
* put `media print` on print.css so it not loaded on screen to increase performance
* gzip the style.css file and inline it on header, (suggested by google page speed), this decrease page load latency. 
* resize the image, and make the thumbnail pizza (that huge 2mb, i turn into 80kb).

####Part 2: Optimize Frames per Second in pizza.html

### views/js/main.js
* the problem was the selector keep calling too much inside the loop .so to make efficiency call, pull out the selector. they only instantiated once, not calling in loop as many pizza will calling. every .randomPizzaContainer selector called the dom will re-initiated and browser re-render it, thats why its unefficient to put inside the loop

changing pizza position :
* this actually same as problem above, inside for iteration updatePositions, the function keep asking the body position from global function/jquery function to change body position on each loop so its defect on rendering the solution were same, pull out every variable that keeping reinitiated defect performance make function only update position when triggered
* also decrease the randompizza object from 300 to 30, the more to load the fps might be dropping alot.

### High reference on getting solution :
* http://jankfree.org/
* https://discussions.udacity.com/t/help-with-pizza-images-and-how-to-find-fps/181265
* https://discussions.udacity.com/t/i-cant-get-up-to-60-fps-on-the-pizza-scroll-please-help/182048
* http://blog.teamtreehouse.com/create-smoother-animations-transitions-browser

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
