Links are created using the (<a>) element.

The (<a>) element uses the href attribute to indicate the page you are linking to.

If you are linking to a page within your own site, it is best to use relative links rather than qualified URLs.

You can create links to open email programs with an email address in the "to" field.

You can use the id attribute to target elements within a page that can be linked to.


### Writing Links

Links are created using the ) element. Users can click on anything between the opening (<a>) tag and the closing (</a>) tag. You specify which page you want to link to using the href attribute.

The text between the opening (<a>) tag and closing (</a>) tag is known as link text. Where possible, your link text should explain where visitors will be taken if they click on it (rather than just saying "click here").


Many people navigate websites by scanning the text for links. Clear link text can help visitors find what they want. This will give them a more positive impression of your site and may encourage them to visit it for longer. (It also helps people using screen reader software.)


To write good link text, you can think of words people might use when searching for the page that you are linking to. (For example, rather than write "places to stay" you could use something more specific such as
"hotels in New York.")

### Relative Link Type

### Same Folder

To link to a file in the same folder, just use the file name. (Nothing else is needed.)

### Child Folder

For a child folder, use the name of the child folder, followed by a 
forward slash, then the file name.

### Grandchild Folder

Use the name of the child folder, followed by a forward slash, then the name of the grandchild folder, followed by another forward slash, then the file name.

### Parent Folder

Use ../ to indicate the folder above the current one, then follow it with the file name.

### GrandParent Folder

Repeat the ../ to indicate that you want to go up two folders (rather than one), then follow it with the file name.

### Email Links

### mailto:

To create a link that starts up the user's email program and addresses an email to a specified email address, you use the ("<a>") element. However, this time the value of the href attribute starts with mailto: and is followed by the email address you want the email to be sent to.On the right you can see that an email link looks just like any other link but, when it is clicked on, the user's email program will open a new email message and address it to the person
specified in the link.

### Opening Links in a New Window

### target

If you want a link to open in a new window, you can use the target attribute on the opening (<a>) tag. The value of this attribute should be _blank. One of the most common reasons a web page author might want a link to be opened in a new window is if it points to another website. In such cases, they hope the user will return to the window containing their
site after finishing looking at the other one. Generally you should avoid
opening links in a new window, but if you do, it is considered good practice to inform users that the link will open a new window before they click on it.

(<div>) elements are often used as containing elements to group together sections of a page.

Browsers display pages in normal flow unless you specify relative, absolute, or fixed positioning.

### Building Blocks

CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.

Block-level boxes start on a new line and act as the main building blocks
of any layout, while inline boxes flow between surrounding text. You can
control how much space each box takes up by setting the width of the
boxes (and sometimes the height, too). To separate boxes, you can use
borders, margins, padding, and background colors.

Block-level elements
start on a new line
Examples include:
(<h1> <p> <ul> <li>)

Inline elements
flow in between
surrounding text
Examples include:
(<img>) (<b>) (<i>)


Containing Elements If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.

It is common to group a number of elements together inside a (<div>)
(or other block-level) element. For example, you might group together
all of the elements that form the header of a site (such as the logo and
the main navigation). The (<div>) element that contains this group of elements is then referred to as the containing element.

CSS has the following positioning schemes that allow you to control
the layout of a page: normal flow, relative positioning, and absolute
positioning. You specify the positioning scheme using the position
property in CSS. You can also float elements using the float property.

Normal flow
Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one. Even if you specify the width of the boxes and there is space for two elements to sit side-byside, they will not appear next to each other. This is the default
behavior (unless you tell the browser to do something else).

Relative Positioning
This moves an element from the position it would be in normal
flow, shifting it to the top, right,bottom, or left of where it
would have been placed. This does not affect the position of
surrounding elements; they stay in the position they would be in
in normal flow.

Absolute positioning
This positions the element in relation to its containing
element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.

To indicate where a box should be positioned, you may also need to use
box offset properties to tell the browser how far from the top or bottom
and left or right it should be placed. (You will meet these when we
introduce the positioning schemes on the following pages.)

Fixed Positioning
This is a form of absolute positioning that positions the element in relation to the browser window, as opposed to the containing element.
Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user
scrolls up or down the page. 

Floating Elements 
Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box. The floated
element becomes a block-level element around which other content can flow.

DECLARING A FUNCTION

To create a function, you give it a name and then write the statements needed to achieve its task iside the curly braces.

You declare a function using the function keyword 

You give the function a name (sometimes called identifiers followed by parentheses)

The statements that perform the task sit in a code block (They are inside curly braces).

CALLING A FUNCTION

Having declared the function, you can then execute all of statements between its curly braces with just one line of code.


Functions allow you to group a set of related statements together that represent a single task.

Functions can take parameters (informatiorJ required to do their job) and may return a value.

LOCAL VARIABLES

When a variable is created inside a function using the var keyword, it can only be used in that function. It is called a local variable or function-level variable. It is said to have local scope or function-level scope. It cannot be accessed outside of the function in which it was declared. Below, area is a local variable.

The interpreter creates local variables when the
function is run, and removes them as soon as the
function has finished its task. This means that:

• If the function runs twice, the variable can have
different values each time.
• Two different functions can use variables with the
same name without any kind of naming conflict.


GLOBAL VARIABLES
If you create a variable outside of a function, then it
can be used anywhere within the script. It is called a
global variable and has global scope. In the example
shown, wa11 Size is a global variable.

Global variables are stored in memory for as long
as the web page is loaded into the web browser.
This means they take up more memory than local
variables, and it also increases the risk of naming
conflicts (see next page). For these reasons, you
should use local variables wherever possible.

If you forget to declare a variable using the var
keyword, the variable will work, but it will be treated
as a global variable (this is considered bad practice).


### 6 Reasons for Pair Programming

1-  Greater efficiency:
    It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making.


2-  Engaged collaboration:
    When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone.


3-  Learning from fellow students:
    Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.


4-  Social skills:
    Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key.


5-  Job interview readiness:
    A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.


6-  Work environment readiness:
    Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.