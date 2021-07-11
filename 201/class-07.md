Domain modeling is the process of creating a conceptual model for a specific problem. And a domain model that's articulated well can verify and validate your understanding of that problem.

Here's some tips to follow when building your own domain models.

1- When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.

2- Model its attributes with a constructor function that defines and initializes properties.

3- Model its behaviors with small methods that focus on doing one job   well.

4- Create instances using the new keyword followed by a call to a constructor function.

5- Store the newly created object in a variable so you can access its properties and methods from outside.

6- Use the this variable within methods so you can access the object's properties and methods from inside.

This is object-oriented programming in JavaScript at its most fundamental level.

1- The new keyword instantiates (i.e. creates) an object.

2- The constructor function initializes properties inside that object using the this variable.

3- The object is stored in a variable for later use.

EXAMPLE:
Generate random numbers

var EpicFailVideo = function(epicRating, hasAnimals) {
  this.epicRating = epicRating;
  this.hasAnimals = hasAnimals;
}

EpicFailVideo.prototype.generateRandom = function(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

var parkourFail = new EpicFailVideo(7, false);
var corgiFail = new EpicFailVideo(4, true);

console.log(parkourFail.generateRandom(1, 5));
console.log(corgiFail.generateRandom(1, 5));

- The table element is used to add tables to a web page.

- A table is drawn out row by row. Each row is created with the <tr> element

- Inside each row there are a number of cells represented by the <td> element (or <th> if it is a header).

- You can make cells of a table span more than one row or column using the rowspan and colspan attributes.

- For long tables you can split the table into a <thead>, <tbody>, and <tfoot>.

A table represents information in a grid format. Examples of tables include financial reports, TV schedules, and sports results.

Grids allow us to understand complex data by referencing information on two axes.

Each block in the grid is referred to as a table cell. In HTML a table is written out row by row.

EXAMPLE:
(' <!-- html><head><title>Tables</title></head><body><table><thead>
<tr><th></th><th scope="col">Home starter hosting</th>
<th scope="col">Premium business hosting</th></tr>
</thead><tbody><tr><th scope="row">Disk space</th>
<td>250mb</td><td>1gb</td>
</tr><tr> <th scope="row">Bandwidth</th>
<td>5gb per month</td>
<td>50gb per month</td></tr>
<!-- more rows like the two above here -->
</tbody><tfoot>
<tr><td></td><td colspan="2">Sign up now and save 10%!</td>
</tr></tfoot></table>
</body></html -->')

An object is a series of variables and functions that represent something from the world around you.

In an object, variables are known as properties of the object; functions are known as methods of the object.

Web browsers implement objects that represent both the browser window and the document loaded into the browser window.

JavaScript also has several built-in objects such as String, Number, Math, and Date. Their properties and methods offer functionality that help you write scripts.


Arrays and objects can be used to create complex data sets (and both can contain the other).

CREATE THE OBJECT, THEN ADD PROPERTIES & METHODS

In both of these examples, the object is created on the first line of the code sample. The properties and methods are then added to it afterwards.


EXAMPLE:
LITERAL NOTATION
var hotel = {}
hotel .name= 'Quay';
hotel .rooms = 40;
hotel.booked = 25;
hotel.checkAvailabil ity =function()
return this . rooms - this .booked;
} ;



Once you have created an object, the syntax for adding or removing any properties and methods from that object is the same.


EXAMPLE:
OBJECT CONSTRUCTOR NOTATION
var hotel = new Object();
hotel.name = 'Quay';
hotel .rooms = 40 ;
hotel . booked= 25;
hotel.checkAvailability =function()
return this .rooms - this .booked;
} ;




CREATING AN OBJECT WITH PROPERTIES & METHODS

LITERAL NOTATION
A colon separates the key/value pairs. There is a comma between each key/value pair.

EXAMPLE:
var hotel = {
name: 'Quay' ,
rooms: 40,
booked: 25,
chec kAvailability: function() {
return this.rooms - this .booked;
}
} ;


OBJECT CONSTRUCTOR NOTATION
The function can be used to create multiple objects. The this keyword is used instead of the object name.


EXAMPLE:
function Hotel(name, rooms, booked) {
this.name = name;
th i s.rooms = rooms;
this.booked = booked;
this.checkAvailability = functio n()
return this . rooms - this.booked;
} ;
var quayHotel =new Hotel('Quay', 40 , 25);
var parkHotel =new Hotel('Park', 120, 77);



