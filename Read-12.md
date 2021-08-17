# Reading

## [Chart.js API](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

This is my first experience importing anything! I know there are lots of different things to import in Python, Javascript, and other languages. 

```Javascript
   <title>Chart.js demo</title>
        <!-- import plugin script -->
        <script src='Chart.min.js'></script>
```

This is what we use to import chart.js

The stack here seems pretty straightforward. Use ```<canvas>``` to set up some basic elements like **id, width, and height**

Then we get the data from what looks like a complex object by using a method we know (getElementById) and a method I don't know (getContext)

## [Chart.js docs:](https://www.chartjs.org/docs/latest/)

Key Points Below

>It's recommended to give the chart its own container for responsiveness.

#### Data Normalization

>Chart.js is fastest if you provide data with indices that are unique, sorted, and consistent across datasets and provide the normalized: true option to let Chart.js know that you have done so. Even without this option, it can sometimes still be faster to provide sorted data

## Canvas API

### [Basic usage](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)

```<canvas>``` does not have src or alt attributes, just width and height. This will auto set to 300px wide and 150px height.

> Note: If your renderings seem distorted, try specifying your width and height attributes explicitly in the ```<canvas>``` attributes, and not using CSS.

Good practice to specify an ID with canvas. 

### [Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)

Looks like canvas can only create rectangles and paths, however the paths can be used to make a bunch of different shapes by specifying a pen "lift" by using the moveTo function

### [Applying styles and colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

Two main methods for using color in canvas.

1. fillStyle: fills a shape with a color
2. strokeStyle: outlines a shape with a color

### [Drawing text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

Similar to above, we have two methods for creating text

1. fillText: "fills" text at a given position
2. strokeText: "strokes" text at a given position

Both take a *text*, *x*, and *y* paramater.
