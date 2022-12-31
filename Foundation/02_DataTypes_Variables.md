## Variables:
* JavaScript has three kinds of variable declarations.
* With the keyword var, can be used to declare both local and global variables, depending on the execution context.
* The var statement declares a function-scoped or globally-scoped variable
* var can be updated & re-declared.
* With the keyword const or let, can be used to declare a block-scope local variable.
* In var and let declarations, the initializer is optional. If a variable is declared without an initializer, it is assigned the value undefined.
* let can be updated but not re-declared.
* const declarations always need an initializer.
* const can not updated and can not re-declared
* loosely typed or a dynamically typed language

```javascript
var myNum; // declare
myNum = 7; // assign
console.log(myNum); // 7
myNum = 8; // update
console.log(myNum); // 8
```
```javascript
var myNum = 8;
var newNum = myNum; // copy in another variable
console.log(newNum);// 8

newNum = 9;
console.log(newNum); // 9
console.log(myNum); // 8
```
```javascript
let firstName = "vivek";
firstName = "kumar";
console.log(firstName);
```
```javascript
const pi  = 3.14; // cant update
pi =3.15; // error
```
## Data types
### 7 primitive datatypes
* primitive type that has only one value
* immutable
* atomic in nature (don't depend upon any other type)
* The variable assigned to a primitive type may be reassigned to a new value, but the original value can not be changed
* Primitives are passed by value
#### types
* null
* undefined
* boolean
* number
* string
* symbol 
* bigint 
### complex data type
* Objects are able to be mutated and their properties are passed by reference
* Booleans can be objects (if defined with the new keyword)
* Numbers can be objects (if defined with the new keyword)
* Strings can be objects (if defined with the new keyword)
* Dates are always objects
* Maths are always objects
* Regular expressions are always objects
* Arrays are always objects
* Functions are always objects
* Objects are always objects
### Number:
* The integers, float values (or decimals), and all the other numeric values are represented by the number datatype.
* The Javascript number type is a double-precision 64-bit binary format, i.e., it occupies 64 bits and ranges between a dynamic range (-2^53 - 1 to 2^53 - 1).
* The numbers that overflow this range are handled by BigInt datatype.
* Largest safe Integer: It represents the largest integer value that can be represented by javascript without any overflow.
	* Representation: Number.MAX_SAFE_INTEGER Value:  2^53 – 1. or 9007199254740991	
* Largest value: Represents the largest possible value that can be stored by javascript.
	* Representation: Number.MAX_VALUE Value: 1.7976931348623157e+308
* The largest safe integer refers to the largest value that can be represented while largest value refers to the largest value that can be stored.
* The JavaScript Number.MIN_SAFE_INTEGER constant represents the minimum safe integer in JavaScript.
	* Representation:Number.MIN_SAFE_INTEGER Value:  -(2^53 - 1) or -9007199254740991.
* Smallest value: It represents the smallest positive value in javascript.
	* Representation:Number.MIN_VALUE:5e-324
### Null
* there is an absence of value

### Undefined
* when a variable is declared but not initialized, it is assigned the value of undefined.
```javascript
let counter;
console.log(counter);        // undefined
console.log(typeof counter); // undefined
```
### NaN
* Not a Number
* special numeric value that indicates an invalid number
```javascript
console.log('a'/2); // NaN;
```
### Bigint
* The bigint type represents the whole numbers that are larger than 2^53 – 1. 
```javascript
let pageView = 9007199254740991n;
console.log(typeof(pageView)); // 'bigint'
```
### Boolean
```
function boolExample(flag){
    if(flag1){
        console.log('Hello world');
    }else{
        console.log('Hey there!');
    }    
}


bool x = true;
bool y = false;

boolExample(x);
//output: Hello world

boolExample(y);
//output: Hey there!
```
### The typeof operator
* The typeof operator returns the type of the argument.
* A call to typeof x returns a string with the type name:
```javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```
* The last three lines may need additional explanation:
* Math is a built-in object that provides mathematical operations
* The result of typeof null is "object". That’s an officially recognized error in typeof,null is not an object. It is a special value with a separate type of its own
* The result of typeof alert is "function", because alert is a function.

### Truthy and Falsy Values:
* The following values get converted to false in JavaScript:
* null 
* NaN 
* 0 (-0, +0)
* empty string ( "" or '' or `` )
* undefined.
