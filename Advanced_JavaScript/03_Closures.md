### Closures:
* A function binds together with it's lexical enviroment
* function along with it's lexical scope forms a closures
```javascript
function x(){
    var b =7;
    function y(){
        console.log(b);
    }
    return y;
}
var z = x();
console.log(z);
z();
/*
ƒ y(){
        console.log(b);
    }


7
*/
```
```javascript
function x(){
    var b =7;
    return function y(){
        console.log(b);
    }
    y;
}
var z = x();
console.log(z);
z();
/*
ƒ y(){
        console.log(b);
    }


7
*/
```

```javascript
function z() {
    var b =900;
    function x() {
        var a =7;
        function y() {
            console.log(a,b); // 7, 900
        }
        y();
    }
    x();
}
z();

/*
closure (x)
a:7

closure (z)
b:900
*/

```
* it remember the reference of variable a & b
```javascript
function x() {
    var i =1;
    setTimeout(function (){
        console.log(i);
    },3000);
    console.log("vivek");
}
x();
/* output:
vivek
1
*/
```
* in the above code, there is call back function forms closure with reference of variable i
* when the timer has finished call back function executed & print the value of reference of i

```javascript
for(var i = 0; i < 5; i++) {
 setTimeout(function() {
  console.log(i);
 }, 1000);
}

```
* Here someone not familiar with Javascript will answer 0,1,2,3,4 where each number is printed at an interval of 1 sec. 
* But its correct answer would be 5,5,5,5,5 But why?
* because setTimeout function calls the function after 1 second, by the time 1 sec passes, the loop has completed its iteration and the value of i is 5
* As i is of var type, its value remains the same (var not blocking scoped). So when the callback function is called, i is 5 and hence we get 5,5,5,5,5 as output.
* to fix this
**Using IIFE AND CLOSURES**
```javascript
for(var i = 0; i < 5; i++) {
 (function(i) { 
   setTimeout(function() {
    console.log(i);
   }, 1000) 
  })(i);
}
```
* for each callback function (function inside the setTimeout) the value of i will not be the value of the iterator but the value of i in the outer function. Since this function is called for each value of i it will log all the value of i as desired.
* **Using let keyword**
```javascript
for(let i = 0; i < 5; i++) {
 setTimeout(function() {
  console.log(i);
 }, 1000);
}
```
* A very simple solution to this can be to use let instead of var in front of i. let creates a new lexical scope in each iteration which means that we will have a new i in each iteration
