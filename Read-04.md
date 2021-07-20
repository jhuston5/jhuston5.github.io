## Chapter 4: Ch.4 “Links” (pp.74-93)
* Links are created using the a tag. These need to have an href added to them to define what link is being used. 
> Use specificity when creating links!
> Links within the same website do not need the domain name in the link (80)

## Chapter 15: “Layout” (pp.358-404)
**Block level elements:** 
- h1
- p
- ul
- li

** Inline elements
- img
- b
- i


### Relative Positioning
Changes an element to be in a different position relative to its spot in normal flow, or position: static

### Absolute Positioning
Element is removed from normal flow. Other elements on the page act like it is not there (367). 

### Fixed Positioning
This one is like absolute but relative to the browser window.It's ideal for a heading that you might want to continue scrolling up or down with the rest of the content on the page.

* Z-Index
> This is like the bring to front and send to back features in Powerpoint (369)

### Float
Float is still confusing to me. I understand that it makes an element have that 'newspaper' styling, where the text would wrap around an image or quotation mark, but often when I use it I get unexpected styling results.

### CSS Styling
Skimmed the sections about liquid vs fixed layout, disadvantages and advantages of each. Obviously with different screen sized there are issues with the fixed layout if viewing on a mobile device or a large screen, while apparently a percentage based liquid layout can cause strange gaps and unintented consequences as it tries to adjust to the size of the screen. 

## Chapter 3 (first part): “Functions, Methods, and Objects” (pp.86-99 ONLY)
### Functions
- Conduct a specific task with the code
- Essentially isolating a task that might be used multiple times. Can store this function and run it often throughout a program.
- Asking a function to perform its task is known as **calling** the function.
- Functions often need information to perform its task. These pieces of information are called **parameters**.
- A function's name can also be known as an **identifier**.
- **Statements** are the code inside the curly braces {}
- You can call a function before it has been declared. This is a bit confusing to me, but for now I am just going to remember that somehow the interpreter knows that there is a function later on down the line. 
- The parameters required in a function are defined with the parentheses after the function name ie function completionPercentage(completed, attempted). Then completionPercentage(233, 297)
### Method
- Same as a function, just used within an object


### Object
- Create models of the world with data (86), made up of properties and methods
- Some built-in objects within JS

## Article: “6 Reasons for Pair Programming”
### Driver and Navigatores
Essentially it looks like we are using this technique to compartmentalize some of the tasks for writing code. 
The Driver writes code, runs the previews, etc.
The Navigator looks over code for bugs, does some thinking about what can be done using it (ie how a task can be translated to a function or loop). Can also look up things on Google or other reference sheets. 
> I see the Navigator as the person taking a 'tactical pause'. It's much easier to see the whole battle when you have a birds eye view rather than being stuck in the weeds of one small fight. 

1. In the long run, paired programming is more efficient as it results in less bugs and higher quality code production the first go-round.

2. From another practical standpoint it means less procrastination as well! You have an accountability partner right there!

3. Different people have different approaches to programming. Exposure to many different styles enables you to come up with creative solutions to problems.