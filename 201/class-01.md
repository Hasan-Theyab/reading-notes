## How the Web Works
When you visit a website, the web server
hosting that site could be anywhere in the
world. In order for you to find the location of
the web server, your browser will first connect
to a Domain Name System (DNS) server

## How Websites Are Created
Small websites are often written just using HTML and CSS.Larger websites — in particularthose that are updated regularlyand use a content managementsystem (CMS), blogging tools, ore-commerce software — often make use of more complex technologies on the web server,but these technologies are actually used to produce HTML and CSS that is then sent to the browser.

HTML pages are text documents.

HTML uses tags (characters that sit inside angled brackets) to give 

the information they surround special meaning.

Tags are often referred to as elements.

Tags usually come in pairs. The opening tag denotesthe start of a piece of content; the closing tag denotes the end.

Opening tags can carry attributes, which tell us more about the content of that element.

Attributes require a name and a value.
To learn HTML you need to know what tags are available for you to use,what they do, and where they can go.

HTML Uses Elements to Describe the Structure of Pages
Let's look closer at the code from the last page.There are several different elements. Each element has an opening tag and a closing tag.

Attributes provide additional information about the contents of an element. They appear on the opening tag of the element and are
made up of two parts: a name and a value,separated by an equals sign.

<p lang="en-us">Paragraph in English</p>

The attribute name indicates what kind of extra information you are supplying about the element's content. It should be written in lowercase.

The value is the information or setting for the attribute. It
should be placed in double quotes. Different attributes can
have different values.

Here an attribute called lang is
used to indicate the language
used in this element. The value
of this attribute on this page
specifies it is in US English

<body> element:
You met the <body> element
in the first example we created.
Everything inside this element is
shown inside the main browser
window.
<head> element:


Before the <body> element you
will often see a <head> element.


This contains information
about the page (rather than
information that is shown within
the main part of the browser
window that is highlighted in
blue on the opposite page).

## EXTRA MARKUP
HTML 5:
<!DOCTYPE html> elment:
HTML 4:
<!DOCTYPE html PUBLIC
"-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">


 element
Transitional XHTML 1.0:
<!DOCTYPE html PUBLIC
"-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/
xhtml1-transitional.dtd"> element
Strict XHTML 1.0:
<!DOCTYPE html PUBLIC
"-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/
xhtml1-strict.dtd">element
XML Declaration:
<?xml version="1.0" ?> element
DOCTYPES tell browsers which version of HTML you are using.

You can add comments to your code between the <!-- and --> markers.

The id and class attributes allow you to identify particular elements.

The <div> and <span> elements allow you to group
block-level and inline elements together.

<iframes> cut windows into your web pages through which other pages can be displayed.

The <meta> tag allows you to supply all kinds of information about your web page.

Escape characters are used to include special characters in your pages such as <, >, and ©.

The new HTML5 elements indicate the purpose of different parts of a web page and help to describe its structure.
The new elements provide clearer code (compared with using multiple <div> elements).

Older browsers that do not understand HTML5 elements need to be told which elements are block-level elements.
To make HTML5 elements work in Internet Explorer 8 (and older versions of IE), extra JavaScript is needed, which is available free from Google

Because there have been several versions of HTML, each
web page should begin with a DOCTYPE declaration to tell a
browser which version of HTML the page is using (although
browsers usually display the page even if it is not included).
We will therefore be including
one in each example for the rest
of the book.

As you will see when we come to look at CSS and its box model on
page 316, the use of a DOCTYPE can also help the browser to
render a page correctly. Because XHTML was written
in XML, you will sometimes see pages that use the XHTML strict DOCTYPE start with the optional XML declaration. Where this is used, it should be the first thing in a document.
There must be nothing before it,
not even a space.

**comments in HTML:**
If you want to add a comment
to your code that will not be
visible in the user's browser, you
can add the text between these
characters:
<!-- comment goes here -->

Example:


(<!-- start of introduction -->)


(<h1>Current Exhibitions</h1>)


(<h2>Olafur Eliasson</h2>)


(<!-- end of introduction -->)


(<!-- start of main text -->)


(<p>Olafur Eliasson was born in Copenhagen, Denmark
in 1967 to Icelandic parents.</p>)


(<p>He is known for sculptures and large-scale
installation art employing elemental materials
such as light, water, and air temperature to
enhance the viewer's experience.</p>)




There are some characters that are used in
and reserved by HTML code. (For example, the
left and right angled brackets.)


HTML5 is introducing a new set of
elements that help define the structure of
a page.

They are covered here (rather than with the other HTML
elements you met earlier in the book) because you'll find
it easier to understand how they can be used now that you
have seen how CSS can control the layout a page. These
new elements are going to play an important part in creating
layouts going forward. 


It's important to understand who your target audienceis, why they would come to your site, what information they want to find and when they are likely to return.

Site maps allow you to plan the structure of a site.

Wireframes allow you to organize the information that will need to go on each page.

Design is about communication. Visual hierarchy helps visitors understand what you are trying to tell them.

You can differentiate between pieces of information using size, color,and style.

You can use grouping and similarity to help simplify
the information you present.
                
looks at some key concepts in computer programming, showing you how computers create models of the world using data, and how JavaScript
is used to change the contents of an HTML page.

How JavaScript makes webpages more interavtive:

1 ACCESS CONTENT

You can use JavaScript to select any element, attribute, or text from an HTML page. For example:


• Select the text inside all of the <hl> elements on a page

• Select any elements that have a class attribute with a value of note

• Find out what was entered into a text input whose id attribute has a
  value of email 

2 MODIFY CONTENT

You can use JavaScript to add elements, attributes, and text to the
page, or remove them. For example:

• Add a paragraph of text after the first <hl> element

• Change the value of class attributes to trigger new CSS rules
  for those elements

• Change the size or position of an <img> element

3 PROGRAM RULES

You can specify a set of steps for the browser to follow (like a recipe), which allows it to access or change the content of a page. For example:

• A gallery script could check which image a user clicked on and        display a larger version of that image.

• A mortgage calculator could collect values from a form, perform a     calculation, and display repayments.

• An animation could check the dimensions of the browser window
  and move an image to the bottom of the viewable area (also known as
  the viewport).

4 REACT TO EVENTS
You can specify that a script should run when a specific event has occurred. For example, it could be run when:

• A button is pressed

• A link is clicked (or tapped) on

• A cursor hovers over an element

• Information is added to a form

• An interval of time has passed

• A web page has finished loading

A script is a series of instructions that a computer can follow to achieve a goal.

To write a script, you need to first state your goal and then list the
tasks that need to be completed in order to achieve it.

You need to learn to "think" like a computer because they solve
tasks in different ways than you or I might approach them.

Often scripts will need to perform different tasks in different situations. You can use flowcharts to work out how the tasks fit together.

The flowcharts show the paths between each step.
A script is a series of instructions that the computer
can follow in order to achieve a goal

Each time the script runs, it might only use a subset of
all the instructions.

Computers approach tasks in a different way than humans, so your instructions must let the computer solve the task prggrammatically

To approach writing a script, break down your goal into a series of tasks and then work out each step needed to complete that task (a flowchart can help).

Computers creates models of the world using Data
Programmers can write code to say "when this event occurs,eun that code."

web browsers use HTML markup to create amodel of the webpage.Each creates its own node (which a kind of object).

To make webpages interactive you write code that uses the browser's model of the web page.

It is best to keep JavaScript code in its own JavaScript
file. JavaScript files are text files (like HTML pages and
CSS style sheets), but they have the . js extension

The HTML <script> element is used in HTML pages
to tell the browser to load the JavaScript file (rather like
the <link> element can be used to load a CSS file).

If you view the source code of the page in the browser,
the JavaScript will not have changed the HTML,
because the script works with the model of the web
page that the browser has created.