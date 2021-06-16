# Read: Class 10 In memory storage

## [Understanding the JavaScript Call Stack](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/)

1. What is a ‘call’?

   - is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

1. How many ‘calls’ can happen at once?

   - only one function can happen.

1. What does LIFO mean?

   - it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

1. Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.
```
    function add(a, b) {
      return a + b;
    }

    function average(a, b) {
      return add(a, b) / 2;
    }

    let x = average(10, 20);
```
![call stack](https://www.javascripttutorial.net/wp-content/uploads/2019/12/JavaScript-Call-Stack.png)

1. What causes a Stack Overflow?
   - when there is a recursive function (a function that calls itself) without an exit point.

## [JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

1. What is a ‘refrence error’?
   - when you try to use a variable that is not yet declared

1. What is a ‘syntax error’?
   - when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

1. What is a ‘range error’?
   - Try to manipulate an object with some kind of length and give it an invalid length 

1. What is a ‘tyep error’?
   - when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

1. What is a breakpoint?
   - it a point to stop the code when the execution reaches it.

1. What does the word ‘debugger’ do in your code?
   - you can see the “history” before reaching that breakpoint.

## Things I want to know more about
