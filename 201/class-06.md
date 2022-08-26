
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

In our example above












How would you describe an object to a non-technical friend you grew up with?

What are some advantages to creating object literals?

How do objects differ from arrays?

Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.

Evaluate the code below. What does the term this refer to and what is the advantage to using this?

