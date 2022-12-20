## Operators
### Arithmatic Operator:
```
+ ---->	Addition
-	----> Subtraction
*	----> Multiplication
** --->	Exponentiation (ES2016)
/	----> Division
%	----> Modulus (Remainder)
++ --->	Increment
--	--> Decrement
```
### Assignment Operators:
```
=	-----> Assignment operator	
+= ----> Addition assignment	
-= ----> Subtraction Assignment	
*= ----> Multiplication Assignment	
/= ----> Division Assignment	
%= ----> Remainder Assignment	
**= ---> Exponentiation Assignment
```
### Comparison Operators:
```
==	-----> Equal to
!= ----> not equal
=== ----> equal value & type
!== ----> not equal valu not equal type
< ----> less than
> ----> greater than	
```
### Logical Operators:
```
&&	-----> Logical And
|| ----> Logical Or
! ------> logical not
```
### Bitwise Operators:
```
& -----> Bitwise AND
| -----> Bitwise OR
^ -----> Bitwise XOR
~ -----> Bitwise NOT
<< ----> Left shift
>> ----> Sign-propagating right shift
>>> ---> Zero-fill right shift
```
### String Operators:
```javascript
// concatenation operator
console.log('hello' + 'world'); // helloworld

let a = 'JavaScript';

a += ' tutorial';  // a = a + ' tutorial';
console.log(a); // JavaScript tutorial
```
### Ternary Operator
```javascript
let age = 18;
let message;

message = age >= 16 ? 'You can drive.' : 'You cannot drive.';

console.log(message); // You can drive
```
## Type Conversion:
* conversion of one data type to another data type
* Implicit type conversions - Automatic type conversion
* Explicit type conversions - Manual type conversion
* The different types of type conversion in JavaScript are :
  * String conversions
  * Numeric conversions
  * Boolean conversions
  * Symbol conversions

### String conversion:
* To explicitly convert a data type into a string, use String() function.
```javascript
// String Conversion Explicitly
String(23);   // '23'
String(true); // 'true'
String(32 - false);  // '32'
String(32 - true);   // '31'
```
* To implicitly convert a data type into a string, use of + binary operator when one operand is a string.
```javascript
// String Conversion Implicitly
"25" + 56; // '2556'
"25" + null; // '25null'
"Ale " + undefined; // 'Ale undefined'
"25" + false; // '25fasle'
```
### String comparison
* string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.
* strings are compared letter-by-letter.
``` javascript
alert( 'Z' > 'A' ); // true
alert( 'Glow' > 'Glee' ); // true
alert( 'Bee' > 'Be' ); // true
```

### Comparison of different types
* When comparing values of different types, JavaScript converts the values to numbers.
``` javascript
alert( '2' > 1 ); // true, string '2' becomes a number 2
alert( '01' == 1 ); // true, string '01' becomes a number 1
```

``` javascript
alert( true == 1 ); // true
alert( false == 0 ); // true
```

``` javascript
let a = 0;
alert( Boolean(a) ); // false

let b = "0";
alert( Boolean(b) ); // true
```
### Numeric Conversion:

```javascript
// Explicit conversion into number
Number(" 12 ");  // 12
Number("-12.34");  // -12.34
Number("\n");   // 0

//null and indefined into a number
Number(null);   // 0
Number(undefined);  // NaN

// Booleans into Number
Number(true); // 1
Number(false); // 0

// Difference between results of the same prompt..
prompt('what is you age?'); // '26'
Number(prompt('what is you age?')); // 26
```
```javascript
let age1 = "22";
age1 = +age1;
console.log(typeof(age1)); // number
```
* numeric conversions does not happen in == expression 
```javascript
null == null;   // true 
null == 0;   // false
// null cannot be converted into 0 with equality operator
null == undefined;  // true
```

*  prompt function always return a String, it automatically converts any input by the user into a string.
```javascript
const age = Number(prompt('Age'));
console.log(age); 
```
```javascript
console.log(parseInt(65.456));  // 65
```
* Evalutes data from left to right
```javascript
2 + 3 + '4' + 'number'
==> 5 + '4' + 'number'
==> '54' + 'number'
==> '54number'
```
### Boolean Conversion:
```javascript
Boolean('');   // false
Boolean(0);    // false     
Boolean(-0);   // false
Boolean(NaN);  // false
Boolean(null);  // false
Boolean(undefined);  // false
Boolean(false);   // false
```
