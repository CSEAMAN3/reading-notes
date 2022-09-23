# React - organize-components Scrimba

###### reference link

Good link to understand import / export in ES6

https://www.digitalocean.com/community/tutorials/js-modules-es6

## organize-components

A good convention could be to call any file you create that will house a react componnet will start with a capital letter.

Call it the same as the component itself.

Remember for any file created that will need to make sense of JSX you will need to:

```
import React from "react"

```

If you are creating a file to be used in another file you will need to export it.

two ways.

export defualt Header at the bottom as Header is the only component inside the file.

```
import React from "react"

function Header() {
    return (
        <header>
            <nav className="nav">
                <img src="./react-logo.png" className="nav-logo" />
                <ul className="nav-items">
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}

export default Header

```

Alternatively

infront of the component name where it is created we can type export default.

```

import React from "react"

export default function Header() {
    return (
        <header>
            <nav className="nav">
                <img src="./react-logo.png" className="nav-logo" />
                <ul className="nav-items">
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}

```

once exported we can import into another file using import

import Header from "./Header"

```

import React from "react"
import ReactDOM from "react-dom"
import Header from "./Header"

```

Note: Make sure the imported file is spelt correctly the same as the file name you have created which may or may not be the same

as the component inside the file.

###### Challenge - move the Footer and MainContent components into their own files.

Header.js File

```

import React from "react"

export default function Header() {
    return (
        <header>
            <nav className="nav">
                <img src="./react-logo.png" className="nav-logo" />
                <ul className="nav-items">
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}

```

Footer.js File

```

import React from "react"

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

export default Footer

```

MainContent.js File

```

import React from "react"

export default function MainContent() {
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

```

index.js file

```

import React from "react"
import ReactDOM from "react-dom"
import Header from "./Header"
import Footer from "./Footer"
import MainContent from "./MainContent"

/**
Challenge: move the Footer and MainContent components
into their own files.
*/

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

We have used the two different export methods on the files. Note - either could have been used. 

We have imported each file using the import method at the top of index.js






