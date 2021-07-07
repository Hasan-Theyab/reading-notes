The img element is used to add images to a web page.

You must always specify a src attribute to indicate the source of an image and an alt attribute to describe the content of an image.

You should save images at the size you will be using them on the web page and in the appropriate format.

Photographs are best saved as JPEGs; illustrations or logos that use flat colors are better saved as GIFs.

HTML 5: Figure and Figure Caption

figure element:

Images often come with captions. HTML5 has introduced a new figure element to contain images and their caption so that the two are associated.

You can have more than one image inside the figure element as long as they all share the same caption.

figcaption element:

The figcaption element has been added to HTML5 in order to allow web page authors to add a caption to an image.

Before these elements were created there was no way to
associate an img element with its caption.

Older browsers that do not understand HTML5 elements simply ignore the new elements and display the content of them.

Color not only brings your site to life, but also helps convey the mood and evokes reactions.

There are three ways to specify colors in CSS: RGB values, hex codes, and color names.

Color pickers can help you find the color you want.

It is important to ensure that there is enough contrast between any text and the background color (otherwise people will not be able to read your content).

CSS3 has introduced an extra value for RGB colors to indicate opacity. It is known as RGBA.

CSS3 also allows you to specify colors as HSL values, with an optional opacity value. It is known as HSLA.

Understanding Color:

Every color on a computer screen is created by mixing amounts of red,green, and blue. To find the color you want, you can use a color picker.

Computer monitors are made up of thousands of tiny squares called pixels (if you look very closely at your monitor you should be able to see them).

When the screen is not turned on, it's black because it's not emitting any light. When it's on, each pixel can be a different color, creating a picture.

The color of every pixel on the screen is expressed in terms of a mix of red, green, and blue — just like on a television screen.

Color picking tools are available in image editing programs like
Photoshop and GIMP. You can see the RGB values specified next to the radio buttons that say R, G, B.

The hex value is provided next to the pound or hash (# symbol). There is also a good color picking tool at: colorschemedesigner.com

RGB Values
Values for red, green, and blue are expressed as numbers
between 0 and 255.

rgb(102,205,170) This color is made up of the
following values:
102 red
205 green
170 blue

Hex Codes
Hex values represent values for red, green, and blue in
hexadecimal code.

#66cdaa
The value of the red, 102, is expressed as 66 in hexadecimal code. The 205 of the green is expressed as cd and the 170 of the blue equates to aa.

Color Names
Colors are represented by predefined names. However, they are very limited in number.

MediumAquaMarine
There are 147 color names supported by browsers (this color is MediumAquaMarine). Most consider this to be a limited color palette, and it is hard to remember the name for each of the colors so (apart from
white and black) they are not commonly used.


Hue
Hue is near to the colloquial idea of color. Technically speaking however, a color can also have saturation and brightness as well as hue.

Saturation
Saturation refers to the amount of gray in a color. At maximum saturation, there would be no gray in the color. At minimum saturation, the color would be mostly gray.


Brightness
Brightness (or "value") refers to how much black is in a color. At maximum brightness, there would be no black in the color. At minimum brightness, the color would be very dark.


There are properties to control the choice of font, size, weight, style, and spacing.


There is a limited choice of fonts that you can assume most people will have installed.

If you want to use a wider range of typefaces there are several options, but you need to have the right license to use them.


You can control the space between lines of text, individual letters, and words. Text can also be aligned to the left, right, center, or justified. It can also be indented.


You can use pseudo-classes to change the style of an element when a user hovers over or clicks on text, or when they have visited a link.

Typeface Terminology

Serif
Serif fonts have extra details on the ends of the main strokes of the letters. These details are known as serifs.

In print, serif fonts were traditionally used for long passages of text because they were considered easier to read.

Sans-Serif

Sans-serif fonts have straight ends to letters, and therefore
have a much cleaner design.

Screens have a lower resolution than print. So, if the text is small,
sans-serif fonts can be clearer to read.

Monospace
Every letter in a monospace (or fixed-width) font is the same
width. (Non-monospace fonts have different widths.)

Monospace fonts are commonly used for code because they align
nicely, making the text easier to follow.

Choosing a Typeface for your Website

When choosing a typeface, it is important to understand that a
browser will usually only display it if it's installed on that
user's computer.

Serif
Serif fonts have extra details on the end of the main strokes of
the letters.

Examples:
Georgia
Times
Times New Roman

Sans-Serif
Sans-serif fonts have straight ends to letters and therefore have a much cleaner design.

Examples:
Arial
Verdana
Helvetica

You may have noticed that programs such as Word, Photoshop and InDesign offer the same sizes of text.



This is because they are set according to a scale or ratio that was developed by European typographers in the sixteenth century.

It is considered that this scale for type is pleasing to the eye and it has therefore changed little in the last 400 years.

For this reason, when you are designing pages, using sizes
from this scale will help them look more attractive.

On the next page, you can see how to achieve this scale using pixels, percentages, and ems.

Print designers often refer to the size of text in terms of points
rather than pixels (hence the use of pt in the scale on the
right). A pixel roughly equates to a point because a point
corresponds to 1/72 of an inch, and most computer displays
have a resolution of 72 dots per inch.


The default size of text in a browser is 16 pixels. So if you
use percentages or ems, you calculate the size of text you
want based on the default size of the text used in browsers.
For example, you could scale down to 12 pixels for body copy
and scale up to 24 pixels for headings.


Recently, some web designers have started to leave the body
text at the default size of 16 pixels and adjust the other font
sizes using a scale that keeps the relative proportions of this
one.


When you first see body text at 16 pixels, it might seem quite
large. Once you get used to the larger type, however, most people find it far easier to read; and going back to a page where
main type is 12 pixels will often then look quite small.

Type Scales
8pt
9pt
10pt
11pt
12pt
14pt
18pt
24pt
36pt
48pt
60pt
72pt


There are hundreds of image formats available each with a specific use case. I bet most of us wouldn’t have come across 90% of the image formats listed on Wikipedia.

In this post, we would only be looking at the three most commonly used image formats in websites and mobile applications — JPEG, PNG and GIF. Several statistics reports, including the one from HTTP Archive, indicate that these 3 formats together comprise of more than 95% of all images loaded on websites. However, these 3 image formats have significant differences amongst themselves thus making each of them suitable for specific use cases. Understanding these major differences would help us deliver the best possible images to our website and mobile app users.



### TL;DR


Use JPEG format for all images that contain a natural scene or photograph where variation in colour and intensity is smooth. Use PNG format for any image that needs transparency or for images with text & objects with sharp contrast edges like logos. Use GIF format for images that contain animations.



These are some of the major differences between the three most popular image formats for web — JPEG, PNG and GIF. To summarise once again, use JPEG format for all images that contain a natural scene or photograph where variation in colour and intensity is smooth. Use PNG format for any image that needs transparency or for images with text & objects with sharp contrast edges like logos. Use GIF format for images that contain animations.
