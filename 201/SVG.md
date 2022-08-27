
# How to Optimize and Export SVGs in Adobe Illustrator

#### reference website
https://www.sitepoint.com/crash-course-optimizing-and-exporting-svgs-in-adobe-illustrator/

When you begin working with SVG, it is important to understand how to create, export, and optimize your SVG files for the browsers that 
will render them.

However, before we start, you need to understand one thing clearly. The optimization of an SVG file begins with its creation and 
continues all the way to export. Like any HTML web page, it’s difficult to fix a poorly built SVG file after it’s completed.

Sure, you can use optimization tools after export, but this automated approach can break your file in all kinds of unexpected ways.
Having a solid working knowledge of good manual SVG optimization concepts will hold you in good stead from the start.

This is exactly what you will learn today.

### Set the Correct Color Space

Illustrator — as most vector illustration software — was originally designed for print production, and therefore its color space is 
set to CMYK by default. RGB is much more appropriate for web and screen use, and has a wider gamut (range of colors) than CMYK. 
So, when you create new document, make sure the color mode is set to RGB.

### Give your drawing a proper structure

An SVG file is not like a regular bitmap image — a grid of pixels. It’s a text document that has a specific structure.

Like an HTML document, you can select and manipulate individual elements separately. To do this, you’ll need to use their names as 
a reference. I’ve found it’s always much easier to create these labels during visual editing in Illustrator, rather than later.

For that reason, it’s important to give a meaningful name to each graphic element as you make it. Here is what you need to know when 
you create a graphic in Illustrator:

1) Illustrator Layers and Layers Groups names are used as IDs for SVG groups

2) Illustrator Symbols names are used as IDs for SVG symbols

3) Illustrator Graphic Styles names are used as CSS classes

### Simplify your shapes whenever possible

The shapes in an SVG drawing are described with coordinate points. The more points a drawing has, the larger the file size and more 
difficult it is to edit and maintain. Creating small, efficient files makes your life easier later.

To solve this issues, you need to use the fewest possible number of points to create the shapes you need. 
This can be achieved in several ways.

### Use Primary SVG shapes instead of SVG paths whenever possible

Using simple elements like line, rect, and circle has some significant advantages.

Firstly, simple shapes are much more readable for humans – it’s self-evident that a circle is a circle when we see it in our SVG code, 
but the code for a path can be anything until we see it render.

Secondly, simple shapes almost always produce smaller file sizes and less code, which make them easier for maintain and edit. 
You can also control them more easily with their direct attributes such as x, y, cx, cy, instead of point coordinates as it is with paths.

### Simplify your paths

A path is nothing more than an array of coordinate points. To simplify a path means to cut out some of its points, which will lead to 
less path data and smaller file size. To do so you can use Object > Path > Simplify… command or Warp Tool. In both cases, the main point 
is to reduce the path’s points maximally without loosing the quality of visual appearance.

### Decide whether to convert text to paths

In SVG graphics, text is a standalone element and as such it is searchable, accessible, and easily re-editable. This is a valuable 
quality for text to have. However, if you want to guarantee your text looks exactly the way you designed it everywhere, your end-user 
will need to have access to the correct fonts. 
This means choosing a common fonts — which limits your creativity — or providing a web font.

If precise text rendering is more important than editability — for example, in a logo — you can convert it into paths by using 
Type > Create Outlines command or by setting this option in the export panel as you’ll see later on.

Bear in mind that convert a lot of text to paths, the file size can increase drastically – so think carefully before converting.

### Use ‘SVG filters’ in preference to Illustrator or Photoshop Filter Effects

Illustrator offers a set of SVG Filters that are applied live in the browser (Effect > SVG Filters). While Illustrator or Photoshop 
Effects are always permanently ‘baked into’ your raster images embedded inside the SVG, SVG filters can be changed or removed at any
time with a few keystrokes.

You can also create re-usable filters and/or edit them via Apply SVG Filter dialog.

### Fit artboard to drawing

If you want your SVG to be displayed predictably, it’s good habit to always to trim your artboard to the drawing before. 
The artboard dimensions are the dimensions of the exported SVG viewport, and any white space in the artboard will be generated 
as white space inside the viewport.

Depending on situation you can use Object > Artboards > Fit to Artwork Bounds or Object > Artboards > Fit to Selected Art command.

### Exporting SVG in Illustrator

Since version 2015.2, Illustrator CC has shipped with a new export panel created for web-optimized SVG files. 
In this section we’ll see how to use it.

When your graphic is ready for production, select File > Export > Export As… command, then select SVG as option for the file type 
and hit Export button. You should see the following panel:

<img width="403" alt="Screenshot 2022-08-27 at 20 59 24" src="https://user-images.githubusercontent.com/88540603/187046168-ac8c538b-340f-4cf8-a4c9-0d4e0c6c98f7.png">

### Styling

There are three way to style your SVG and they are presented in the first dropdown list.

1) The first is to use internal CSS (i.e. a <style> block), which is generally considered the best option following the Separation of 
Concerns principle.
2) The second method is to use inline CSS styles (i.e. ).
3) The third method is to use SVG presentation attributes.

In the image below, you can see the difference between these three options.

<img width="521" alt="Screenshot 2022-08-27 at 21 06 30" src="https://user-images.githubusercontent.com/88540603/187046375-3bbd7a14-c253-45f4-bc82-98d77fd86039.png">

### Font
  
If you want to convert your text to outlines, here you can instruct Illustrator to do so. If you want to preserve your text
editability, then select SVG option. Outlined text gives you complete visual control of your typography, but at a significant cost 
- file sizes blow out and text loses editability and searchability.
  
Note: SVG fonts will be removed from SVG 2 and is considered as a deprecated feature with support being removed from browsers.
  
### Images

Here you can choose how you treat any raster images in your SVG. You can choose to keep them as external files, or to embed them into 
the SVG as DataURIs. Often Link is a useful choice as it makes the parent SVG file dramatically smaller and, as such, far more      
manageable in your code editor.
  
However, the Embed option does have one great, overriding advantage: embedded images can never become unlinked/separated from their    
‘parent SVG’. SVGs using linked resources will show the missing image icon the first time the SVG is downloaded, uploaded or moved 
without its ‘child images’.
  
Keep this in mind if you require portability in your SVG.

As a general rule, you’ll avoid many future headaches if you can simply avoid using pixel-based graphics in your SVGs whenever you can.
  
  
  
  
  
  
  
  






