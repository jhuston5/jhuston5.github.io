## Understanding The Problem Domain Is The Hardest Part Of Programming
TL;DR on this one seems to be that understanding a program from many different angles (business case, users, technical side) helps to write good code.

It is hard to write a solution to a problem when you are still trying to figure out the problem itself. If you don't you may not select the appropriate part of your programming language to solve it.

> "It is very difficult to solve a problem before you know the question.  It’s like buzzing in on Jeopardy before you hear the clue and shouting out random questions."


## Chapter 3: “Object Literals” (pp.100-105)
### OBJECTS
Variables become *properties* of an object.
Functions become *methods* of an object.

Arrays are stored using brackets [] while objects are stored using curly braces {}

Names of variables in an object are called keys. 

| Objects |  |
|------|------|
| Key | Value |
| var name | string |
| var rooms | number |
| var booked | number |
| var gym | Boolean |
| var roomTypes | array |
| checkAvailability() | function |

#### Literal Notation
Create a variable, followed by curly braces, and the properties made up of keys and values.

``` JavaScript
{
  var hotel = {
    name: 'Quay',
    rooms: 40,
    booked: 25,
    checkAvailability: function {
      return this.rooms - this.booked;
    }
  }
}
```

- Pretty important callout above - when using a method you can use the **this** keyword to refer to other properties in the object. 


#### Dot Notation
**Structure**
``` JavaScript
{
  var hotelName = hotel.name;
}
```
Use the object name, followed by a period, or member operator, then the name of the property or method you want to access. This is the most common way of accessing properties.

Less common is square bracket syntax. Duckett notes that this should be used when:
- The name of the property has a special character
- The name has a number (not encouraged)
- A variable is being used in place of the property name (103)


## Chapter 5: “Document Object Model” (pp.183-242)

### Document Object Model (DOM)

#### Making a Model of an HTML Page (184)

- Creates a model of the page in memory
- DOM tree determines how model will be structured
- Model is made of objects
- Each object represents a different part of the page (184)

#### Accessing and Changing the HTML Page (184)

- Determines how to update objects in the model
- DOM is an API? ie what allows programs to talk to each other (184)

DOM Tree 
Utilizes 4 types of nodes
1. Document Node
- represents the entire page
2. Element Node
- methods allow you element nodes 
3. Attribute Node
- List any attributes inside an opening tag of an HTML element
4. Text Node
- Always new branches of the DOM, no other branches can come from it (187)


#### Select elements
``` Javascript 
{
  getElementById()
  querySelector()
  getElementsByClassName()
  getElementsByTagName()
  querySelectorAll()
  parentNode
  previousSibling/nextSibling
  firstChild/lastChild
}
```

#### Use the elements
``` Javascript
{
  nodeValue
  innerHTML
  textContent
  createElement()
  createTextNode()
  appendChild()
  removeChild()
}
```

I have seen these elements before and used them in basic websites but I think I am finally understanding them in context. These are used to narrow in on specific elements of an HTML page for use. Most of this seems based on allowing the website to function as quickly as possible. 

We can loop through a node list using a for statement. 

> We can add or remove HTML content in two ways
- innerHTML, which is quicker but has some security risks
- DOM manipulation, safer but uses more code and is slower(219)