
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

### let & const:
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

## Difference Between 'var' and 'let':
* The main difference between var and let is that the scope of the variable that is defined by let is limited to the block in which it is declared, whereas the variable declared using var has the global scope, i.e., can be used throughout the code.
* If we declare a variable using var outside of any block (i.e., in the global scope), then the variable gets added to the window object, whereas variables declared with let will never get added to it.
* We cannot declare the same variable multiple times if one of them is declared using let, whereas we can declare the same variable any number of times using var.
* Variable hoisting can be done using var, but hoisting cannot be done using let.
* Once a variable is declared or initialized, we can change its value anytime and anywhere within its scope. 
