# Reading notes: Class 05

#### Reference pages

Multimedia and embedding.
https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding

Using Images In HTML.
https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML

Common Image Types.
https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types

Choosing Image Formats
https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#choosing_an_image_format


## Readings: Images, Color, Text

<img> is the element used to place an image in HTML. The img element is a empty element meaning it is self closing - no content or closing tag.
The img element must include the src="" attribute. The src attribute contains a path pointing to the image you want to embed in the page, which can be a relative or absolute URL, in the same way as href attribute values in <a> elements.

 Examples
 if your image is called dinosaur.jpg, and it sits in the same directory as your HTML page, you could embed the image like so:

 ```
  
  <img src="dinosaur.jpg" alt="Dinosaur">
  
 ```
 If the image was in an images subdirectory, which was inside the same directory as the HTML page, then you'd embed it like this:
 
```
  
  <img src="images/dinosaur.jpg" alt="Dinosaur">
  
```

You could embed the image using its absolute URL, for example:
  
```
  
  <img src="https://www.example.com/images/dinosaur.jpg" alt="Dinosaur">
 
```

You could embed the image using its absolute URL, But this is pointless, as it just makes the browser do more work, looking up the IP address from the DNS server all over again, etc. You'll almost always keep the images for your website on the same server as your HTML.
  

#### Alternative text
 
The alt="" attribute is used to provide a textual description of the image, for use in situations where the image cannot be seen/displayed or takes a long time to render because of a slow internet connection.

Example
```
<img src="images/dinosaur.jpg"
     alt="The head and torso of a dinosaur skeleton;
          it has a large head with long sharp teeth">
```
To test your alt text is working purposly enter the file name with a typo and render the page.
 
alt text is important for:
User is visually impaired, and is using a screen reader
The spelling of the file or path name might be wrong.
The browser doesn't support the image type.
You may want to provide text for search engines to utilize; for example, search engines can match alt text with search queries.
Users have turned off images to reduce data transfer volume and distractions. 

#### What should you write in your alt attribute
It depends on why the image is there. What will you lose if your image doesn't show up:

Decoration. You should use CSS background images for decorative images, but if you must use HTML, add a blank alt="". If the image isn't part of the content, a screen reader shouldn't waste time reading it.
 
Content. If your image provides significant information, provide the same information in a brief alt text – or even better, in the main text which everybody can see. Don't write redundant alt text. How annoying would it be for a sighted user if all paragraphs were written twice in the main content? If the image is described adequately by the main text body, you can just use alt="".
 
Link. If you put an image inside <a> tags, to turn an image into a link, you still must provide accessible link text. In such cases you may, either, write it inside the same <a> element, or inside the image's alt attribute – whichever works best in your case.
 
Text. You should not put your text into images. If your main heading needs a drop shadow, for example, use CSS for that rather than putting the text into an image. However, If you really can't avoid doing this, you should supply the text inside the alt attribute. 
 
#### Width and height
You should use an image editor to put your image at the correct size before putting it on your webpage

#### Image titles
You can also add title attributes to images, to provide further supporting information if needed. 
This gives us a tooltip on mouse hover, just like link titles.
However, this is not recommended.

#### Annotating images with figures and figure captions
Use the HTML <figure> and <figcaption> elements. These are created for exactly this purpose: to provide a semantic container for figures, and to clearly link the figure to the caption.
 
```
<figure>
  <img src="images/dinosaur.jpg"
       alt="The head and torso of a dinosaur skeleton;
            it has a large head with long sharp teeth"
       width="400"
       height="341">

  <figcaption>A T-Rex on display in the Manchester University Museum.</figcaption>
</figure>
```
The <figcaption> element tells browsers, and assistive technology that the caption describes the other content of the <figure> element.
A figure could be several images, a code snippet, audio, video, equations, a table, or something else.

### CSS background images

use CSS to embed images into webpages (and JavaScript, but that's another story entirely). The CSS background-image property, and the other background-* properties, are used to control background image placement.
 
This example shows a background image added to all pragaraphs on a page.
```
 p {
  background-image: url("images/dinosaur.jpg");
}
```
CSS background images are for decoration only. If you just want to add something pretty to your page to enhance the visuals, this is fine.
such images have no semantic meaning at all. They can't have any text equivalents, are invisible to screen readers, and so on. This is where HTML images shine!
 
###Image file type and format guide

Please see link
https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types






#### HTML Media Questions

1) What is a real world use case for the alt attribute being used in a website?
 If the image does not load on a website the alt attribute content will be displayed.
 
2) How can you improve accessibility of images in an HTML document?
 Use the alt tags so screen reader can access them and describe the images to the user.
 Use figure and figcaption elements. 
 
3) Provide an example of when the figure element would be useful in an HTML document?
 To semantically link the image to its caption for screen readers. 
 
4) Describe the difference between a gif image and an svg image, pretend you are explaining to an elder in your community.
 A gif is designed for basic images and animations, an SVG allows simple graphics to be scalable as the computer will mathmatically work it out.
 
5) What image type would you use to display a screenshot on your website and why?
The best file type for a screenshot would be a jpeg. This is becuase it doesn't have a transparent background or other memory intensive files. You would choose PNGs for graphics, files with transparent backgrounds, and other images where clarity and color vibrancy are important.






