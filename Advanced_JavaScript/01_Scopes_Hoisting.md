## Hoisting:
* Hoisting is a phenomenona in javascript, by which we can access the variable & function even before we initialized it
``` javascript
getName();  // vivek kumar
console.log(x); // undefined

var x = 7;
function getName() {
	console.log("vivek kumar")
}
```
* so in the memory creation phase function getName() stores the whole function & var x stores the undefined.
* functions are fully hoisted
* var variable is hoisted & initliazed to undefined but let & const are hoisted but not initliazed to value
* arow function & function expression behaves just like variable so it stores undefined first
``` javascript
var x = 1;
a();  // 10
b();  // 100
console.log(x);  // 1

function a() {
	var x = 10;
	console.log(x); // find x in the local enviroment
}


function b() {
	var x = 100;
	console.log(x)
}
```
## window & this:
* window is a global object which is created along with global execution context
* when any js code is run a global object is created & a global execution context is created & a this keyword is created.
``` javascript
var a = 10;
function b() {
	var x = 10;
}

// window.a = 10
// this.a = 10
// a = 10 by default window.a

```

* whatever the variable & function you created in the global scope, are attached to window object(global object) & can be access through 
* window.var
* this.var
* var (by default window.var)

* var x is not in the global scope so, this.x is not defined.
## let & const:
* let & const declaration are hoisted
``` javascript
console.log(a) // reference error 
let a = 10;

console.log(b); // undefinedf
var b = 100;
```
``` javascript
let a = 10;
console.log(a); // 10

console.log(b); // undefinedf
var b = 100;
```
* global: b = undefined 
* script: a = undefined

* var b is attached to global level but a is attached in a  separate space(script)
* let & const are also get memory but they are stored in a different memory then global
* you can't access these let & const without initiliazation
* temporal dead zone is the time since when this let variable is hoisted and till it is initiliazed some value, the time between that is known as temporal dead zone
``` javascript
console.log(c);  // c = undefined

                  time between this is temporal dead zone
                  
let c = 30;      // c = 10
```
* whenever you try to access a variable in temporal dead zone,it gives you a refrence error
* var b = 100; this is global object so attached to window object 
* this.b = 100
* but let a = 100; this is not global so don't attached to window object
* this.a = undefined
* const is more strict then let 
* const is always initiliazed  with value, & can't be updated again
* but let can be updated without using let keyword
* let & const both are in scope level
* we can update let in same scope level. outside of the scope, it shows error

## Block scope & Shadowing:
``` javascript
{
	 this is block
}
```
* whatever all the variable & function can access inside the block, block scope called

``` javascript
{
  var a = 10;
  let b = 50;
  const c = 30;
}
```
*           Block --> b : undefined (hoisted in block)
*                     c : undefined (hoisted in block)

* Global --> a : undefined (hoisted in global)

* let & const can not access outside of the block

``` javascript
var a = 100;  // global
let b = 50;   // script
const c = 40; // script
{
	var a = 10; // global but updated 
	let b = 20; // block 
	const c = 30; // block
	console.log(a);  // 10
	console.log(b);  // 20
	console.log(c);  // 30
}
console.log(a);  // 10
console.log(b);  // 50
console.log(c);  // 40
```

``` javascript
let a = 20;
{
	var a = 20;
}
```
* we can not shadowing a let variable using var, we can shadowing only let inside block
``` javascript
let a = 20;
function x() {
	var a = 20;
}
```
* this can be done, because var is functionl block so it's boundry is function 
* but in the above case, it is on the block level scope, so can't shadowing  
``` javascript 
var a = 20;
{
	let a = 20;
}
```
* this is also true because var is in global scope.

* block scope follows lexical scope
``` javascript 
const a = 20;
{
	const b = 100;
	{
		const c = 200;
		console.log(a);
	}
}
```
## Difference Between 'var' and 'let':
* The main difference between var and let is that the scope of the variable that is defined by let is limited to the block in which it is declared, whereas the variable declared using var has the global scope, i.e., can be used throughout the code.
* If we declare a variable using var outside of any block (i.e., in the global scope), then the variable gets added to the window object, whereas variables declared with let will never get added to it.
* We cannot declare the same variable multiple times if one of them is declared using let, whereas we can declare the same variable any number of times using var.
* Variable hoisting can be done using var, but hoisting cannot be done using let.
* Once a variable is declared or initialized, we can change its value anytime and anywhere within its scope. 



