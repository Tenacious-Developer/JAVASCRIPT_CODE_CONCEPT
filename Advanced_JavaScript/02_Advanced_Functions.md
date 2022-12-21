### Function Statement:
* Function Statements is also known as function declaration
``` javascript
a();  // a called
function a() {
	console.log("a called");
}
a();   // a called
``` 

### Function Expression
``` javascript
console.log(b); // undefined
b();            // error
var b = function () {         // function acts like a value
	console.log("b called");
}
b();            // b called
```

### Anonymous Function
``` javascript
(function () {
   //...
});
```
* A function without a name is Anonymous Function,& does not have their own identity
* it is used when the functions are used as values , it is not used as function statement
* in function expression, we use anonymous function as values assign to variables

### Named Function Expression
``` javascript
var b = function xyz() {  
	console.log("b called");  // b called
	console.log(xyz);         // Function:xyz
}
b();   //
xyz(); // we can not access xyz as global scope because it is created in local scope 
```

### Fnction returning function
```javascript
function myFunc(){
    function hello(){
        return "hello world"
    }
    return hello;
}

const ans = myFunc();
console.log(ans()); // hello world
```

### function can be passed in a function as an argument
``` javascript
var b = function (parm1) {
	console.log(parm1)
		
}
function xyz() {
	
}
b(xyz); // Function : xyz
```
* here in the above codde we pass function xyz as an argument in the function b 
``` javascript
var b = function (parm1) {
	return function () {
		
	}		
}

console.log(b()); // [Function (anonymous)]
```
### First class Function:
* the ability of function to be used as values and can be passed these as an arguments to another function and can be returned from the function is this ability is known as first class function
* first class function is also known as first class citizen

### Callback Function:
* callback function are very powerfull in javascript
* it can give access to the whole asynchronous world in a single synchronous thread language
* javascript is a synchronous single threaded language
* it can do only one thing at a time in specific order
``` javascript
setTimeout(function () {
	console.log("timer");
},5000);

function x(y) {
	console.log("x");
	y();
}

x(function y() {
	console.log("y")
});

// x
// y
// after 5 second
// timer
```

### IIFE - IMMEDIATELY INVOKED FUNCTION EXPRESSION:
* A JavaScript immediately invoked function expression is a function defined as an expression and executed immediately after creation. 
* When you define a function, the JavaScript engine adds the function to the global object. 
* if you declare a variable outside of a function using the var keyword, the JavaScript engine also adds the variable to the global object
* If you have many global variables and functions, the JavaScript engine will only release the memory allocated for them until the global object loses its scopes.
* One way to prevent the functions and variables from polluting the global object is to use immediately invoked function expressions.
``` javascript
(function(){
    //...
})();
```
* Can also be referred to as a Self-Executing Anonymous Function.
```javascript
(function() {
    var counter = 0;

    function add(a, b) {
        return a + b;
    }

    console.log(add(10,20)); // 30
}());
```
### Function pass-by-value or pass-by-reference
* In JavaScript, all function arguments are always passed by value. 
* Function arguments are local variables in JavaScript.

### High Order Function:
* Afunction which takes another function as an argument or return a function from it
```javascript
function x() {
    console.log("namaste")
}

function y(x) {
    x();
}
```
* map,filter & reduce are high order functionin js
* map,filter & reduce are used in array

