
# React - Custom Components

In react we can create our own custom components.

A function that returns react elements is considered in react a compononent.

Our component names need to use pascal case. Capatalise the first letter of the name of the component.

```

function TemporaryName() {

}

```

Secondly instead of calling the function with parentheses like we are used to.

We need to wrap it in angle brackets similar to an HTML element.

```

ReactDOM.render(<TemporaryName />, document.getElementById("root"))

```

## React - Custom Components part 2 Challenge

Note: Inside the component make sure you have one parent component/element.

You could either wrap your elements in a fragment tag <> elements and content here </>

Or simply wrap it in a div tag 


Finished code to challenge

```
import React from "react"
import ReactDOM from "react-dom"

function Page() {
    return (
        <div>
            <header>
                <nav>
                    <img src="./react-logo.png" width="40px" />
                </nav>
            </header>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
            <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
            </footer>
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))

```

## Custom Components Quiz

Quiz!

1. What is a React component?

###### Scrimba Answer

A function that returns React elements.

React elements are the objects that get created when we return JSX.

Those objects are then turned into real DOM elements that people can see on the screen.

Sometimes people will refer to this as UI user interface.

Just like any javascript function a component can be used reused over and over.

###### Google Answer

Components are independent and reusable bits of code.

They serve the same purpose as JavaScript functions, but work in isolation and return HTML. 

Components come in two types: 

Class components and Function components.



2. What's wrong with this code?
```
function myComponent() {
    return (
        <small>I'm tiny text!</small>
    )
}
```

Any componnents you create must use pascal case. The first letter of the name needs to be capatalised. MyComponent.




3. What's wrong with this code?
```
function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
}

ReactDOM.render(Header(), document.getElementById("root"))
```

Instead of calling the function with parentheses like you would in Javascript.

We need the call the function with angled brackets surrounding the component name:

```

ReactDOM.render(<Header />, document.getElementById("root"))

```

In react this is the correct way to call your component.


## Parent/Child components

Challenge Was to create a seperate component called Header and return the header html / JSX.

```

import React from "react"
import ReactDOM from "react-dom"

/**
Challenge: 

- Move the `footer` into its own component called "Footer" 
  and render that component inside the Page component.
- Move the `h1` and `ol` together into another component
  called "MainContent" and render inside Page as well.
*/

function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
            <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
            </footer>
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))

```

The next challenge was to create components for the main and the footer and render them onto the page.

```

import React from "react"
import ReactDOM from "react-dom"

/**
Challenge: 

- Move the `footer` into its own component called "Footer" 
  and render that component inside the Page component.
- Move the `h1` and `ol` together into another component
  called "MainContent" and render inside Page as well.
*/

function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
}

function Main(){
    return (
        <main>
            <h1>Reasons I'm excited to learn React</h1>
                <ol>
                    <li>It's a popular library, so I'll be 
                    able to fit in with the cool kids!</li>
                    <li>I'm more likely to get a job as a developer
                    if I know React</li>
                </ol>
        </main>
    )
}

function Footer(){
    return (
        <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <Main />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))

```

So to explain the parent / child component relationship

Page has become the parent component to the Header, Main and Footer Components as they have been nested inside the Page Components.

Header, Main and Footer are the child components inside the parent component Page.








