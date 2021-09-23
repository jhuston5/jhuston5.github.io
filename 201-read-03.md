
# Chapter 3: “Lists” (pp.62-73)

## Ordered List
1. Use the <ol> tag to create the list
2. List is formatted with numbers
3. Use <li> tag to create individual list items

## Unordered List
- Use the <ul> tag to create an unordered list
- Formatted with bullet points instead of numbers
- Use <li> tag to create individual list items

## Nested List
* Create sub-lists inside an <li> element

# Chapter 13: “Boxes” (pp.300-329)
### Useful functions
'min-width'
'max-width'
> These help to ensure sizes don't get out of whack across different screen sizes. Should test on the browser before setting. (304)

## Pixels/ems/%
I had only used pixels in the past when using CSS, so ems and % were new. It seems to me that percentages and ems are useful when wanting to keep the relative size of an object consistent, while pixels can be used when wanting to be very precise.

### Centering a box
- ** Must set a width for the box, otherwise it will take up the whole page ** *315*
- Then can set a 'left-margin: auto' and 'right-margin: auto'



# Chapter 2: “Basic JavaScript Instructions” (pp.70-73)
## Arrays
' authors = ['Sanderson', 'Tolkien', 'Martin'];'
Arrays are extremely flexible, and can be updated with elements added and removed throughout your code. 

The index of the array is the order number of each item contained in it, starting at 0 and working up. 

Can use '.length' to determine the number of values in an array.


# Chapter 4: “Decisions and Loops” from switch statements on (pp.162-182)

## Switch Statement
I had previously been unfamiliar with a switch statement. 

Framework for switch:
case:
  break;
case:
  break;
default:

Uses an exact match on the case statements, and if none are matching it will run the default statement code. It will also stop the rest of the code from executing using the break statements, which can be faster than if statements. (164)

vs IF statement: this will check every statement even if a match has been found. 

### Weak Typing
> data type for a value can change (166)
### Type Coercion
> JS might attempt to use a string such as '1' to convert to the number 1. ie instead of returning NaN when compared to 0 it would now return true.

### Truthy Values
| Value | Description |
| ----- | ----------- |
| var ex = true | Boolean True |
| var ex = 1 | Non-zero numbers |
| var ex = 'apple' | strings with content |
| var ex = 20/5 | Number calculations |
| var ex = 'true' | True as a string is also true |
| var ex = '0' | 0 written as a string surprisingly is true |
| var ex = 'false' | False written as a string is true | 


### Falsy Values
| Value | Description |
| ----- | ----------- |
| var ex = false | Boolean false |
| var ex = 0 | zero |
| var ex = '' | empty string |
| var ex = 10/'amount' | NaN |
| var ex = | No variable assignment|


** Should almost always use strict equals === **


## LOOPS
Standard Structure
'for (var i = 0; i < 10; i++) {
  console.log(index[i]);
}'

** break**
Terminate the loop
** continue **
Stop, update, check, true = run again

Nesting for and while loops are tricky for me, so I will need to ensure I understand this.