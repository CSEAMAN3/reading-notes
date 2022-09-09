# Transform 3D

Reference Link:
https://learn.shayhowe.com/advanced-html-css/css-transforms/#two-dimensional-transforms


#### Transform Origin

The default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. 

To change this default origin position the transform-origin property may be used.


The transform-origin property can accept one or two values.

When only one value is specified, that value is used for both the horizontal and vertical axes. 

If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.


Individually the values are treated like that of a background image position, using either a length or keyword value. 

That said, 0 0 is the same value as top left, and 100% 100% is the same value as bottom right. 

More specific values can also be set, for example 20px 50px would set the origin to 20 pixels across and 50 pixels down the element.

###### Example

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

Notably, the transform-origin property does run into some issues when also using the translate transform value.

Since both of them are attempting to position the element, their values can collide. 

Use the two of these with caution, always checking to make sure the desired outcome is achieved.

#### Perspective

In order for three-dimensional transforms to work the elements need a perspective from which to transform. 

The perspective for each element can be thought of as a vanishing point, similar to that which can be seen in three-dimensional drawings.

The perspective of an element can be set in two different ways. 

One way includes using the perspective value within the transform property on individual elements

The other includes using the perspective property on the parent element residing over child elements being transformed.

Using the perspective value within the transform property works great for transforming one element from a single, unique perspective. 

When you want to transform a group of elements all with the same perspective, or vanishing point, apply the perspective property to their parent element.

###### Example

The example below shows a handful of elements all transformed using their individual perspectives with the perspective value.

```
.box {
  transform: perspective(200px) rotateX(45deg);
}
```

This next example shows a handful of elements, side by side, all transformed using the same perspective,

accomplished by using the perspective property on their direct parent element.

```
.group {
  perspective: 200px;
}
.box {
  transform: rotateX(45deg);
}
```

#### Perspective Depth Value

The perspective value can be set as none or a length measurement.

The none value turns off any perspective, while the length value will set the depth of the perspective. 

The higher the value, the further away the perspective appears, thus creating a fairly low intensity 

perspective and a small three-dimensional change. The lower the value the closer the perspective appears,

thus creating a high intensity perspective and a large three-dimensional change.

Imagine yourself standing 10 feet away from a 10 foot cube as compared to standing 1,000 feet away from the same cube. 

At 10 feet, your distance to the cube is the same as the dimensions of the cube, 

therefore the perspective shift is much greater than it will be at 1,000 feet, 

where the dimensions of the cube are only one one-hundredth of your distance to the cube.

The same thinking applies to perspective depth values.

###### Example

```
.box-1 {
  transform: perspective(100px) rotateX(45deg);
}
.box-2 {
  transform: perspective(1000px) rotateX(45deg);
}
```

#### Perspective origin

Like transform-origin you can also set a perspective-origin.

The same values used for the transform-origin property may also be used with the perspective-origin property. 

The difference between the two is where the origin of a transform determines the coordinates used to calculate

the change of a transform, while the origin of a perspective identifies the coordinates of the vanishing point of a transform.

```
.original {
  perspective: 200px;
}
.box {
  transform: rotateX(45deg);
}
.original-1 {
  perspective-origin: 0 0;
}
.original-2 {
  perspective-origin: 75% 75%;
}
.original-3 {
  perspective-origin: 20px 40px;
}
```

#### 3D Transform

Working with two-dimensional transforms we are able to alter elements on the horizontal and vertical axes.

Using three-dimensional transforms we can change elements on the z axis, giving us control of depth as well as length and width.

###### 3D Rotate

With three-dimensional transforms we can rotate an element around any axes. 

To do so, we use three new transform values, including rotateX, rotateY, and rotateZ.

rotateX value allows you to rotate an element around the x axis, as if it were being bent in half horizontally. 

rotateY value allows you to rotate an element around the y axis, as if it were being bent in half vertically.

rotateZ value allows an element to be rotated around the z axis.

Positive values will rotate the element around its dedicated axis clockwise.

Negative values will rotate the element counterclockwise.

```
.box-1 {
  transform: perspective(200px) rotateX(45deg);
}
.box-2 {
  transform: perspective(200px) rotateY(45deg);
}
.box-3 {
  transform: perspective(200px) rotateZ(45deg);
}
```

#### 3D scale

Using the scaleZ three-dimensional transform elements may be scaled on the z axis. 

This isn’t extremely exciting when no other three-dimensional transforms are in place, as there is nothing in particular to scale. 

In the demonstration below the elements are being scaled up and down on the z axis.

The rotateX value is added in order to see the behavior of the scaleZ value. 

When removing the rotateX in this case, the elements will appear to be unchanged.

```
.box-1 {
  transform: perspective(200px) scaleZ(1.75) rotateX(45deg);
}
.box-2 {
  transform: perspective(200px) scaleZ(.25) rotateX(45deg);
}
```

#### 3D Transform

Elements may also be translated on the z axis using the translateZ value. 

A negative value here will push an element further away on the z axis, resulting in a smaller element. 

Using a positive value will pull an element closer on the z axis, resulting in a larger element.

The transform is taking place on the z axis, not the x or y axes. 

```
.box-1 {
  transform: perspective(200px) translateZ(-50px);
}
.box-2 {
  transform: perspective(200px) translateZ(50px);
}
```

#### 3D Skew

Skew is the one two-dimensional transform that cannot be transformed on a three-dimensional scale. 

Elements may be skewed on the x and y axis, then transformed three-dimensionally as wished.

They cannot be skewed on the z axis.

#### Shorthand 3D Transforms

There are properties to write out shorthand three-dimensional transforms. 

These properties include rotate3d, scale3d, transition3d, and matrix3d. 

These properties require a bit more math and a strong understanding of the matrices behind each transform.
















