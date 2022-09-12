# CSS Layout

###### Reference links

https://web.dev/learn/css/flexbox/


### Flexbox

Flex box is a one dimensional layout mechanism for laying out groups of items.

It excels at taking a bunch of items which have different sizes, and returning the best layout for those items.

#### The main axis and the cross axis

The main axis is the one set by your flex-direction property. 

If that is row your main axis is along the row, if it is column your main axis is along the column.

#### The initial values mean that:

Items display as a row.

They do not wrap.

They do not grow to fill the container.

They line up at the start of the container.

#### Controlling the direction of items

Use flex-direction property to set the direction.

To change the direction, add the property and one of the four values:

row: the items lay out as a row.

row-reverse: the items lay out as a row from the end of the flex container.

column: the items lay out as a column.

column-reverse : the items lay out as a column from the end of the flex container.

#### Writing modes and direction

Flex items lay out as a row by default. 

A row runs in the direction that sentences flow in your writing mode and script direction.

If your css writing mode changes the so will your direction.

#### Wrapping flex items 

The flex-wrap property has a default value of nowrap.

This means if there is not enough space in the container the items will overflow.

Items will shrink to be as small as possible. 

To make the items wrap use flex-wrap: wrap;

This will mean items will display at max-content size wrapping if there is enough space.

#### The flex-flow shorthand

You can set the flex-direction and flex-wrap properties using the shorthand flex-flow.

```
.container {
  display: flex;
  flex-flow: column wrap;
}
```

#### Controlling space inside flex items

If our container has more space than is needed to display the items, the items line up at the start and do not grow to fill the space.

They stop growing at their max-content size. This is because the initial value of the flex- properties is:

flex-grow: 0: items do not grow.
flex-shrink: 1: items can shrink smaller than their flex-basis.
flex-basis: auto: items have a base size of auto.

This can be represented by a keyword value of flex: initial. 

The flex shorthand property, or the longhands of flex-grow, flex-shrink and flex-basis are applied to the children of the flex container.

To cause the items to grow, while allowing large items to have more space than small ones use flex:auto. 

You can try this using the demo above. This sets the properties to:

flex-grow: 1: items can grow larger than their flex-basis.
flex-shrink: 1: items can shrink smaller than their flex-basis.
flex-basis: auto: items have a base size of auto.

Using flex: auto will mean that items end up different sizes, as the space that is shared between the items is shared out after each item 
is laid out as max-content size. 

So a large item will gain more space. To force all of the items to be a consistent size and ignore the size of the content change 
flex:auto to flex: 1 in the demo.

This unpacks to:

flex-grow: 1: items can grow larger than their flex-basis.
flex-shrink: 1: items can shrink smaller than their flex-basis.
flex-basis: 0: items have a base size of 0.
Using flex: 1 says that all items have zero size, therefore all of the space in the flex container is available to be distributed. As all 
items have a flex-grow factor of 1 they all grow equally and the space is shared equally.

There is also a value of flex: none, which will give you inflexible flex items that do not grow or shrink. This might be useful if you are
purely using flexbox to access the alignment properties but don't want any flexible behavior.

#### Allowing items to grow at different rates

You don't have to give all items a flex-grow factor of 1. You could give your flex items different flex-grow factors. 

so if you had 3 items with the following: flex: 1; flex: 2; flex: 3; Then the items would be divided across 6 fractions.

The first item 1/6th the second 2/6th the third item 3/6th.

You can do the same thing from a flex-basis of auto, though you will need to specify the three values. 

The first value being flex-grow, the second flex-shrink, and the third flex-basis.

```
.item1 {
  flex: 1 1 auto;
}

.item2 {
  flex: 2 1 auto;
}
```

#### Reordering flex items

Items in your flex container can be reordered using the order property. 

This property allows the ordering of items in ordinal groups. 

Items are laid out in the direction dictated by flex-direction, lowest values first.

If more than one item has the same value it will be displayed with the other items with that value.

We use the syntax:

```
.container {
  display: flex;
  gap: 1rem;
}

.box:nth-child(2) {
  order: 2;
}

.box:nth-child(3) {
  order: 3;
}

select {
  min-width: 80px;
}
```

#### Flexbox alignment overview







###### Questions


1) Flexbox is designed for one-dimensional content. Explain what this means.

   Flex is one dimensional as it can control layout in a single direction either as a row or a column.


2) Explain the difference between the main axis and cross axis.

   The main axis is determined by the flex direction. 
   If your flex direction is set to row the main axis is set to the row. 
   If your flex direction is set to column the main axis is set to column.
   The main axis will also affect how other flex properties such as justify-content and align-items effect the flex items.
  
  
3) How can using certain properties of flexbox negatively impact accessibility?

   You need to be cautious when setting reverse-row and reverse-column. These will change the visual order only. 
   Therefore a screen reader will still follow the order as written in the HTML document.
   
   
1) What are some advantages of using flexbox over float?
  
  Flexbox is responsive and mobile friendly.
  
  Flex container’s margins do not collapse with the margins of its content.
  
  Positioning child elements becomes easier with flexbox.
  
  We can easily change the order of elements on our webpage without even making changes in HTML.

2) How does this topic connect with your long term goals?

  Undeestanding layout positioning and flex is extremely important for building websites and software development. It's   to essential for me to have an understanding of these concepts to be successful as a developer.
  
