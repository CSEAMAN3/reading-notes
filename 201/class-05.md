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
  

#### Reference pages























