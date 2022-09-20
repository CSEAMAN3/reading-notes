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

Example functions changed to arrow functions

A named function with multiple parameters.
```
  function sum(a, b){
    return a + b
  }
  
<!-- convert to arrow function -->
<!-- remove the function key word, with an arrow function the function keyword is assumed -->
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
  
  
  
```

A named function with no parementers
```
  function randomNumber(){
    return Math.random
  }
```

An anonymous function - a function with no name. 
```
  document.addEventListener("click", function){
    console.log("click")
  }
```


