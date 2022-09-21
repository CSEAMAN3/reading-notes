# Arrow Functions

###### Arrow functions reference links

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions

https://caniuse.com/?search=arrow%20functions

### Arrow function expressions

An arrow function expression is a compact alternative to a traditional function expression.

It is limited and can't be used in all situations.

Differences between arrow functions and traditional functions, as well as some limitations:

Arrow functions don't have their own bindings to this, arguments or super, and should not be used as methods.

Arrow functions don't have access to the new.target keyword.

Arrow functions aren't suitable for call, apply and bind methods, which generally rely on establishing a scope.

Arrow functions cannot be used as constructors.

Arrow functions cannot use yield, within its body.

#### Example functions changed to arrow functions

A named function with multiple parameters.
```
  function sum(a, b){
    return a + b
  }
  
<!-- convert to arrow function -->
<!-- remove the function key word. With an arrow function the function keyword is assumed -->
<!-- We need to assign the function to a variable either let or const -->
<!-- Set the variable = to the parentheses -->
<!-- next add the arrow to denote this is a function followed by the body syntax of the function in curly braces -->

let sum2 = (a, b) => {
  return a + b
}  

<!-- We can simplify further -->
<!-- We can remove the return and the curly braces -->
<!-- place the body syntax on the same line -->
<!-- the arrow function then assumes anything following the arrow is to be returned -->

let sum2 = (a, b) => a + b

```

A named function with one parameter.
```
  function isPositive(number){
    return number >= 0    
  }
  
<!-- Again we remove the function keyword and set isPositive to a variable -->
<!-- Set the variable = to the parentheses (number) -->
<!-- Include the arrow after the parentheses -->

let isPositive = (number) => {
    return number >= 0    
  }
  
<!-- again we can reduce this further by removing the return and the curly braces and placing onto one line -->

let isPositive2 = (number) => number >= 0

<!-- Also, when we only have 1 parameter, we can remove the parentheses from around the parameter -->

let isPositive3 = number => number >= 0

```

A named function with no parementers
```
  function randomNumber(){
    return Math.random
  }

<!-- Again remove the keyword function  replace it with a variable -->
<!-- assign it equal to empty parentheses -->
<!-- place the arrow after the parentheses followed by the curly braces and the body syntax of the function -->

  let randomNumber2 = () => {
    return Math.random
  }
  
<!-- Again we can remove the return and the curly braces then place eveything onto one line -->

let randomNumber3 = () => Math.random
```

An anonymous function - a function with no name. This is where arrow functions really shine!
```
  document.addEventListener("click", function(){
    console.log("click")
  })
  
<!-- We remove the keyword function and add our arrow function after the parentheses -->

  document.addEventListener("click", () => {
    console.log("click")
  })
  
<!-- we can also put this onto one line by removing the curly braces-->

  document.addEventListener("click", () => console.log("click"))

```

To summerise:

With one parameter the parentheses are not needed. 

Simple expression return on one line the word "return" is not needed

param => expression

Multiple parameters require parentheses.

(param1, param2) => expression

Multiline statements require body braces and return

param => {
  const a = 1
  return a + param
}

Multiple parameters require parenthese and Multiline statements require body braces and return

(param1, param2) => {
  const a = 1
  return a + param1 + param2
}





### Arrow functions Re-defining the this keyword

What really makes arrow funcitons important is that they re-define the this keyword inside of them as opposed to normal functions.






