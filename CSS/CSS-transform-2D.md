#CSS Transform

Reference Link
https://learn.shayhowe.com/advanced-html-css/css-transforms/

The transform property comes in two different settings, two-dimensional and three-dimensional. 
Each of these come with their own individual properties and values.

### 2D Transform values

transform: rotate(90deg);
transform: scale(1.5);
transform: translate(-50%, -50%)
transform: skew(5deg, 10deg);
transform-origin: 20px 30px;

###### Combining transform values:

transform: rotate(90deg) scale(1.5);

#### Examples

###### Rotate
css
```.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

###### Scale

css
```
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```
css
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

###### Translate

css
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

###### Skew

css
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

###### Combining Transform values

css
```
.box-1 {
  transform: rotate(25deg) scale(.75);
}
.box-2 {
  transform: skew(10deg, 20deg) translateX(20px);
}
```

###### Transform-Origin

css
```
.box-1 {
  transform: rotate(15deg);
  transform-origin: 0 0;
}
.box-2 {
  transform: scale(.5);
  transform-origin: 100% 100%;
}
.box-3 {
  transform: skewX(20deg);
  transform-origin: top left;
}
.box-4 {
  transform: scale(.75) translate(-10px, -10px);
  transform-origin: 20px 50px;
}
```

## The Details

#### Transform Syntax

The actual syntax for the transform property is quite simple, including the transform property followed by the value.
The value specifies the transform type followed by a specific amount inside parentheses.

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
Vendor prefixes are, however, strongly encouraged for any code in a production environment. 
Over time we will be able to remove these prefixes, however keeping them in is the safest approach for the time being.

Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes. 
Three-dimensional transforms work on both the x and y axes, as well as the z axis. 
These three-dimensional transforms help define not only the length and width of an element, but also the depth.

#### Transform Rotate

The rotate value provides the ability to rotate an element from 0 to 360 degrees. 
Using a positive value will rotate an element clockwise.
Using a negative value will rotate the element counterclockwise. 
The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically.

#### Transform Scale

The scale value within the transform property allows you to change the appeared size of an element. 
The default scale value is 1.
Any value between .99 and .01 makes an element appear smaller. 
while any value greater than or equal to 1.01 makes an element appear larger.

It is possible to scale only the height or width of an element using the scaleX and scaleY values. 
The scaleX value will scale the width of an element while.
The scaleY value will scale the height of an element. 
To scale both the height and width of an element but at different sizes, the x and y axis values may be set simultaneously. 
To do so, use the scale transform declaring the x axis value first, followed by a comma, and then the y axis value.

#### Translate

The translate value works a bit like that of relative positioning, 
pushing and pulling an element in different directions without interrupting
the normal flow of the document. 

Using the translateX value will change the position of an element on the horizontal axis.
Using the translateY value will change the position of an element on the vertical axis.

To set both the x and y axis values at once, use the translate value and declare the x axis
value first, followed by a comma, and then the y axis value.

The distance values used within the translate value may be any general length measurement. 
Most commonly pixels or percentages. 
Positive values will push an element down and to the right of its default position
Negative values will pull an element up and to the left of its default position.

#### Skew

Skew, is used to distort elements on the horizontal axis, vertical axis, or both. 
Using the skewX value distorts an element on the horizontal axis
Using the skewY value distorts an element on the vertical axis. 
To distort an element on both axes the skew value is used,
declaring the x axis value first, followed by a comma, and then the y axis value.

The distance calculation of the skew value is measured in units of degrees. 
Length measurements, such as pixels or percentages, do not apply here.







