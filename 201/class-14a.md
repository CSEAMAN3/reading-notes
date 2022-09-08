# Transform, Transition, Animations

#### References

https://learn.shayhowe.com/advanced-html-css/css-transforms/

https://learn.shayhowe.com/advanced-html-css/transitions-animations/

https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users/


### Transform

general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by 
the transform property.

The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and 
values.

Generally speaking, browser support for the transform property isn’t great, but it is getting better every day. For the best support vendor prefixes are 
encouraged, however you may need to download the nightly version of Chrome to see all of these transforms in action.

###### Transform Syntax

The actual syntax for the transform property is quite simple, including the transform property followed by the value. The value specifies the transform 
type followed by a specific amount inside parentheses.

```
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

Notice how the transform property includes multiple vendor prefixes to gain the best support across all browsers. 
The un-prefixed declaration comes last to overwrite the prefixed versions, should a browser fully support the transform property.

The vendor prefixes strongly encouraged for any code in a production environment. 
Over time we will be able to remove these prefixes, however keeping them in is the safest approach for the time being.

#### 2D Transforms

Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes.

###### 2D Rotate

The rotate value provides the ability to rotate an element from 0 to 360 degrees. 
Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. 
The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically. 
Later we will discuss how you can change this default point of rotation.

HTML
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

CSS
```
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

###### 2D Scale
Using the scale value within the transform property allows you to change the appeared size of an element. 
The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller.
While any value greater than or equal to 1.01 makes an element appear larger.

HTML
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

CSS
```
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```
It is possible to scale only the height or width of an element using the scaleX and scaleY values.
The scaleX value will scale the width of an element while the scaleY value will scale the height of an element.
To scale both the height and width of an element but at different sizes, the x and y axis values may be set simultaneously. 
To do so, use the scale transform declaring the x axis value first, followed by a comma, and then the y axis value.

HTML
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

CSS
```
.box-1 {
  transform: scaleX(.5);
}
.box-2 {
  transform: scaleY(1.15);
}
.box-3 {
  transform: scale(.5, 1.15);
}
```

###### 2D Translate

The translate value works a bit like that of relative positioning. 
Pushing and pulling an element in different directions without interrupting the normal flow of the document.
TranslateX value will change the position of an element on the horizontal axis 
TranslateY value will change the position of an element on the vertical axis.
To set both the x and y axis values at once, use the translate value and declare the x axis value first, followed by a comma, and then the y axis value.

HTML
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

###### 2D Skew

Skew, is used to distort elements on the horizontal axis, vertical axis, or both. 
The syntax is very similar to that of the scale and translate values. 
Using the skewX value distorts an element on the horizontal axis while the skewY value distorts an element on the vertical axis. 

To distort an element on both axes the skew value is used, declaring the x axis value first, followed by a comma, and then the y axis value.%p
The distance calculation of the skew value is measured in units of degrees. Length measurements, such as pixels or percentages, do not apply here.

HTML
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

CSS
```
.box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```

###### Combining Transforms

It is common for multiple transforms to be used at once, rotating and scaling the size of an element at the same time for example. 
In this event multiple transforms can be combined together. 
To combine transforms, list the transform values within the transform property one after the other without the use of commas.

HTML
```

```








