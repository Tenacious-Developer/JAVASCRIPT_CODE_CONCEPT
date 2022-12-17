## What is Javascript:
* JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions.
* JavaScript is a prototype-based, multi-paradigm, single-threaded, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional            programming) styles.
* JavaScript is a single threaded synchronous language.
* one thing can be executed at a time in a specific order

## Features of JavaScript:
* cross platform
* Object oriented (prototype based)
* Scripting language (depends on the browser for the execution)
* Case sensitive
* JIT compiled (converts the JS code to byte code)
* Interpreted

## Javascript Engine:
* The Javascript engine is a special programme which can execute JS code not only in the browser but also on the server side and basically any machine which has this engine.
* This engine is also sometimes called as "Javascript virtual machine".
* Parsing is the process of analyzing the source code, checking it for errors, and breaking it up into parts.
* The parser produces a data structure called the Abstract Syntax Tree or AST
* AST is a tree graph of the source code that does not show every detail of the original syntax, but contains structural or content-related details
* interpreter converts the AST to byte code.
* JIT compiler tries to optimize this code as much as possible.
* Executed
### JIT Compiler:
* In modern engines, the interpreter starts reading the code line by line while the profiler watches for frequently used code and flags then passes is to the compiler to be optimized. In the end, the JavaScript engine takes the bytecode the interpreter outputs and mixes in the optimized code the compiler outputs and then gives that to the computer. This is called "Just in Time" or JIT Compiler.

### JavaScript run time enviroment: 
### Call Stack:
* The call stack keeps track of where we are in the code, so we can run the program in order.
* All the execution context is managed by the call stack
* Everything in js happens inside an execution context.
* Execution context is simply the environment within which your code is ran.
*  There are 2 types of execution context in JavaScript, global or function.
*  There are 2 stages as well to each context, the creation and executing phase. 
*  As the JavaScript engine starts to read your code, it creates something called the Global Execution Context.
*  1 stage is the memory creation phase,inside this variable & function in key-value pair exist,also called variable enviroment
*  2 stage is the execution pahse,also called  code component,thread of execution start from here,one line at a time
``` javascript
var n = 2;
function square(num) {
	var ans = num * num;
	return ans;
}
var square2 = square(n);
console.log(square2)     // 4
var square4 = square(4);
console.log(square4);    // 16
```
* how this js code work behind the scene
* first there is global execution context is created
* after the variable n, we come to variable square2 & square4 
* in these variable,there is a function invocation so, another new functional execution context is created for square2 & square4
* similarly in these execution context there is memory creation & execution phase
* all the EC is pushed into call stack one by one & after the operation,it will be deleted automatically one by one,after the whole code will be completed the GEC will be deleted, work as lifo
* in case of recursion function calling function again & again,stack over flow comes into picture.
### Memory Heap:
* The memory heap is a place to store and write information so that we can use our memory appropriately. It is a place to allocate, use, and remove memory as needed.
* JavaScript is a garbage collected language.
* If you allocate memory inside of a function, JavaScript will automatically remove it from the memory heap when the function is done being called. 
* JavaScript completes garbage collection with a mark and sweep method.
### Execution of code in run time enviroment:
* JavaScript is a single threaded synchronous language.
* one thing can be executed at a time in a specific order
* Each browser has its own version of JavaScript Runtime with a set of Web API's, methods that developers can access from the window object
* In a synchronous language, only one thing can be done at a time
* Imagine an alert on the page, blocking the user from accessing any part of the page until the OK button is clicked
* If everything in JavaScript that took a significant amount of time, blocked the browser, then we would have a pretty bad user experience
* This is where concurrency and the event loop come in.
* the event loop is constantly checking the call stack to see if it is empty so that it can add anything in the callback queue back into the call stack  
```javascript
console.log("1");
// goes on call stack and runs 1
setTimeout(() => {
  console.log("2"), 1000;
});
// gets sent to web api
// web api waits 1 sec, runs and sends to callback queue
// the javascript engine keeps going
console.log("3");
// goes on call stack and runs 3
// event loop keeps checking and see call stack is empty
// event loop sends calback queue into call stack
// 2 is now ran

// 1
// 3
// 2

// Example with 0 second timeout

console.log("1");
setTimeout(() => {
  console.log("2"), 0;
});
console.log("3");

// 1
// 3
// 2

// Still has the same output
```
* The job queue or microtask queue came about with promises in ES6
* With promises we needed another callback queue that would give higher priority to promise calls
* The JavaScript engine is going to check the job queue before the callback queue.
```javascript
// 1 Callback Queue ~ Task Queue
setTimeout(() => {
  console.log("1", "is the loneliest number");
}, 0);
setTimeout(() => {
  console.log("2", "can be as bad as one");
}, 10);

// 2 Job Queue ~ Microtask Queue
Promise.resolve("hi").then(data => console.log("2", data));

// 3
console.log("3", "is a crowd");

// 3 is a crowd
// 2 hi
// undefined Promise resolved
// 1 is the loneliest number
// 2 can be as bad as one
```
