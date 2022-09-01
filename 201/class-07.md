
# Object-Oriented Programming, HTML Tables


Reference Links:
https://github.com/codefellows/domain_modeling#domain-modeling
https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics#introducing_constructors
https://ui.dev/beginners-guide-to-javascript-prototype

### Domain Modelling
Domain modeling is the process of creating a conceptual model in code for a specific problem.
A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain.
An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domian model can verify and validate the understanding of a specific problem among various stakeholders.
it defines a vocabulary that can be used within and between both technical and business teams.

Domain modeling is the process of creating a conceptual model for a specific problem. And a domain model that's articulated well can 
verify and validate your understanding of that problem.

##### Here's some tips to follow when building your own domain models.

When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
Model its attributes with a constructor function that defines and initializes properties.
Model its behaviors with small methods that focus on doing one job well.
Create instances using the new keyword followed by a call to a constructor function.
Store the newly created object in a variable so you can access its properties and methods from outside.
Use the this variable within methods so you can access the object's properties and methods from inside.


Explain why we need domain modeling?

To gain an understanding of functionality.

### HTML table basics

A table is a structured set of data made up of rows and columns (tabular data).
When implemented correctly, HTML tables are handled well by accessibility tools such as screen readers, so a successful HTML table should enhance 
the experience of sighted and visually impaired users alike.

##### When should you NOT use HTML tables?
HTML tables should be used for tabular data — this is what they are designed for. Unfortunately, a lot of people used to use HTML tables to 
lay out web pages, e.g. one row to contain the header, one row to contain the content columns, one row to contain the footer, etc.

Layout tables reduce accessibility for visually impaired users
Tables produce tag soup
Tables are not automatically responsive

The content of every table is enclosed by these two tags : <table></table>.
The smallest container inside a table is a table cell, which is created by a <td> element ('td' stands for 'table data').
To stop this row from growing and start placing subsequent cells on a second row, we need to use the <tr> element
```
 <table>
   <tr>
    <td>Hi, I'm your first cell.</td>
    <td>I'm your second cell.</td>
    <td>I'm your third cell.</td>
    <td>I'm your fourth cell.</td>
  </tr>
 </table>
```
Each row needs to be wrapped in an additional <tr> element, with each cell contained in a <td>

<th></th> are special cells that go at the start of a row or column and define the type of data that row or column contains.

Table headers and cells have the colspan and rowspan attributes, which allow us to span multiply columns or rows. 
For example, colspan="2" makes a cell span two columns.
  
#### Styling without <col>
  
HTML has a method of defining styling information for an entire column of data all in one place — the <col> and <colgroup> elements. These exist because it 
can be a bit annoying and inefficient having to specify styling on columns — you generally have to specify your styling information on every <td> or <th> 
in the column, or use a complex selector such as :nth-child

#### Styling with <col>

Instead of doing this, we can specify the information once, on a <col> element. <col> elements are specified inside a <colgroup> container just below the opening <table> tag. We could create the same effect as we see above by specifying our table as follows:
```
 <table>
  <colgroup>
    <col>
    <col style="background-color: yellow">
  </colgroup>
  <tr>
    <th>Data 1</th>
    <th>Data 2</th>
  </tr>
  <tr>
    <td>Calcutta</td>
    <td>Orange</td>
  </tr>
  <tr>
    <td>Robots</td>
    <td>Jazz</td>
  </tr>
</table>
```
If we wanted to apply the styling information to both columns, we could just include one <col> element with a span attribute on it, like this:
```
 <colgroup>
  <col style="background-color: yellow" span="2">
</colgroup>
```
Just like colspan and rowspan, span takes a unitless number value that specifies the number of columns you want the styling to apply to. 
 
Why should tables not be used for page layouts?
 
Firstly tables are not very good for responsive layout, they really don't act in a responsive manner and there are many better layout solutions such as flex and grid. Secondly they reduce accessibility for visually impaired users.
 
List and describe 3 different semantic HTML elements used in an HTML <table>.
<tr> the tr element is used to encapsulate th and td elements and contain them in a table row.
<th> the th element is used to represent a table header cell where the content for each row/column are placed.
<td> the td element is used to represent a table data cell where the content for your data is placed. 

### Introducing constructors

Object literals work great when you only need to create one object. However these are considered inadequate/vebose when you have more than one object. 
Firstly we need to write each an every object and secondly making changes can lead to making the change for each object.

A better way is to use a constructor. A constructor is just a function called using the new keyword. When you call a constructor, it will:
1) create a new object
2) bind this to the new object, so you can refer to this in your constructor code
3) run the code in the constructor
4) return the new object

Constructors, by convention, start with a capital letter and are named for the type of object they create. So we could rewrite our example like this:
```
 function Person(name) {
  this.name = name;
  this.introduceSelf = function() {
    console.log(`Hi! I'm ${this.name}.`);
  }
}
```
 
To call Person() as a constructor, we use new:
 
```
const salva = new Person('Salva');
salva.name;
salva.introduceSelf();

const frankie = new Person('Frankie');
frankie.name;
frankie.introduceSelf();
```
 
#### You've been using objects all along

You have probably been thinking that the dot notation you've been using is very familiar. That's because you've been using it every time we've been working through an example that uses a built-in browser API or JavaScript object.
When you accessed the document object model using lines like this:
```
 const myDiv = document.createElement('div');
 const myVideo = document.querySelector('video');
```

You were using methods available on a Document object. For each webpage loaded, an instance of Document is created, called document, which represents the entire page's structure, content, and other features such as its URL. Again, this means that it has several common methods and properties available on it.
 
The same is true of pretty much any other built-in object or API you've been using — Array, Math, and so on.
 
Note that built in objects and APIs don't always create object instances automatically. As an example, the Notifications API — which allows modern 
browsers to fire system notifications — requires you to instantiate a new object instance using the constructor for each notification you want to fire. 
Try entering the following into your JavaScript console:
```
 const myNotification = new Notification('Hello!')
```

### Summary

you should now have a good idea of how to work with objects in JavaScript — including creating your own simple objects. You should also appreciate that 
objects are very useful as structures for storing related data and functionality — if you tried to keep track of all the properties and methods in our
person object as separate variables and functions, it would be inefficient and frustrating, and we'd run the risk of clashing with other variables and 
functions that have the same names. Objects let us keep the information safely locked away in their own package, out of harm's way.
In the next article we'll look at prototypes, which is the fundamental way that JavaScript lets an object inherit properties from other objects.
 
What is a constructor and what are some advantages to using it?

https://www.techopedia.com/definition/5656/constructor
A constructor is a special method of a class or structure in object-oriented programming that initializes a newly created object of that type. Whenever an 
object is created, the constructor is called automatically.

A constructor is like an instance method that usually has the same name as the class, and can be used to set the values of the members of an object, 
either to default or to user-defined values. However, although it resembles it, a constructor is not a proper method since it doesn’t have a return type. 
Instead of performing a task by executing code, the constructor initializes the object, and it cannot be static, final, abstract, and synchronized.
 
How does the term this differ when used in an object literal versus when used in a constructor?
 
In a constructor function this does not have a value. It is a substitute for the new object. The value of this will become the new 
object when a new object is created.
 
 
### Object Prototypes Using A Constructor

Objects are key/value pairs. The most common way to create an object is with curly braces {} and you add properties and methods to an object using dot 
notation.
 
```
let animal = {}
animal.name = 'Leo'
animal.energy = 10

animal.eat = function (amount) {
  console.log(`${this.name} is eating.`)
  this.energy += amount
}

animal.sleep = function (length) {
  console.log(`${this.name} is sleeping.`)
  this.energy += length
}

animal.play = function (length) {
  console.log(`${this.name} is playing.`)
  this.energy -= length
}
```` 

Now odds are in our application we'll need to create more than one animal. Naturally, the next step for this would be to encapsulate that logic inside of a function that we can invoke whenever we needed to create a new animal.
 
We'll call this pattern Functional Instantiation and we'll call the function itself a "constructor function" since it's responsible for "constructing" a 
new object.

#### Functional Instantiation
```
 function Animal (name, energy) {
  let animal = {}
  animal.name = name
  animal.energy = energy

  animal.eat = function (amount) {
    console.log(`${this.name} is eating.`)
    this.energy += amount
  }

  animal.sleep = function (length) {
    console.log(`${this.name} is sleeping.`)
    this.energy += length
  }

  animal.play = function (length) {
    console.log(`${this.name} is playing.`)
    this.energy -= length
  }

  return animal
}

const leo = Animal('Leo', 7)
const snoop = Animal('Snoop', 10)
```


 
 
 
 
Explain prototypes and inheritance via an analogy from your previous work experience.
NOTE: This is a very common front end developer interview question
 
 

 












