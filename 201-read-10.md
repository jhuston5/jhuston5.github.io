# Ch. 10, “Error Handling & Debugging

Learning to use the error messages is a crucial skill to tracking down bugs and problems. I am excited to get a better grasp on the console and common issues that we run into so I can write better code and stop some problems before they happen.

## Order of Execution

I have to bear in mind the way that the page interprets Javascript, as well as scope. Functions will not be read until they are called or invoked, and nested functions will run immediately within their parents.

### **Execution Context**

***Global Context***: code that is in the Javascript page, but not inside a function (Duckett Javascript 452)

***Function Context***: code that is contained and run within a function. Each function has individual context.

### **Variable Scope**

***Global Scope***: variables declared outside of functions can be used anywhere in the script.

***Function Level Scope***: variable declared within a function. The variable's scope is limited to being utilized within the function.

## The Stack

**Hoisting**: placing all variables, functions, and arguments at the top of the script. Hoisting is part of the ***preparation*** phase.

**Execution**: invoke functions and execute statements.

***Lexical Scope***
When a function is nested, I need to understood variables within that function. Each function gets its own execution context.

>"For each execution contextg the scope is the execution context's variables object plus the variables object for each parent execution context."

Error = exception

### Error Objects

Property | Description

- name: type of error
- message: description
- fileNumber: Name of the Javascript file
- lineNumber: Line number of error

Object | Description

1. *Error*: Generic error description
2. *SyntaxError*: Syntax has not been followed
3. *ReferenceError*: tried to reference a variable that has not been declared or within scope
4. *TypeError*: Unexpected Data Type
5. *RangeError*: Numbers not in acceptable range
6. *URIError*: encodeURI(), decodeURI() and other methods are used incorrectly. Not sure what this means!
7. *EvalError*: eval() function used incorrectly (Duckett Javascript 459)

### Breakpoints

Use your browsers debugger or console and can make the script stop at a particular line to see its value at that point in the scripts execution. (Duckett Javascript 476)

### Handling Exceptions

``` javascript
{
  try {
    // Try to execute the code
  } catch (exception) {
    // if there is an exception, run this code
  } finally {
    // This always gets executed
  }
}
```

(Duckett Javascript 480)
