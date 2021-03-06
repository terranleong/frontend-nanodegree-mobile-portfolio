## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.

### Getting started

#### Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

#### Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

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



#### Optimisation:
#### 1. Measurement:
1) Google PageSpeed Insights

    1. Before Score:
        Mobile  :   85
        Desktop :   84

    2. After Score:
        Mobile  :   99
        Desktop :   100

2) GTmetrix
    1. Before:
        1. PageSpeed Score      =   28%
        2. YSlow Score Score    =   79%
        3. Fully Loaded Time    =   13.2s
        4. Total Page Size      =   2320 KB
        5. Request              =   13

    2. After:
        1. PageSpeed Score      =   96%
        2. YSlow Score Score    =   92%
        3. Fully Loaded Time    =   1.8s
        4. Total Page Size      =   24.4 KB
        5. Request              =   11

3) Time to build CSSOM
    1. Before:
        40.4 ms

    2. After:
        3.6 ms

#### 2. Optimisation Detail:
1) Minimize bytes
    1) Minify file (CSS, JS) -done
    2) GZip compressing-done
    3) Minimise picture by resizing/compressing/converting 
        1) resize pizzeria to 100px -done
        2) convert all pictures format to webp format for smaller size -done

2) Reduce critical resources
    1) Avoid render blocking CSS (e.g. use media queries for css and asyc/defer for js)
    - move smartphone css from style.css to another css file (portrait.min.css) -done
    - add media="print" on print.min.css- done
    - add media="(orientation: portrait)" on portrait.min.css -done
    - no request web font -done
    - import webfont instead of link -used local machine font instead
    - move js to different file and async -no action taken
    - moving scripts down the html page -no action taken, no obvious improvement for me
    - defer js -used async on perfmatters instead
    2) Inline CSS -not viable, update would be ineeficient in future
    3) Inline JS -not viable, update would be ineeficient in future

3) Shorten CRP length
    1) HTTP Caching -done

### 3. Bug Fixed:
1. Adding this line <!-- <link rel="shortcut icon" href="#"> --> to head to resolve 'favicon.ico, 404 File not found' error

### 4. Performance Checking:
1. W3C check                    - done
2. gtmetrix.com                 - done
3. http-compression-test        - done
4. Google PageSpeed Insights    - done


