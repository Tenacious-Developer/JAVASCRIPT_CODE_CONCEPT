# Arrays:
* Ordered collection of item
* Store multiple type of values
* index based
* reference type (i.e Object)
* the size of an array is dynamic and auto-growing
```javascript
let temp = [1,1.2,"vivek",null,undefined];
console.log(temp);// [1, 1.2, 'vivek', null, undefined]
```
### Creating an Arrays:
* two ways to create an array
#### Array constructor
```javascript
let arrayName = new Array(); // create an empty array
let arrayName = new Array(10); // create an array of size 10
let arrayName = new Array(1,2,3,"vivek",null); // create an array with values
```
#### Array literal notation
```javascript
let temp = [] // empty array // 
let temp = [1,1.2,"vivek",null,undefined]; // [1, 1.2, 'vivek', null, undefined]
```
### Accessing array elements:
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];

console.log(mountains[0]); // 'Everest'
console.log(mountains[1]); // 'Fuji'
console.log(mountains[2]); // 'Nanga Parbat'
```
* To change the value of an element
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains); // ['Everest', 'Fuji', 'Nanga Parbat']
mountains[1] = 'k2';
console.log(mountains); // ['Everest', 'k2', 'Nanga Parbat']
```
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
mountains[6] = "himalaya";
console.log(mountains); // ['Everest', 'k2', 'Nanga Parbat', undefined, undefined, undefined, 'himalaya']
console.log(mountains.length); // 7
console.log(mountains[2]); // Nanga Parbat
console.log(mountains[3]); // undefined
console.log(mountains[4]); // undefined
```
* now size becomes index + 1 i.e 7 & remaing index filled with undefined values
* access the element outside of it's range show error

### Functions
#### length
* to know the size or number of element in array
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
```
#### push() method
* add one or more element to the end of an array and return the new length of the array
```javascript
let userName = ["vivek", "Ajay"];
console.log(userName);  // ['vivek', 'Ajay']
console.log(userName.push("vijay")); // 3
console.log(userName); // ['vivek', 'Ajay', 'vijay']
```
#### pop() method
* used to remove the last element from the array & return that element
* decrese the length
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.pop()); // vijay
console.log(userName); // (2) ['vivek', 'Ajay']
```
#### shift() method
* used to remove the first element from the array & return that element
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.shift()); // vivek
console.log(userName); // (2) ['Ajay', 'vijay']
```
#### unshift() method
* add one element or more element to the begining of the array and return the new length
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.unshift("kumar")); // 4
console.log(userName); // (4) ['kumar', 'vivek', 'Ajay', 'vijay']
```
#### indexOf()
* used to return the first index at which the given element is found in the array
```javascript
let userName = ["vivek", "Ajay", "vijay", "Ajay"];
let id = userName.indexOf("Ajay");
console.log(id); // 1
```
#### Array.isArray()
*  To check if a value is an array
```javascript
let userName = ["vivek", "Ajay", "vijay", "Ajay"];
console.log(Array.isArray(userName)); // true
```

### clone & concatenate two arrays
```javascript
let array1 = ["item1", "item2"];
let array2 = array1; // both reference to same array
console.log("array1", array1); // array1 (2) ['item1', 'item2']
console.log("array2", array2); // array2 (2) ['item1', 'item2']
array1.push("item3");
console.log("after pushing element to array 1");
console.log("array1", array1); // array1 (3) ['item1', 'item2', 'item3']
console.log("array2", array2); // array2 (3) ['item1', 'item2', 'item3']
```
* cloning or copying one array into another array without reflecting the another array
* used slice method for cloning 
```javascript
let array1 = ["item1", "item2"];
let array2 = array1.slice(0);
array2.push("item3");
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3']
console.log(array1===array2); // false
```
* used slice method for cloning & adding extra element
```javascript
let array1 = ["item1", "item2"];
let array2 = array1.slice(0).concat(["item3", "item4"]);
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
```javascript
let array1 = ["item1", "item2"];
let array2 = [].concat(array1,["item3", "item4"]);
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
* new method for cloning is Spread operator
```javascript
let array1 = ["item1", "item2"];
let oneMoreArray = ["item3", "item4"];
let array2 = [...array1, ...oneMoreArray];
console.log(array1)  // (2) ['item1', 'item2']
console.log(oneMoreArray) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
### for loop in array:
```javascript
let fruits = ["apple", "mango", "grapes", "banana"];
let fruits2 = [];
for(let i=0; i < fruits.length; i++){
    fruits2.push(fruits[i].toUpperCase());
}

console.log(fruits2); // (4) ['APPLE', 'MANGO', 'GRAPES', 'BANANA']
```
* use const for creating array
* we are not changing the address of const variable here
```javascript
// heap memory ["apple", "mango"] 0x11

const fruits = ["apple", "mango"]; // 0x11
fruits.push("banana");
console.log(fruits); // (3) ['apple', 'mango', 'banana']
```
#### for of loop in array
```javascript
const fruits = ["apple", "mango", "grapes", "fruit4", "fruit5"];
const fruits2 = [];
for(let fruit of fruits){
    fruits2.push(fruit.toUpperCase());
}
console.log(fruits2); // (5) ['APPLE', 'MANGO', 'GRAPES', 'FRUIT4', 'FRUIT5']
```
#### for in loop in array
```javascript
const fruits = ["apple", "mango", "grapes", "fruit4", "fruit5"];
const fruits2 = [];

for(let index in fruits){
    fruits2.push(fruits[index].toUpperCase());
}
console.log(fruits2); // (5) ['APPLE', 'MANGO', 'GRAPES', 'FRUIT4', 'FRUIT5']
```
### Array destructuring
* for storing the different value of array in different variable
```javascript
const myArray = ["value1", "value2", "value3","value4"];
let myvar1 = myArray[0];
let myvar2 = myArray[1];
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
```
* using destructuring
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, myvar2] = myArray;
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
```
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, , myvar3] = myArray; // commas skip the value
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar3", myvar3); // value of myvar3 value3
```
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, myvar2, ...myNewArray] = myArray;
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
console.log(myNewArray);  // (2) ['value3', 'value4']
```
### passing array to function
```javascript
function findTarget(array, target){
    for(let i = 0; i<array.length; i++){
        if(array[i]===target){
            return i;
        }
    }
    return -1;
}
const myArray = [1,3,8,90]
const ans = findTarget(myArray, 8);
console.log(ans); // 2
```

### for-each
```javascript
const users = [
    {firstName: "harshit", age: 23},
    {firstName: "mohit", age: 21},
    {firstName: "nitish", age: 22},
    {firstName: "garima", age: 20},
]

users.forEach(function(user){
    console.log(user.firstName);
});
```
### Sort Method 
* this sort the array assuming string
* it compare the ASCII value of first letter or number
```javascript
const userNames = ['harshit', 'abcd', 'mohit', 'nitish', 'aabc', 'ABC', 'Harshit'];
userNames.sort();
console.log(userNames); // (7) ['ABC', 'Harshit', 'aabc', 'abcd', 'harshit', 'mohit', 'nitish']
```
* output is not as expected because of ascii comparison
```javascript
const numbers = [5,9,1200, 410, 3000];
numbers.sort();
console.log(numbers);

/*
[1200, 3000, 410, 5, 9]
ascii value of 1 in 1200 = 49[49,51,52,53,57]
ascii value of 3 in 3000 = 51
ascii value of 4 in 410 = 52
ascii value of 5        = 53
ascii value of 9        = 57
*/
```
* sollution of the above problem
```javascript
const numbers = [5,9,1200, 410, 3000];
numbers.sort((a,b)=>a-b); // for ascending a-b & descending b-a
console.log(numbers); //  [5, 9, 410, 1200, 3000]
```
### Find method
```javascript
const users = [
    {userId : 1, userName: "harshit"},
    {userId : 2, userName: "harsh"},
    {userId : 3, userName: "nitish"},
    {userId : 4, userName: "mohit"},
    {userId : 5, userName: "aaditya"},
];

const myUser = users.find((user)=>user.userId===3);
console.log(myUser); // {userId: 3, userName: 'nitish'}
```
### Every method
```javascript
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
]


const ans = userCart.every((cartItem)=>cartItem.price < 30000);
console.log(ans); // false
```
### Some method
* any one item exist true
```javascript
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
    {productId: 3, productName: "macbook", price: 25000},
]

const ans = userCart.some((cartItem)=>cartItem.price > 20000);
console.log(ans); // true
```
### fill method 
* value , start , end 
```javascript
const myArray = [1,2,3,4,5,6,7,8];
myArray.fill(0,2,5);
console.log(myArray); // [1, 2, 0, 0, 0, 6, 7, 8]
```
### splice method 
* start , delete , insert 
* delete
```javascript
const myArray = ['item1', 'item2', 'item3'];
const deletedItem = myArray.splice(1, 2);
console.log("delted item", deletedItem); // delted item (2) ['item2', 'item3']
```
* insert 
```javascript
const myArray = ['item1', 'item2', 'item3'];
myArray.splice(1, 0,'inserted item');
console.log(myArray); // ['item1', 'inserted item', 'item2', 'item3']
```
* insert and delete 
```javascript
const myArray = ['item1', 'item2', 'item3'];

const deletedItem = myArray.splice(1, 2, "inserted item1", "inserted item2")
console.log("delted item", deletedItem); // delted item (2) ['item2', 'item3']
console.log(myArray);  // (3) ['item1', 'inserted item1', 'inserted item2']
```
### Map:
* it is used to transform the array
* it returns a new array
```javascript
const arr = [1,2,3,4,5];

function binary(x) {
    return x.toString(2)
}

const output = arr.map(binary);

console.log(output); // (5) ['1', '10', '11', '100', '101']
```

```javascript
const arr = [1,2,3,4,5];


const output = arr.map(function binary(x) {
    return x.toString(2)
});

console.log(output); // (5) ['1', '10', '11', '100', '101']
```


```javascript
const arr = [1,2,3,4,5];


const output = arr.map((x) =>x.toString(2));

console.log(output); // (5) ['1', '10', '11', '100', '101']
```
### Filter 
```javascript
const arr = [1,2,3,4,5];


const output = arr.filter((x) => x >2);

console.log(output); // (3) [3, 4, 5]
```
### Reduce
* used at a place where you have to take all the element of the array & comeup with the single value out of them
* takes two argument
```javascript
const arr = [1,2,3,4,5];


const output = arr.reduce(function (acc,curr) {
    acc =acc + curr;
    return acc;
}, 0);

console.log(output); // 15
```
### chaining map filter
```javascript
const users = [
    {firstName : "vivek", LastName : "kumar", age : 25},
    {firstName : "gudiya", LastName : "kumari", age : 20},
    {firstName : "rachna", LastName : "kumari", age : 20},
    {firstName : "rashmka", LastName : "mandana", age : 29},
]

const output = users.filter((x) => x.age <25).map((x) => x.firstName);

console.log(output); // (2) ['gudiya', 'rachna']
```
