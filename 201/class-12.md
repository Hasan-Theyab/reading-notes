# Chart.js

Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. They’re easier to look at and convey data quickly, but they’re not always easy to create.

A great way to get started with charts is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.

The first thing we need to do is download Chart.js. Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script:

### Drawing a line chart

To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart. So add this to the body of our HTML page.

### Drawing a pie chart

Our line chart is complete, so let’s move on to our pie chart. First, we need the canvas element
Next, we need to get the context and to instantiate the chart.

You’ll notice that this time, we are going to supply some options to the chart.

Next we need to create the data. This data is a little different to the line chart because the pie chart is simpler, we just need to supply a value and a color for each section.

### Drawing a bar chart

Finally, let’s add  a bar chart to our page. Happily the syntax for the bar chart is very similar to the line chart we’ve already added. First, we add the canvas element.

Next, we retrieve the element and create the graph.

And finally, we add in the bar chart’s data.

### Conclusion

The great things about Chart.js are that it’s simple to use and really very flexible. Plus, once you’ve mastered the basics here, you’ll discover that there are tons of options listed in the documentation.

# Canvas API

### Basic usage of canvas

### The canvas element

At first sight a canvas looks like the img element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the canvas element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. The element can be sized arbitrarily by CSS, but during rendering the image is scaled to fit its layout size: if the CSS sizing doesn't respect the ratio of the initial canvas, it will appear distorted.

The id attribute isn't specific to the canvas element but is one of the global HTML attributes which can be applied to any HTML element (like class for instance). It is always a good idea to supply an id because this makes it much easier to identify it in a script.

The canvas element can be styled just like any normal image (margin, border, background…). These rules, however, don't affect the actual drawing on the canvas. We'll see how this is done in a dedicated chapter of this tutorial. When no styling rules are applied to the canvas it will initially be fully transparent.

### Fallback content

The canvas element differs from an img tag in that, like for video, audio, or picture elements, it is easy to define some fallback content, to be displayed in older browsers not supporting it, like versions of Internet Explorer earlier than version 9 or textual browsers. You should always provide fallback content to be displayed by those browsers.

Providing fallback content is very straightforward: just insert the alternate content inside the canvas element. Browsers that don't support canvas will ignore the container and render the fallback content inside it. Browsers that do support canvas will ignore the content inside the container, and just render the canvas normally.

elling the user to use a different browser that supports canvas does not help users who can't read the canvas at all, for example. Providing a useful fallback text or sub DOM helps to make the canvas more accessible.

### Required /canvas tag

As a consequence of the way fallback is provided, unlike the img element, the canvas element requires the closing tag (/canvas). If this tag is not present, the rest of the document would be considered the fallback content and wouldn't be displayed.

If fallback content is not needed, a simple canvas id="foo" ...(/canvas) is fully compatible with all browsers that support canvas at all.

### The rendering context

The canvas element creates a fixed-size drawing surface that exposes one or more **rendering contexts**, which are used to create and manipulate the content shown. In this tutorial, we focus on the 2D rendering context. Other contexts may provide different types of rendering; for example, WebGL uses a 3D context based on OpenGL ES.

The canvas is initially blank. To display something, a script first needs to access the rendering context and draw on it. The (canvas) element has a method called **getContext()**, used to obtain the rendering context and its drawing functions. getContext() takes one parameter, the type of context.

The first line in the script retrieves the node in the DOM representing the (canvas) element by calling the document.getElementById() method. Once you have the element node, you can access the drawing context using its **getContext()** method.

### Drawing shapes with canvas

Now that we have set up our canvas environment, we can get into the details of how to draw on the canvas. By the end of this article, you will have learned how to draw rectangles, triangles, lines, arcs and curves, providing familiarity with some of the basic shapes. Working with paths is essential when drawing objects onto the canvas and we will see how that can be done.

### The grid

Before we can start drawing, we need to talk about the canvas grid or coordinate space. Our HTML skeleton from the previous page had a canvas element 150 pixels wide and 150 pixels high.

### Drawing rectangles

Unlike SVG, (canvas) only supports two primitive shapes: rectangles and paths (lists of points connected by lines). All other shapes must be created by combining one or more paths. Luckily, we have an assortment of path drawing functions which make it possible to compose very complex shapes.

### Drawing paths

Now let's look at paths. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:

1. First, you create the path.
2. Then you use drawing commands to draw into the path.
3. Once the path has been created, you can stroke or fill the path to render it.

### Path2D objects

As we have seen in the last example, there can be a series of paths and drawing commands to draw objects onto your canvas. To simplify the code and to improve performance, the Path2D object, available in recent versions of browsers, lets you cache or record these drawing commands. You are able to play back your paths quickly.
Let's see how we can construct a **Path2D** object:
Path2D()
The **Path2D()** constructor returns a newly instantiated **Path2D** object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of **SVG path** data.

All path methods like **moveTo, rect, arc or quadraticCurveTo, etc.**, which we got to know above, are available on **Path2D** objects.

The **Path2D API** also adds a way to combine paths using the **addPath** method. This can be useful when you want to build objects from several components, for example.

***Path2D.addPath(path [, transform])***
Adds a path to the current path with an optional transformation matrix.

### Applying styles and colors

### Colors

Up until now we have only seen methods of the drawing context. If we want to apply colors to a shape, there are two important properties we can use: **fillStyle** and **strokeStyle.**

***fillStyle = color***
Sets the style used when filling shapes.

***strokeStyle = color***
Sets the style for shapes' outlines.

### Transparency

In addition to drawing opaque shapes to the canvas, we can also draw semi-transparent (or translucent) shapes. This is done by either setting the **globalAlpha** property or by assigning a semi-transparent color to the stroke and/or fill style.

### Line styles

There are several properties which allow us to style lines.

***lineWidth = value***
Sets the width of lines drawn in the future.

***lineCap = type***
Sets the appearance of the ends of lines.

***lineJoin = type***
Sets the appearance of the "corners" where lines meet.

***miterLimit = value***
Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.

***getLineDash()***
Returns the current line dash pattern array containing an even number of non-negative numbers.

***setLineDash(segments)***
Sets the current line dash pattern.

***lineDashOffset = value***
Specifies where to start a dash array on a line.

### Gradients

Just like any normal drawing program, we can fill and stroke shapes using linear, radial and conic gradients. We create a ***CanvasGradient*** object by using one of the following methods. We can then assign this object to the **fillStyle** or **strokeStyle** properties.

### Patterns

***createPattern(image, type)***
Creates and returns a new canvas pattern object. **image** is a ***CanvasImageSource*** (that is, an ***HTMLImageElement***, another canvas, a **(video)** element, or the like. **type** is a string indicating how to use the image.

The type specifies how to use the image in order to create the pattern, and must be one of the following string values:

**repeat**
Tiles the image in both vertical and horizontal directions.

**repeat-x**
Tiles the image horizontally but not vertically.

**repeat-y**
Tiles the image vertically but not horizontally.

**no-repeat**
Doesn't tile the image. It's used only once.

### Shadows

Using shadows involves just four properties:

**shadowOffsetX = float**
Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.

**shadowOffsetY = float**
Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.

**shadowBlur = float**
Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.

**shadowColor = color**
A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

### Canvas fill rules

When using **fill** (or **clip** and **isPointInPath**) you can optionally provide a fill rule algorithm by which to determine if a point is inside or outside a path and thus if it gets filled or not. This is useful when a path intersects itself or is nested.

Two values are possible:

**"nonzero":** ***The non-zero winding rule,*** which is the default rule.


**"evenodd":** ***The even-odd winding rule.***


### Drawing text

The canvas rendering context provides two methods to render text:

**fillText(text, x, y [, maxWidth])**
Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.

**strokeText(text, x, y [, maxWidth])**
Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

### Styling text

 There are some more properties which let you adjust the way the text gets displayed on the canvas:

**font = value**
The current text style being used when drawing text. This string uses the same syntax as the ***CSS*** font property. The default **font** is 10px sans-serif.

**textAlign = value**
Text alignment setting. Possible values: **start, end, left, right or center.** The default value is **start.**

**textBaseline = value**
Baseline alignment setting. Possible values: **top, hanging, middle, alphabetic, ideographic,** bottom. The default value is **alphabetic.**

**direction = value**
Directionality. Possible values: **ltr, rtl, inherit.** The default value is **inherit.**

These properties might be familiar to you, if you have worked with CSS before.

### Advanced text measurements

In the case you need to obtain more details about the text, the following method allows you to measure it.

**measureText()**
Returns a **TextMetrics** object containing the width, in pixels, that the specified text will be when drawn in the current text style.


### Gecko-specific notes

In Gecko (the rendering engine of Firefox, Firefox OS and other Mozilla based applications), some ***prefixed APIs*** were implemented in earlier versions to draw text on a canvas. These are now deprecated and removed, and are no longer guaranteed to work.
