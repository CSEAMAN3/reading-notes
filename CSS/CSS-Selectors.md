

# CSS



## Understanding using the +, > and ~ symbols in CSS selectors.
link - https://levelup.gitconnected.com/understanding-use-of-the-and-symbols-in-css-selectors-95552eb436f5

There are four different combinators in CSS:
Descendant Selector (space)
Child Selector (>)
Adjacent Sibling Selector (+)
General Sibling Selector (~)
Let us see how we can use different symbols (+, >, and ~) in CSS selectors and their differences.

Here is some starter HTML

```
<div class="container">
  <p>Apple</p>
  <div>
    <p>An apple a day keeps doctor away!</p>
  </div>
  <p>Banana</p>
  <p>Cherry</p>
</div>
```
### The Space

```
div.container p {
 font-size: 20px;
}
```
As you can see in the code above, there is a space between div.container and p. It is called the Descendant selector. 
It will target all <p> tags within container div. That is, all <p> elements that are children of #container at any depth.

  
### The ‘>’ Symbol

This is called the child selector. CSS rules will be applied to elements which are direct children of the particular element.

```
  div.container > p {
  border-bottom: 1px dashed black;
}
```

<img width="561" alt="Screenshot 2022-08-29 at 10 23 45" src="https://user-images.githubusercontent.com/88540603/187169511-b88344c4-3694-487e-bd61-7141d3bd5f9b.png">

It will target (represented with a green dot in HTML image) all the <p> tags which are immediate children of container <div>, but the children of children will not be selected (represented with the red dot).
  

### The ‘+’ Symbol
  
This is Adjacent Sibling Selector. It selects all elements that are the adjacent siblings of a specified element.
Sibling elements must have the same parent element, and “adjacent” means “immediately following”.

```
  div + p {
  background-color: yellow;
}
```
  
<img width="560" alt="Screenshot 2022-08-29 at 10 29 01" src="https://user-images.githubusercontent.com/88540603/187170458-2673ed59-29ea-4ea2-8367-497544d6e651.png">
  
In our example, it will target to Banana only because the <p> tag comes just after the <div> tag. 


### The ‘~’ Symbol
  
It is General Sibling Selector and similar to Adjacent Sibling Selector. It selects all next elements that are siblings of a specified element.

The following example selects all next <p> elements that are siblings of <div> elements.
  
```
  div ~ p {
  background-color: yellow;
}
```

<img width="561" alt="Screenshot 2022-08-29 at 10 33 30" src="https://user-images.githubusercontent.com/88540603/187171608-ddd167fa-5214-4798-a63b-9e91ed0b960a.png">

It will target Banana and Cherry <p> tags.







