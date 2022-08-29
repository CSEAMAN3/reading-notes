

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














