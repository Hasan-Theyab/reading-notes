# Images in HTML

- You can specify the dimensions of images using CSS. This is very helpful when you use the same sized images on several pages of your site.


- Images can be aligned both horizontally and vertically using CSS.


- You can use a background image behind the box created by any element on a page.



- Background images can appear just once or be repeated across the background of the box.


- You can create image rollover effects by moving the background position of an image.



- To reduce the number of images your browser has to load, you can create image sprites.




#### IMAGE ROLLOVERS & SPRITES

Using CSS, it is possible to create a link or button that changes to a second style when a user moves their mouse over it (known as a **rollover**) and a third style when they click on it.


This is achieved by setting a background image for the link or button that has three different styles of the same button (but only allows enough space to show one of them at a time). You can see the image we are using in this example on the right. It actually features two buttons on the one image.


When the user moves their mouse over the element, or clicks on it, the position of the background image is moved to show the relevant image.


When a single image is used for several different parts of an interface, it is known as a **sprite**. You can add the logo and other interface elements, as well as buttons to the image.


The advantage of using sprites is that the web browser only needs to request one image rather than many images, which can make the web page load faster.

HTML CODE:
a class="button" id="add-to-basket"
Add to basket /a
a class="button" id="framing-options"
Framing options /a



CSS CODE:

a.button {
height: 36px;
background-image: url("images/button-sprite.jpg");
text-indent: -9999px;
display: inline-block;}
a#add-to-basket {
width: 174px;
background-position: 0px 0px;}
a#framing-options {
width: 210px;
background-position: -175px 0px;}
a#add-to-basket:hover {
background-position: 0px -40px;}
a#framing-options:hover {
background-position: -175px -40px;}
a#add-to-basket:active {
background-position: 0px -80px;}
a#framing-options:active {
background-position: -175px -80px;}

# Practical Information 

- Search engine optimization helps visitors find your sites when using search engines.


- Analytics tools such as Google Analytics allow you to see how many people visit your site, how they find it, and what they do when they get there.



- To put your site on the web, you will need to obtain a domain name and web hosting.


- FTP programs allow you to transfer files from your local computer to your web server.


- Many companies provide platforms for blogging, email newsletters,e-commerce and other popular website tools (to save you writing them from scratch). 



#### FTP & Third Party Tools

To transfer your code and images from your computer to your hosting company, you use something known as File Transfer Protocol.


As the name suggests, File Transfer Protocol (or FTP) allows you to transfer files across the Internet from your computer to the web server hosting your site.


There are many FTP programs that offer a simple interface that shows you the files on your computer alongside the files that are on your web server. These allow you to drag and drop files from your computer to the server or vice versa.



There are a wide variety of sites that offer services commonly created by web developers (to save you having to build them yourself).


Some hosting companies offer tools to upload files to their servers using a web browser, but it is more common to use an FTP program as they are faster at transmitting files.



When you purchase your web hosting, you will be given FTP details that you enter into your FTP program in order to connect to the server. Usually this will be an address (such as ftp:// mydomain.com), a username, and a password. It is important to keep this information secure in order to prevent strangers from gaining access to your server.



Here is a list of some popular FTP applications:

**FileZilla:**
filezilla-project.org
Windows, Mac, Linux


**FireFTP:**
fireftp.mozdev.org
Windows, Mac, Linux


**CuteFTP:**
cuteftp.com
Windows, Mac


**SmartFTP:**
smartftp.com
WIndows


**Transmit:**
panic.com/transmit
Mac


Here is a list of some popular third party tools:

<span style="color: orange;">BLOGS</span>

wordpress.com
tumblr.com
posterous.com

<span style="color: orange;">E-COMMERCE</span>

shopify.com
bigcartel.com
go.magento.com

<span style="color: orange;">EMAIL NEWSLETTERS</span>

campaignmonitor.com
mailchimp.com

<span style="color: orange;">SOCIAL NETWORKING
SHARING BUTTONS</span>

addthis.com
addtoany.com


# Video and Audio APIs

#### HTML5 video and audio

The (video) and (audio) elements allow us to embed video and audio into web pages. As we showed in Video and audio content, a typical implementation looks like this:

(video controls)
  (source src="rabbit320.mp4" type="video/mp4")
  (source src="rabbit320.webm" type="video/webm")
  (p) Your browser doesn't support HTML5 video. Here is a (a href="rabbit320.mp4")link to the video (/a) instead.(/p)
(/video)


This creates a video player inside the browser, the most interesting attribute is controls, which enables the default set of playback controls. If you don't specify this, you get no playback controls:


This is not as immediately useful for video playback, but it does have advantages. One big issue with the native browser controls is that they are different in each browser — not very good for cross-browser support! Another big issue is that the native controls in most browsers aren't very keyboard-accessible.

You can solve both these problems by hiding the native controls (by removing the controls attribute), and programming your own with HTML, CSS, and JavaScript.

#### Exploring the HTML

* The video element contains two source elements so that different    formats can be loaded depending on the browser viewing the site.

* The controls HTML is probably the most interesting:
    
    * We have four buttons — play/pause, stop, rewind, and fast forward.

    * Each button has a class name, a data-icon attribute for defining what icon should be shown on each button (we'll show how this works in the below section), and an aria-label attribute to provide an understandable description of each button, since we're not providing a human-readable label inside the tags. The contents of aria-label attributes are read out by screenreaders when their users focus on the elements that contain them.


    * There is also a timer <div>, which will report the elapsed time when  the video is playing. Just for fun, we are providing two reporting mechanisms — a span containing the elapsed time in minutes and seconds, and an extra <div> that we will use to create a horizontal indicator bar that gets longer as the time elapses.

#### Exploring the CSS

* We set the outer .timer <div> to have flex: 5, so it takes up most of the width of the controls bar. We also give it position: relative, so that we can position elements inside it conveniently according to it's boundaries, and not the boundaries of the <body> element.


* The inner <div> is absolutely positioned to sit directly on top of the outer <div>. It is also given an initial width of 0, so you can't see it at all. As the video plays, the width will be increased via JavaScript as the video elapses.


* The (span) tag is also absolutely positioned to sit near the left hand side of the timer bar.


* We also give our inner <div> and (span) tag the right amount of z-index so that the timer will be displayed on top, and the inner <div> below that. This way, we make sure we can see all the information — one box is not obscuring another.

#### Implementing the JavaScript

1. First of all, we work out the number of minutes and seconds in the  HTMLMediaElement.currentTime value.

2. Then we initialize two more variables — minuteValue and secondValue.

3. The two if statements work out whether the number of minutes and seconds are less than 10. If so, they add a leading zero to the values, in the same way that a digital clock display works.


4. The actual time value to display is set as minuteValue plus a colon character plus secondValue.


5. The Node.textContent value of the timer is set to the time value, so it displays in the UI.


6. The length we should set the inner <div> to is worked out by first working out the width of the outer <div> (any element's clientWidth property will contain its length), and then multiplying it by the HTMLMediaElement.currentTime divided by the total HTMLMediaElement.duration of the media.


7. We set the width of the inner <div> to equal the calculated bar length, plus "px", so it will be set to that number of pixels.


