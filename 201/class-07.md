
# Object-Oriented Programming, HTML Tables


Reference Links:
https://github.com/codefellows/domain_modeling#domain-modeling
https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics

### Domain Modelling
Domain modeling is the process of creating a conceptual model in code for a specific problem.
A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain.
An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domian model can verify and validate the understanding of a specific problem among various stakeholders.
it defines a vocabulary that can be used within and between both technical and business teams.

Domain modeling is the process of creating a conceptual model for a specific problem. And a domain model that's articulated well can 
verify and validate your understanding of that problem.

##### Here's some tips to follow when building your own domain models.

When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
Model its attributes with a constructor function that defines and initializes properties.
Model its behaviors with small methods that focus on doing one job well.
Create instances using the new keyword followed by a call to a constructor function.
Store the newly created object in a variable so you can access its properties and methods from outside.
Use the this variable within methods so you can access the object's properties and methods from inside.


Explain why we need domain modeling?
To gain an understanding of functionality.

### HTML table basics

A table is a structured set of data made up of rows and columns (tabular data).
When implemented correctly, HTML tables are handled well by accessibility tools such as screen readers, so a successful HTML table should enhance 
the experience of sighted and visually impaired users alike.

##### When should you NOT use HTML tables?
HTML tables should be used for tabular data — this is what they are designed for. Unfortunately, a lot of people used to use HTML tables to 
lay out web pages, e.g. one row to contain the header, one row to contain the content columns, one row to contain the footer, etc.

Layout tables reduce accessibility for visually impaired users
Tables produce tag soup
Tables are not automatically responsive

The content of every table is enclosed by these two tags : <table></table>.
The smallest container inside a table is a table cell, which is created by a <td> element ('td' stands for 'table data').
To stop this row from growing and start placing subsequent cells on a second row, we need to use the <tr> element
```
 <table>
   <tr>
    <td>Hi, I'm your first cell.</td>
    <td>I'm your second cell.</td>
    <td>I'm your third cell.</td>
    <td>I'm your fourth cell.</td>
  </tr>
 </table>
```
Each row needs to be wrapped in an additional <tr> element, with each cell contained in a <td>

<th></th> are special cells that go at the start of a row or column and define the type of data that row or column contains.

Table headers and cells have the colspan and rowspan attributes, which allow us to span multiply columns or rows. 
For example, colspan="2" makes a cell span two columns.
  
#### Styling without <col>
  
HTML has a method of defining styling information for an entire column of data all in one place — the <col> and <colgroup> elements. These exist because it 
can be a bit annoying and inefficient having to specify styling on columns — you generally have to specify your styling information on every <td> or <th> 
in the column, or use a complex selector such as :nth-child


  











