# Why problem domains are hard

The real world is a messy place.  Many of the problem domains we face as programmers are difficult to understand and look completely different depending on your viewpoint.

As programmers, we also are often not given complete information about the problem domain, so we don’t even have the information we need to understand it.

Just try and read the famous Domain Driven Design book and you’ll quickly see how complicated and difficult problem domains can be.  (Great book by the way, although you may have to read it twice or three times—I certainly did.)


# Programming is easy if you understand the problem domain

I’ve spent days trying to implement a feature only to finally go back and talk to a product owner and hash out completely how something should work and why it should work in a particular way, only to go back to my desk and crank out the code in a matter of hours.

The more and more I write code, the more I learn that understanding the problem is the most critical piece to the equation. It is very difficult to solve a problem before you know the question.  It’s like buzzing in on Jeopardy before you hear the clue and shouting out random questions.

# What can you do about it?

If understanding the problem domain is the hardest part of programming and you want to make programming easier, you can do one of two things:

1- Make the problem domain easier
2- Get better at understanding the problem domain


You can often make the problem domain easier by cutting out cases and narrowing your focus to a particular part of the problem.

What I mean by this is that it is often beneficial to take a part of the problem and fully understand that part before expanding the problem domain.

Games are really good at this.  Look at most games today and you’ll find that you start with a very small problem domain.  The first level is usually a tutorial that has a basic set of things you can do so that you don’t get overwhelmed.  But, as you advance through the levels, you usually find they get harder and introduce new concepts that build gradually on what you know, until you understand a pretty large problem domain.  (Starcraft is really good at this.)

The other choice is to become better at understanding problem domains.  As developers, we tend to think that sitting down and talking to customers or business people who know about the problem domain is a waste of time. It is easy to fall into the trap of thinking you understand enough of the problem to get started coding it.  Best to resist the temptation to “not waste anymore time talking” and make sure you understand a problem inside and out before you try and solve it with code.  It is much more expensive and time consuming to do things over than it is to do them right the first time.  I learn this lesson the hard way time and time again.


Objects group together a set of variables and functions to create a model
of a something you would recognize from the real world. In an object,
variables and functions take on new names.


IN AN OBJECT: VARIABLES BECOME KNOWN AS PROPERTIES If a variable is part of an object, it is called a property. Properties tell us about the object, such as the name of a hotel or the number of rooms it has.
Each individual hotel might have a different name and a different number of rooms.



IN AN OBJECT: FUNCTIONS BECOME KNOWN AS METHODS If a function is part of an object, it is called a method. Methods represent tasks that are associated with the object. For example, you can check how many rooms are available by subtracting the number of booked rooms from the total number of rooms.


Like variables and named functions, properties and methods have a
name and a value. In an object, that name is called a key.

An object cannot have two keys with the same name. This is
because keys are used to access their corresponding values.

The value of a property can be a string, number, Boolean, array, or
even another object. The value of a method is always a function.

EXAMPLE:
var hotel = {
name: "Quay",
room: 40,
booked: 25,
gym: true,
roomTypes: ['twin',double','suite'],
checkAvailability: function(){
    return this.rooms - this.booked;
}
};

Above you can see a hotel object. The object
contains the following key/value pairs:
PROPERTIES:     KEY         VALUE
                name        string
                rooms       number
                booked      number
                gym         Boolean
                roomTypes   array

METHODS: checkAvailability function

As you will see over the next few pages, this is just
one of the ways you can create an object.

Programmers use a lot of name/value pairs:
• HTML uses attribute names and values.
• CSS uses property names and values.

In JavaScript:
• Variables have a name and you can assign them a
value of a string, number, or Boolean.

• Arrays have a name and a group of values. (Each
item in an array is a name/value pair because it
has an index number and a value.)

• Named functions have a name and value that is a
set of statements to run if the function is called.

• Objects consist of a set of name/value pairs
(but the names are referred to as keys).


Sometimes you will want several objects to represent similar things.
Object constructors can use a function as a template for creating objects.First, create the template with the object's properties and methods.

A function called Hotel will be used as a template for creating new objects that represent hotels. Like all functions, it contains statements. In this case, they add properties or methods to the object.


The function has three parameters. Each one sets the value of a property in the object. The methods will be the same for each object created using this function.

The this keyword is used instead of the object name to indicate that the property or method belongs to the object that this function creates.

The name of a constructor function usually begins with a capital letter (unlike other functions, which tend to begin with a lowercase character).

Each statement that creates a new property or method for this object ends in a semicolon (not a comma, which is used in the literal syntax).

The uppercase letter is supposed to help remind developers to use the new keyword when they create an object using that function (see next page).


- An object is a series of variables and functions that represent something from the world around you.

- In an object, variables are known as properties of the object; functions are known as methods of the object.

- Web browsers implement objects that represent both the browser window and the document loaded into the browser window.


- JavaScript also has several built-in objects such as String, Number, Math, and Date. Their properties and methods offer functionality that help you write scripts.

- Arrays and objects can be used to create complex data sets (and both can contain the other).


The browser represents the page using a DOM tree.

DOM trees have four types of nodes: document nodes, element nodes, attribute nodes, and text nodes.

You can select element nodes by their id or cl ass attributes, by tag name, or using CSS selector syntax.

Whenever a DOM query can return more than one node, it will always return a NodeList.


From an element node, you can access and update its content using properties such as textContent and innerHTML or using DOM manipulation techniques.


An element node can contain multiple text nodes and child elements that are siblings of each other.