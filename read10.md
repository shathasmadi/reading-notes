# Read: 10 - JS Debugging
EXECUTION CONTEXT
+ GLOBAL CONTEXT:Code that is in the script, but not in a function. There is only one global context in any page.
+ FUNCTION CONTEXT:Code that is being run within a function.Each function has its own function context.
+ EVAL CONTEXT (NOT SHOWN):Text is executed like code in an internal function called eva l {) (which is not covered in this book).
VARIABLE SCOPE
+ VARIABLE SCOPE:If a variable is declared outside a function, it can be used anywhere because it has global scope.
+ FUNCTION-LEVEL SCOPE:When a variable is declared within a function, it can only be used within that function. This is because it has function-level scope.
The stack: javascript interpreter procced one line of code at a time,when statement need another data from a function it stacks or piles
+ Each time a script enters a new execution context, there are two phases of activity:
  1.PREPARE 2.EXECUTE
+ **hoisting**
  + Call functions before they have been declared
  + Assign a value to a va ria ble that has not yet been declared
+ The **preparation** phase is often described as taking all of the variables and functions and **hoisting** them to the top of the execution context.
+ Each **execution context** also creates its own variab1es object. This object contains details of all of the variables, functions, and parameters for that execution context.
+ If a JavaScript statement generates an error, then it throws an **exception**. At that point, the interpreter stops and looks for exception-handling code.
+ When an Er ror object is created, it will contain the following properties:
   + name : Type of execution
   + message :Description
   + fileNumber :Name of the JavaScript 
   + fillineNumber :Line number of error
 + There are seven types of built-in error objects in JavaScript.
    1.Error :Generic error - the other errors are all based upon this error
    2.Syntax Error :Syntax has not been followed
    3.ReferenceError:Tried to reference a variable that is not declared/within scope
    4.TypeError :An unexpected data type that cannot be coerced
    5. Range Error: Numbers not in acceptable range
    6.URI Error: encodeURI ().decodeURI(),and similar methods used incorrectly
    7.EvalError: eval () function used incorrectly
   
HOW TO DEAL WITH ERRORS
1: DEBUG THE SCRIPT TO FIX ERRORS
2: HANDLE ERRORS GRACEFULLY

# Resources:
JavaScript book, Ch. 10, “Error Handling & Debugging”
