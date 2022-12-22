# Strings:
### create:
```javascript
let str ="srita";
console.log(str);

let str1 = 'sarita';
console.log(str1);

let str2 = `sarita`;
console.log(str2); 
```
* Strings in javascript can be created by calling the String() constructor
* String() constructor is called using the new keyword
```javascript
const name = new String("Vivek Kumar");
```
### Accessing characters:
* indexing
* function use charAt()
```javascript
let str ="srita";
console.log(str[0]); //s
console.log(str.charAt(0)); //s
```
### Function in string:
```javascript
str = str.toUpperCase(); 
console.log(str);    // SARITA
str = str.toLowerCase();
console.log(str);   // sarita
str = str.slice(1,3);
console.log(str);   // ar
```
### String length:
```javascript
let newName = "vivek";
console.log(newName.length);
//  last character of the string,use the length - 1 index
console.log(newName.length);
console.log(newName[newName.length - 1]);
console.log(newName[newName.length - 2]);
```
### Strings are immutable:
* cannot be modified once created
* create a new string from an existing string
```javascript
let str = 'Hi';

str = 'h' + str[1]; // replace the string

alert( str ); // hi
```
### Concatenating strings:
```javascript
let firstName = "vivek";
let lastName = "kumar";
let fullName = firstName + " " + lastName;
console.log(fullName);
```
``` javascript
let age = 22;
let firstName = "harshit"

//"my name is harshit and my age is 22 "
let aboutMe = "my name is " + firstName + " and my age is " + age; 
console.log(aboutMe);
let aboutMe = `my name is ${firstName} and my age is ${age}`
console.log(aboutMe);
```



### String Methods
* **charAt()**	Finds the character present at a particular index in the string.
* **concat()**	Concatenates the string arguments.
* **indexOf()**	returns the index of the first occurrence of the passed value.
* **lastIndexOf()**	returns the index of the last occurrence of the passed value.
* **toLowerCase()**	converts all the characters of the string into lowercase letters.
* **toUpperCase()**	converts all the characters of the string into uppercase letters.
* **split()**	divides the given string into an ordered list of substrings.
* **trim()**	removes additional spaces around the string.
* **toString()**	returns a string object as a string.
* **substring()**	extracts the characters between two indices of a string and returns a substring.
* **slice()**	extracts a section of a string and returns it as a new string, without modifying the original string.
