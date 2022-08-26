
# Reading Notes Class 06

## Problem Domain, Objects, and the DOM

### links
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics

#### Object basics

An object is a collection of related data and/or functionality. 
These usually consist of several variables and functions (which are called properties and methods when they are inside objects).
in JavaScript, creating an object often begins with defining and initializing a variable. 

An object looks like this:
```
const person = {
  name: ['Bob', 'Smith'],
  age: 32,
  bio: function () {
    console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old.`);
  },
  introduceSelf: function () {
    console.log(`Hi! I'm ${this.name[0]}.`);
  }
};
```

Each name/value pair must be separated by a comma, and the name and value in each case are separated by a colon. The syntax always follows this pattern:
```
const objectName = {
  member1Name: member1Value,
  member2Name: member2Value,
  member3Name: member3Value
};
```

The value of an object member can be pretty much anything. 
a number, array, function, boolean.

In our example above the first two items are data items, and are referred to as the object's properties. The last two items are functions that allow the object to do something with that data, and are referred to as the object's methods.

When the object's members are functions there's a simpler syntax. Instead of bio: function () we can write bio(). Like this:
```
const person = {
  name: ['Bob', 'Smith'],
  age: 32,
  bio() {
    console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old.`);
  },
  introduceSelf() {
    console.log(`Hi! I'm ${this.name[0]}.`);
  }
};
```

An object like this is referred to as an object literal

#### Dot notation

To access the properties of an object we use dot notation.
Example: 
```
person.age
person.bio()
```

#### Objects as object properties

An object property can itself be an object.
To access these items you just need to chain the extra step onto the end with another dot.
```
person.name.first
person.name.last
```

#### Bracket notation

Bracket notation provides an alternative way to access object properties.
```
person['age']
person['name']['first']
```

Dot notation is generally preferred over bracket notation
However there are some cases where you have to use brackets. For example, if an object property name is defined at runtime then you can't use dot notation to access the value, but you can pass the name as a variable inside brackets as shown with input below:
```
const person = {
  name: ['Bob', 'Smith'],
  age: 32
}
const input = prompt('Get name or age?')
console.log(person[input]
```

#### Setting object members

you can also set (update) the value of object members by declaring the member you want to set (using dot or bracket notation), like this:
```
person.age = 45;
person['name']['last'] = 'Cratchit';
```

Setting members doesn't just stop at updating the values of existing properties and methods; you can also create completely new members. 
```
person['eyes'] = 'hazel';
person.farewell = function() {
  console.log('Bye everybody!');
}
```

One useful aspect of bracket notation is that it can be used to set not only member values dynamically, but member names too. Let's say we wanted users to be able to store custom value types in their people data, by typing the member name and value into two text inputs. We could get those values like this:
```
const myDataName = nameInput.value;
const myDataValue = nameValue.value;
```
We could then add this new member name and value to the person object like this:
```
person[myDataName] = myDataValue;
```

Adding a property to an object using the method above isn't possible with dot notation, which can only accept a literal member name, not a variable value pointing to a name.

#### What is "this"?

The this keyword refers to the current object the code is being written inside — so in this case this is equivalent to person. So why not just write person instead?

The this keyword refers to the current object the code is being written inside — so in this case this is equivalent to person. So why not just write person instead?

```
const person1 = {
  name: 'Chris',
  introduceSelf() {
    console.log(`Hi! I'm ${this.name}.`);
  }
}

const person2 = {
  name: 'Deepti',
  introduceSelf() {
    console.log(`Hi! I'm ${this.name}.`);
  }
}
```

In this case, person1.introduceSelf() outputs "Hi! I'm Chris."; person2.introduceSelf() on the other hand outputs "Hi! I'm Deepti.", even though the method's code is exactly the same in each case. This isn't hugely useful when you are writing out object literals by hand, but it will be essential when we start using constructors to create more than one object from a single object definition

#### Introducing constructors



//////////////////////////////////////////////////////

## Introduction to the DOM

The Document Object Model (DOM) is the data representation of the objects that comprise the structure and content of a document on the web.

#### What is the DOM?

The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

The Document Object Model (DOM) representation allows it to be manipulated. As an object-oriented representation of the web page, it can be modified with a scripting language such as JavaScript.

All of the properties, methods, and events available for manipulating and creating web pages are organized into objects. For example, the document object that represents the document itself, any table objects that implement the HTMLTableElement DOM interface for accessing HTML tables, and so forth, are all objects.

#### DOM and JavaScript
The DOM is not a programming language, but without it, the JavaScript language wouldn't have any model or notion of web pages, HTML documents, SVG documents, and their component parts. The document as a whole, the head, tables within the document, table headers, text within the table cells, and all other elements in a document are parts of the document object model for that document. They can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

The DOM was designed to be independent of any particular programming language, making the structural representation of the document available from a single, consistent API.








How would you describe an object to a non-technical friend you grew up with?
An object is a way of storing data. Inside the object you can write a property which consists of a key value pair. essential the key is the name of the property and the value is its value. A simple example would be color as the key and blue as the value.

What are some advantages to creating object literals?
The advantages of using object literals to create objects include convenience, flexibility in declaration, and less code during declaration. 

How do objects differ from arrays?
Objects store a key and a value. 

Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.
if an object property name is defined at runtime

Evaluate the code below. What does the term this refer to and what is the advantage to using this?
The keyword this is refering the the property key name inside of the object in which this is written. So this.name is refering to name inside of dog object.

