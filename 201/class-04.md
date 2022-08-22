


# Reading notes: Class 04

#### Reference pages:
Hyperlinks
https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks

## Learn HTML
### Hyperlinks

What is a HyperLink: 
Hyperlinks allow us to link documents to other documents or resources, link to specific parts of documents, or make apps available at a web address.
Most web content can be converted in a link so when clicked upon or activated the browser goes to another url (web address).

#### Anatomy of a link

Basic links consist of a text wrapped between an achor tag with an href attribute to contain the web address: 
Example:
```
<a href="https://www.helloworld.com">hello world</a>.
```

The title attribute: Including a title attribute to your anchor element allows you to include supporting information about where the link will take you. So when you hover the link a tooltip will display what ever text you have included in your title attribute.
Example:
```
<a href="https://www.helloworld.com" title="The best place to introduce yourself to the world and get to know who else exists">Hello world</a>
```

#### Block level links

Almost any content can be made into a link - this inludes block level elements. For example an image.

```

<a href="https://www.helloworld.com">hello world
  <img src="globe-image.jpg" alt="Earth viewed from space.">
</a>

```

#### A quick primer on URLs and paths

A URL is a Uniform Resource Locator. It is a string of text that defines where something is on the web.
URLs use paths to find files. Paths specify where the file is in the filesystem.
When working locally with a website you will have one directory that contains the entire site. 
index.html will always be our homepage when working on a real website.
Your paths can link to:
The same directory
```
<a href="contacts.html">Contact page</a>

```
Moving down into subdirectories
```
<a href="projects/index.html">Contact page</a>

```
Moving back up into parent directories
```
<a href="../pdfs/project-brief.pdf">Contact page</a>

```
To go up a directory use two dots ..

#### Document Fragments

You can link to a specific part of an HTML document rather than just to the top of the page.
To do this you must assign an id to the element you're wanting to link to.
Usually it is best to link to a heading.
Example
```
<h2 id="mailing-address">Mailing Address</h2>

```

To link to that specific id we would include it at the end of the URL, preceded by a # symbol.
Example:
```
<p>Write to use at our
<a href="contacts.html#mailing-address">mailing address</a>
or contact us on 01603 545343.</p>

```
You can also link to a specific part of the same page by simply using the # symbol and the name of the id.
```

<p>The
<a href="#mailing-address">mailing address</a>
can be found at the bottom of this page.</p>

```

#### Absolute vs relative URLs

Absolute URL: Points to a location defined by its absolute location on the web, including protocol and domain name.
Example: If an index.html page is uploaded to a directory called projects that sits inside the root of a web server, and the website's domain is https://www.example.com, the page would be available at https://www.example.com/projects/index.html
An absolute URL will always point to the same location, no matter where it's used.

Relative URL: Points to a location that is relative to the file you are linking from, more like what we looked at in the previous section. For example, if we wanted to link from our example file at https://www.example.com/projects/index.html to a PDF file in the same directory, the URL would just be the filename — project-brief.pdf — no extra information needed. If the PDF was available in a subdirectory inside projects called pdfs, the relative link would be pdfs/project-brief.pdf (the equivalent absolute URL would be https://www.example.com/projects/pdfs/project-brief.pdf.)

#### Link best practices

Use clear link wording:
Screen reader users access links jumping around the links to find useful info.
Search engines use link text to index target files so include keywords in your link text.
visual readers skim text. 
Good link text
```
<p><a href="https://www.mozilla.org/firefox/">
  Download Firefox
</a></p>
```
Bad link text
```
<p><a href="https://www.mozilla.org/firefox/">
  Click here
</a>
to download Firefox</p>
```

Other tips:
Don't repeat the URL as part of the link text.
Don't say "link" or "links to" in the link text.
Keep your link text as short as possible.
Minimize instances where multiple copies of the same text are linked to different places. 

####Linking to non-HTML resources — leave clear signposts
Let's look at some examples, to see what kind of text can be used here:

```
<p><a href="https://www.example.com/large-report.pdf">
  Download the sales report (PDF, 10MB)
</a></p>

<p><a href="https://www.example.com/video-stream/" target="_blank">
  Watch the video (stream opens in separate tab, HD quality)
</a></p>

<p><a href="https://www.example.com/car-game">
  Play the car game (requires Flash)
</a></p>
```

















