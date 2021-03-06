# There are three types of HTML lists: ordered, unordered, and          definition.

Ordered lists use numbers.

Unordered lists use bullets.

Definition lists are used to define terminology.

Lists can be nested inside one another.





CSS treats each HTML element as if it has its own box.

You can use CSS to control the dimensions of a box.

You can also control the borders, margin and padding
for each box with CSS.

It is possible to hide elements using the display and
visibility properties.


Block-level boxes can be made into inline boxes, and
inline boxes made into block-level boxes.


Legibility can be improved by controlling the width of
boxes containing text and the leading.

CSS3 has introduced the ability to create image
borders and rounded borders.

1
Border
Every box has a border (even if it is not visible or is specified to be 0 pixels wide). The border separates the edge of one box from another.
2
Margin
Margins sit outside the edge of the border. You can set the width of a margin to create a gap between the borders of two adjacent boxes.
3
Padding
Padding is the space between the border of a box and any content contained within it. Adding padding can increase the readability of its contents.





Sometimes you will want to use a double or single quote mark
within a string. Because strings can live in single
or double quotes, if you just want to use double quotes in the
string, you could surround the entire string in single quotes.
If you just want to use single quotes in the string, you could
surround the string in double quotes (as shown in the third line
of this code example). You can also use a technique
called escaping the quotation characters. This is done by
using a backwards slash (or "backslash") before any type of quote mark that appears within a string (as shown on the fourth
line of this code sample). The backwards slash tells the
interpreter that the following character is part of the string,
rather than the end of it.

A Boolean variable can only have a value of true or fa 1 se, but this
data type is very helpful.

Programmers sometimes use shorthand to create variables.
Here are three variations of how to declare variables and assign
them values:

1. Variables are declared and values assigned in the same statement.

2. Three variables are declared on the same line, then values assigned to each.

3. Two variables are declared and assigned values on the same line. Then one is declared and assigned a value on the next line. (The third example shows two numbers, but you can declare variables that hold different types of data on the same line, e.g., a string and a number.)

4 . Here, a variable is used to hold a reference to an element in the HTML page. This allows you to work directly with the element
stored in that variable. (See more about this on p190.)
While the shorthand might save you a little bit of typing, it can
make your code a little harder to follow. So, when you are
starting off, you will find it easier to spread your code over a few
more lines to make it easier to read and understand.




A switch statement starts with a variable called the switch value.
Each case indicates a possible value for this variable and the
code that should run if the variable matches that value.
Here, the variable named 1 eve l is the switch value. If the value of the l eve 1 variable is the string One, then the code for the first case is executed. If it is Two, the second case is executed. If it is Three, the third case is executed. If it is none of these, the code
for the defaul t case is executed. The entire statement lives in one code block (set of curly braces), and a colon separates the option
from the statements that are to be run if the case matches the switch value.
At the end of each case is the break keyword. It tells the JavaScript interpreter that it has finished with this switch statement and to proceed to run any subsequent code that appears after it.
IF ... ELSE

??? There is no need to provide an else option. (You can just use an if
statement.)

??? With a series of if statements, they are all checked even if a match has been found (so it performs more slowly than switch

JavaScript can convert data types behind the scenes to complete an operation. This is known as type coercion. For
example, a string 'l ' could be converted to a number 1 in the
following expression:(' 1' > 0). As a result, the above expression
would evaluate to true. JavaScript is said to use weak
typing because the data type for a value can change. Some
other languages require that you specify what data type
each variable will be. They are said to use strong typing.
Type coercion can lead to unexpected values in your
code (and also cause errors). Therefore, when checking if two
values are equal, it is considered better to use strict equals
operators ===and ! == rather than == and ! = as these
strict operators check that the value and data types match

A for loop is often used to loop through the items in an array.
In this example, the scores for each round of a test are stored in
an array called scores. The total number of items in
the array is stored in a variable called array length. This number is obtained using the length property of the array.
There are three more variables:
roundNumber holds the round of the test; msg holds the message to display; i is the counter (declared outside the loop).
The loop starts with the for keyword, then contains the condition inside the parentheses. As long as the counter is less than the total number of items in the array, the contents of the curly braces will continue to
run. Each time the loop runs, the round number is increased by 1.
Inside the curly braces are rules that write the round number and
the score to the msg variable. The variables declared outside of the
loop are used within the loop. The msg variable is then written
into the page. It contains HTML so the i nnerHTML property is
used to do this. Remember, p228 will talk about security
issues relating to this property.




