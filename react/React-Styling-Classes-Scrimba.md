# React-Styling-Classes-Scrimba

The Challenge is to create a Navigation inside our Header component.

```
import React from "react"
import ReactDOM from "react-dom"

/**
Challenge: 

- Add an `ul` inside the Header's `nav` and create
  the following `li`s: "Pricing", "About", & "Contact"
*/

function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" alt="logo" />
                <ul>
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```

This is not styled it does not look good!



### Styling in React

Styling in react is the same as in HTML however,

Instead of giving an element a class="hero-heading"

We give the element a className="hero-heading"

This is because react is taking these JSX elements and under the hood

turning them into native DOM elements.

The challenge is to now styles the page using CSS and className to:

Flexbox our ul nav.

index.js
```

import React from "react"
import ReactDOM from "react-dom"

/**
Challenge: 

- Add an `ul` inside the Header's `nav` and create
  the following `li`s: "Pricing", "About", & "Contact"
- Using flexbox, line up the nav items horizontally, and
  put them inline with the React logo.
*/

function Header() {
    return (
        <header>
            <nav className="header-nav">
                <img className="logo-img" src="./react-logo.png" width="40px" />
                <ul className="nav-items">
                    <li className="nav-list-item">Pricing</li>
                    <li className="nav-list-item">About</li>
                    <li className="nav-list-item">Contact</li>
                </ul>
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))

```

style.css
```

.logo-img{
    width: 40px;
    height: auto;
    display: block;
}

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-items {
    list-style: none;
    display: flex;
}

.nav-items > li {
    padding: 10px;
}


```











