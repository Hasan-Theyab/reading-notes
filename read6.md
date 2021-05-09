## Functions
Functions are one of the fundamental building blocks in JavaScript. A function in JavaScript is similar to a procedure—a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output. To use a function, you must define it somewhere in the scope from which you wish to call it.


## Function declarations
A function definition (also called a function declaration, or function statement) consists of the function keyword, followed by:

- The name of the function.
- A list of parameters to the function, enclosed in           parentheses and separated by commas.
- The JavaScript statements that define the function,         enclosed in curly brackets, {...}.

For example, the following code defines a simple function named square:

function square(number) {
  return number * number;
}

## Function expressions
While the function declaration above is syntactically a statement, functions can also be created by a function expression.

Such a function can be **anonymous**; it does not have to have a name. For example, the function square could have been defined as:

const square = function(number) { return number * number }
var x = square(4) // x gets the value 16