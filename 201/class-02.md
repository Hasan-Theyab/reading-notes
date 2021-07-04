# Chapter 2: Text

HTML elements are used to describe the structure of the page (e.g. headings, subheadings, paragraphs).


They also provide semantic information (e.g. where emphasis should be placed, the definition of any acronyms used, when given text is a quotation).



Example TEXT:



("<html>
    <head>
    <title>Text</title>
    </head>
    <body>
    <h1>The Story in the Book</h1>
    <h2>Chapter 1</h2>
    <p>Molly had been staring out of her window for about
    an hour now. On her desk, lying between the copies
    of <i>Nature</i>, <i>New Scientist</i>, and all
    the other scientific journals her work had
    appeared in, was a well thumbed copy of <cite>On
    The Road</cite>. It had been Molly's favorite book
    since college, and the longer she spent in these
    four walls the more she felt she needed to be
    free.</p>
    <p>She had spent the last ten years in this room,
    sitting under a poster with an Oscar Wilde quote
    proclaiming that <q>Work is the refuge of
    people who have nothing better to do</q>. Although
    many considered her pioneering work, unraveling
    the secrets of the llama <abbr
    title="Deoxyribonucleic acid">DNA</abbr>, to be an
    outstanding achievement, Molly <em>did</em> think
    she had something better to do.</p>
    </body>
</html>")




### Semantic Markup


1- ("<address>") 
    The ("<address>") element has
    quite a specific use: to contain
    contact details for the author of
    the page.




2- (<strong>): The use of the (<strong>)
    element indicates that its
    content has strong importance.
    For example, the words
    contained in this element might
    be said with strong emphasis.




3- (<cite>): When you are referencing a
    piece of work such as a book,
    film or research paper, the
    (<cite>) element can be used
    to indicate where the citation is
    from.




# Chapter 10:Introducing CSS

CSS treats each HTML element as if it appears inside
its own box and uses rules to indicate how that
element should look.



Rules are made up of selectors (that specify the
elements the rule applies to) and declarations (that
indicate what these elements should look like).



Different types of selectors allow you to target your
rules at different elements.



Declarations are made up of two parts: the properties
of the element that you want to change, and the values
of those properties. For example, the font-family
property sets the choice of font, and the value arial
specifies Arial as the preferred typeface.



CSS rules usually appear in a separate document,
although they may appear within an HTML page.


Example: INTRODUCING CSS


This example uses two documents: the HTML file (example.html)
and a separate CSS file (example.css). The fifth line of HTML uses the
("<link>") element to indicate where the CSS file is located




("<!DOCTYPE html>
    <html>
    <head>
    <title>Introducing CSS</title>
    <link href="css/example.css" type="text/css"
    rel="stylesheet" />
    </head>
    <body>
    <h1>From Garden to Plate</h1>
    <p>A <i>potager</i> is a French term for an
    ornamental vegetable or kitchen garden ... </p>
    <h2>What to Plant</h2>
    <p>Plants are chosen as much for their functionality
    as for their color and form ... </p>
    </body>
    </html>
    body {
    font-family: Arial, Verdana, sans-serif;}
    h1, h2 {
    color: #ee3e80;}
    p {
    color: #665544;}")




CSS Associates Style rules with HTML elements:

CSS works by associating rules with HTML elements. These rules govern
how the content of specified elements should be displayed. A CSS rule
contains two parts: a selector and a declaration.


Selectors indicate which
element the rule applies to.
The same rule can apply to
more than one element if you
separate the element names
with commas.



Declarations indicate how
the elements referred to in
the selector should be styled.
Declarations are split into two
parts (a property and a value),
and are separated by a colon.


CSS Properties Affect How Elements Are Displayed:

CSS declarations sit inside curly brackets and each is made up of two
parts: a property and a value, separated by a colon. You can specify
several properties in one declaration, each separated by a semi-colon.


Properties indicate the aspects
of the element you want to
change. For example, color, font,
width, height and border.




Values specify the settings
you want to use for the chosen
properties. For example, if you
want to specify a color property
then the value is the color you
want the text in these elements
to be.



# Chapter 2: “Basic JavaScript Instructions

A script is made up of a series of statements. Each
statement is like a step in a recipe.


Scripts contain very precise instructions. For example,
you might specify that a value must be remembered
before creating a calculation using that value.



Variables are used to temporarily store pieces of
information used in the script.


Arrays are special types of variables that store more
than one piece of related information.


JavaScript distinguishes between numbers (0-9),
strings (text), and Boolean values (true or false).



Expressions evaluate into a single value.


Expressions rely on operators to calculate a value.

EXAMPLE:




("<!DOCTYPE html>
    <html>
    <head>
    1111., .• ,
    <title>JavaScript &amp; jQuery - Chapter 2: Basic JavaScript Instructions -
    Example</ title>
    <link rel="stylesheet" href="css/c02.css" />
    </head>
    <body>
    <hl>Elderflower</hl>
    <div id="content">
    <div id="greeting" class="message">Hello! </div>
    <table>
    <tr>
    <td>Custom sign: </ td>
    <td id="userSign"></ td>
    </ tr>
    <tr>
    <td>Total tiles: </td>
    <td id="ti l es "></td>
    </tr>
    <tr>
    <td>Subtotal: </td>
    <td id="subTotal">$</ td>
    </ tr>
    <tr>
    <td>Shipping: </ td>
    <td id="shipping">$</td>
    </tr>
    <tr>
    <td>Grand total: </td>
    <td id="grandTotal ">S</td>
    </tr>
    </ table>
    <a href="D" class="action">Pay Now</ a>
    </div>
    <script src="js/ example.js"></ script>
    </body>
    </html>)




# Chapter 4: Decisions and Loops

Conditional statements allow your code to make
decisions about what to do next.


Comparison operators (===, ! ==, ==, ! =, <, >, <=, =>)
are used to compare two operands.


Logical operators allow you to combine more than one
set of comparison operators


if ... else statements allow you to run one set of code
if a condition is true, and another if it is false.



switch statements allow you to compare a value
against possible outcomes (and also provides a default
option if none match).


Data types can be coerced from one type to another.

All values evaluate to either truthy or falsy.


There are three types of loop: for, while, and
do ... while. Each repeats a set of statements

EXAMPLE: IF STATEMENT



("var score 75; // Score
    var msg; // Message
    if (score>= 50) { // If score is 50 or higher
    msg = 'Congratulations!';
    msg += ' Proceed to the next round . ' ;
    var el = document.getElementByld('answer ' ) ;
    el .textContent = msg;")




EXAMPLE: IF...ELSE STATEMENT

(var pass = 50;              //  Pass mark
    var score = 75;            //  Current score
    var msg;                  //  Message     
                            


    // Select message to write based on score
    if (score >= pass) {
    msg = 'Congratulations, you passed!';
    } else {
    msg = 'Have another go!';
    var el = document .getElementByld('answer');
    el .textContent = msg;))




EXAMPLE: SWITCH STATEMENT

(var msg;                   // Message
 var level = 2;            // Level
 



 // Determine message based on level
 switch (level) {
    case 1:
        msg = 'Good luck on the first test ' ;
        break;
    case 2:
        msg = 'Second of three - keep going!';
        break;
    case 3:
        msg = ' Final round, almost there!';
        break;
    default :
        msg = 'Good l uck!';
        break;
    }    
    var el = document.getEl ementByld('answer ' );
    el .textContent = msg;)





