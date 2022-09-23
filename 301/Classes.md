# Classes

###### Reference links

https://www.youtube.com/watch?v=9Yc5J3Ap9-4




### Objects and Inheritance

Javascript objects use prototype-based inheritance. Classes is logically similar but its implementation is different.

Loosely described - when methods or properties are attached to object's prototype they become available for use on that 

object and its decendants but it is not directly attached to them.

When you use class and extends keyword internally JavaScript will still use prototype-based inheritance.

However it will simplify the syntax.

While classes are easier to use it is still i,portant to understand how prototype inheritance works as it is at the

core of the language design.

### ES6 Classes and Data Modeling - youtube video

Understand the functions and process of data modelling.

When we talk about a data model we are talking about modelling real world objects.

For example: A person

A person has attributes - hair color, height, weight, location ect

A person has behaviours - walk(), speak(), drive() ect

attributes are nouns - things about you

behaviours are verbs - things you can do - in code these are methods things you can do!

Sub classing - A person is a good example, everyone is a person but a child has different features than an adult.

In which case you could make a child which has differnet features but also gets all the features of a person.

This is called inheritance.

Example: 

```

// lets make an animal class using a constructor function

const Animal = function(name, legs){
 //when we instantiate a new animal we'll take the name and the legs and declare them as internal properties.
 // this will be your attributes.

  this.name = name
  this.legs = legs
   
}

// for our behaviours we'll use a prototype

Animal.prototype.walk = function(){
  this.isWalking = true
}

// now we'll create a new instance of an animal

let puppy = new Animal("blake", 4)

```

If we console.log(puppy)

It will log Animal {name: "blake", legs: 4}

if before the console.log we parse the walk prototype to the puppy like:

```

let puppy = new Animal("blake", 4)
puppy.walk()
console.log(puppy)

```

Then it will log Animal {name: "blake", legs: 4, isWalking: true}

The prototype method allowed us to add this new behaviour.

Next we'll add an eat function as a method inside our constructor:

```

// lets make an animal class using a constructor function

const Animal = function(name, legs){
 //when we instantiate a new animal we'll take the name and the legs and declare them as internal properties.
 // this will be your attributes.

  this.name = name
  this.legs = legs
  
 // new method added to Animal constructor
   this.eat = function(){
    this.isEating = true
   }
}

// for our behaviours we'll use a prototype

Animal.prototype.walk = function(){
  this.isWalking = true
}

// now we'll create a new instance of an animal

let puppy = new Animal("blake", 4)

```

If we console.log(puppy)

It will log Animal {name: "blake", legs: 4}

if before the console.log we parse the walk prototype to the puppy like:

```

let puppy = new Animal("blake", 4)
puppy.walk()
// we will call the method on our puppy
puppy.eat()
console.log(puppy)

```
now in the console we will have:

```
Animal {
  name: "blake",
  legs: 4,
  eat: [function],
  isWalking: true,
  isEating: true
  }
  
```
The two properties (eat and walk) were set on puppy by the invocation of those methods on this instance of an animal.

Notice how eat is a property / attribute that value is a function.

The eat method as its in the constructor is part of the instance. So each time an instace is created it will have this method.

If we have thousands of instances thats a lot of memory and work. It's very inefficient.

The walk method is a protoype function. This means anything that gets created as an instance of an animal gets to share what

ever the prototype is. Prototype is like a blueprint, so any animal has access to the walk method as though it was it's own 

but it doesn't have to have the walk method as part of it's first class properties / attributes. This makes the code much more 

memory efficient. We can share behaviours rather than owning behaviours.

Now to create sub classes:

Lets make a new constructor - A dog:

```
const Dog = function(name, legs){
  //DOG is so much like an Animal we actually want to say is in this contructor function I want Dog to be Animal
  // remember this keyword inside of a constructor function is a pointer or reference to the instance we created. 
  // We are saying call the animal constructor with this Which we are about to create and send along name and legs.
  
  Animal.call(this, name, legs)
   
}
```

Additionally we want to make sure Dog has all the attributes of an animal.

We want to make sure this dog can also eat and also walk.

So we need to recreate the Dog prototype as a mirror of the Animal prototype.

```
  Dog.prototype = Object.create(Animal.prototype)
```

Now instead of making puppy a new instance of animal make it a new instance of a Dog.

```
let puppy = new Dog("blake", 4)
puppy.walk()
puppy.eat()
console.log(puppy)
```
The console log will look exactly the same, infact it is exactly the same!

We have made a new Dog

The Dog creates it self out of an Animal. Essentially Dog calls the Animal constructor.

It then copies the Animal prototype.

This is painfull it's very heavy to manage.

### ES6 JavaScript Syntax Classes

This sytax can rewrite the code above however it is a lot easier to understand and consume!

The re-write: 

```
//We start by making a new class

class Animal {

//The constructor for the class takes in a name and legs

  constructor(name, legs){
    this.name = name
    this.legs = legs
  }
  
//This class will also have a few methods. We just declare a method in a class by its name.

  walk(){
    this.isWalking = true
  }
  
// we will also create the eate method

  eat(){
   this.isEating = true
  }
  
}

// we'll make a new instance of Animal outside of the class

let rosie = new Animal("rosie", 4)

```

Now if we console.log(rosie)

It will log: Animal {name: rosie, legs: 4}

Walk and eat automatically become prototypes. 

So if we call rosie.walk() and rosie.eat()

before the conole.log(rosie)

```

let rosie = new Animal("rosie", 4)
rosie.walk()
rosie.eat()
console.log(rosie)

```
The console will log Animal with the values of the prototypes

Animal { name: "rosie", legs: 4, isWalking: true, isEating: true}

Next lets make a sub class lets make a Dog this time we'll add a new method to Dog and some new behaviours.

```

class Dog extends Animal {

}

```

using the extends keyword now allows dog to have all the properties of animal

So if we chnaged rosie to a new instance of Dog:

let rosie = new Dog("rosie", 4)
rosie.walk()
rosie.eat()
console.log(rosie)

It will console log the same however it will be Dog not Animal.

If we open up the detail in the console the hierarcy will show:

Dog is an Animal it has its own constructor and has inherited the methods from the parent class of Animal.

Now lets add a methods to dog called speak and invoke the speak method on rosie.

```

class Dog extends Animal {

  speak(){
    console.log("woof!")
  }
 
}

let rosie = new Dog("rosie", 4)
rosie.walk()
rosie.eat()
console.log(rosie)
rosie.speak()

```

So now we have made a Dog class which is an extention of Animal class which has it own special properties / attributes

that only instances of Dog can do but it can still participate in everything an Animal can do!

You automatically get everything the parent constructor can do. If you need the Dog sub class to add something in the constructor.

You would call the parent class inside the Dog sub class like so:

```

class Dog extends Animal {

// we create the constructor with the extra parameter
// then inside to declare this is type super
// Super invokes the constructor on the parent class
// we then set the value of this.furType to furType so it will be what we parse in.

  constructor(name, legs, furType) {
    super(name, legs)
    this.furType = furType
  }
  
  speak {
    console.log("Woof!")
  }
 
}

// If we create a new instance of Dog called rosie set the argument for furType to "Short hair"

let rosie = new Dog("rosie", 4, "Short Hair")
rosie.walk()
rosie.eat()
console.log(rosie)
rosie.speak()

```

The console.log will show:

Dog {
  name: "rosie",
  legs: 4,
  furType: "Short Hair",
  isWalking: true,
  isEating: true
 }
woof!

```

### Scrimba











