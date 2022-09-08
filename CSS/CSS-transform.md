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











