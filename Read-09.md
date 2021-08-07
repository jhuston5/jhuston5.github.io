# Forms and JS Events

## Chapter 7: “Forms” (p.144-175)

Forms are HTML elements that allow us to gather information from site users.

### Form Control

Many different options here, and I can sense I probably have a lot to learn about the best way to collect information in a way that is usable by backend languages.

- Adding Text

1. Text Input
2. Password Input
3. Text Area

- Making Choices

1. Radio Buttons
2. Checkboxes
3. Drop-down boxes

- Submiting Forms

1. Submit buttons
2. Image buttons

- Uploading Files

1. File Upload

> "You should never change the name of a form control in a page unless you know that the code on the server will understand this new value." (Duckett HTML 150)

## Form Methods

This one is pretty important for information flow - you can use either ***get*** or ***post*** to utilize information from forms. Get will be used when information can be kept localized, ie within the browser. Post will be used when you need to update a backend database or secure something important such as a password.

## Chapter 14: “Lists, Tables & Forms” (pp.330-357)

This sections is about using CSS to exercise greater control over specific elements of our lists, forms, etc. 

Unordered and ordered lists can both use several built in characters to change their style.

**Unordered** can utilize discs, circles, or squares.

**Ordered** can use decimals, lower and upper cased characters, and Roman numerals.

In addition, you can utilize images to create custom bullet points.

> "Forms are easier to use if the form controls are vertically aligned using CSS"
> "Forms benefit from styles that make them feel more interactive" (Duckett HTML 356)

## Chapter 6: “Events” (pp.243-292)

User Interaction > Event > Code > Response to User (Duckett JS 244)

When interaction with the webpage occurs, the DOM can be used to make updates. Does this mean we should hardcode HTML elements we know need to be on the page and use DOM manipulation for adding parts? Not sure exactly when to use each method.

### KEYWORDS

***fired*** or ***raised***

- terminology describing an event's occurence

***trigger***

- events cause a script to start running, called triggering a script

### Events

1. UI
2. Keyboard
3. Mouse
4. Focus
5. Form
6. Mutation

### Event Handling

- Select **element** node
- Choose which **event** will trigger a response
  - Known as ***binding***
- Choose what **code** you want to run

1. HTML Event Handlers
  Do not use, outdated
2. Traditional DOM Event Handlers
  Can only use one function per event, and can cause problems when combining multiple scripts (Duckett JS 250)
3. DOM Level 2 Event Listeners
  Best way to handle events

When passing the arguments to a function that is being called by an event handler or listener, create an **anonymous function** that wraps around a named function.

### Event Flow

- Event Bubbling: starts at the most specific node and flows outwards
- Event Capturing: starts at the least specific node and flows inwards

### Event Delegation

Utilize event listeners on parent elements vs child elements.

Improves browser performance and easier to implement new child elements.


### Focus and Blur

- Focus: fires an event for a specific DOM node when it gains focus
- Blur: fires an event for a specific DOM node when it loses focus

### Mouse Events

1. click
2. dblclick
3. mousedown
4. mouseup
5. mouseover
6. mouseout
7. mousemove

### Event Object

Tells you where a cursor was positioned when an event was triggered (Duckett JS 278)

### Keyboard events

1. input
2. keydown
3. keypress
4. keyup