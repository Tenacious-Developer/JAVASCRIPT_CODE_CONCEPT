## Functions:
* A block of code that performs specific task
* DRY
* y = f(x)
```javascript
y = f(x) {
   // logic
}
```
### First Class Objects:
* Functions have properties & methods just like other objects so it is also called first class object.
* Functions are the callable object.

### Function declarations:
* Function Statements is also known as function declaration
```javascript
function add(x,y) {
	let res = x+y;
	return res;
}

let sum = add(3,4);
console.log(sum); // 7
```
* The return statement is the last line of any function, which returns a value to the calling function, and ends function execution.
* if you don't write return statement then it will return undefined.
```javascript
function add(x,y) {
	let res = x+y;
	console.log(res);
}

let sum = add(3,4);
console.log(sum); 

// 7
// undefined
```
* console.log() is a function which prints the value and by default return undefined if return is omited
* console is a object in which log is a function key

### Function Expression
```javascript
const add = function (x,y){
	return x+y; 
}
console.log(add(3,4)); // 7
```
### Anonymous Function
```javascript
(function () {
   //...
});
```
* A function without a name is Anonymous Function,& does not have their own identity
* it is used when the functions are used as values , it is not used as function statement
* in function expression, we use anonymous function as values assign to variables
### Arrow Functions:
``` javascript
const add = (x,y) => {
	return x+y;
}
console.log(add(3,4)); // 7
```
```javascript
const add = (x,y) => x+y;

console.log(add(3,4)); // 7
```
* DOM-level methods like setTimeout, setInterval, addEventListener are great applications of the Arrow functions.
* the arrow functions don't have their own this binding and are not suitable to be used for the call, apply and bind methods. They cannot be used as a constructor either.
### When are function expressions useful: 
* Function expressions are most useful when
* We want to pass a function as an argument to another function.
* We want to use our functions as values.
### Rest Parameter(...):
```javascript
function sum(x,y,...args) {
	console.log(x); // 3
	console.log(y); // 4
	console.log(args); // [ 5, 6, 7, 8, 9 ]
}
sum(3,4,5,6,7,8,9);
```
* rest parametre return the array of element
### Function returning function:
```javascript
function sum(x,y){
	let add = x+y;
	console.log(add);
	return function greet(a,b){
		return a-b;
	}
}
let res = sum(3,4)(4,3);
console.log(res);// 7,1
```
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
### Function can be passed in a Function as an argument
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
* All arguments in JavaScript functions are optional or loosely typed.
### First class Function:
* the ability of function to be used as values and can be passed these as an arguments to another function and can be returned from the function is this ability is known as first class function
* first class function is also known as first class citizen
### Pass-by-value or Pass-by-reference
* Primitive data types are the pass by value & non-primitive data types are the pass by reference.
* Primitive data types are compared by value
```javascript
var num1 = 60;
var num2 = 60;
console.log(num1 === num2); // true

var string1 = 'Vivek Kumar';
var string2 = 'vivek Kumar';
console.log(string1 === string2); // false
```
* Objects and arrays are not compared by value
```javascript
var obj1 = { 
  name : 'vivek',
  id : 101	
};
    
var obj2 = {    
  name : 'vivek',
  id : 101	
};
    
console.log(obj1 === obj2);  // false

var myArray1 = [1,2,3,4,5];
var myArray2 = [1,2,3,4,5];
console.log(myArray1 === myArray2);  // false
```
* primitive values are stored on the stack while non-primitive values are stored in a heap.
