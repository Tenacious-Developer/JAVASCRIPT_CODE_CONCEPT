## Conditional Flow:
### if...else...else if
```javascript
let weight = 70; // kg
let height = 1.72; // meter

// calculate the body mass index (BMI)
let bmi = weight / (height * height);

let weightStatus;

if (bmi < 18.5) {
  weightStatus = 'Underweight';
} else if (bmi >= 18.5 && bmi <= 24.9) {
  weightStatus = 'Healthy Weight';
} else if (bmi >= 25 && bmi <= 29.9) {
  weightStatus = 'Overweight';
} else {
  weightStatus = 'Obesity';
}

console.log(weightStatus);
```
### Switch Case
```javascript
function groceryPrice(exp){
 switch (exp) {
  case 'Cookies':
    console.log('Cookies cost 100 rupees');
    break;
  case 'Milk':
    console.log('Milk cost 60 rupees');
    break;
  case 'Fruits':
    console.log('Fruits cost 300 rupees');
    break;
  case 'Corn Flakes':
    console.log('Corn Flakes cost 150 rupees');
    break;
  default:
    console.log(exp + ' is not available right now');
  }
}


groceryPrice('Cookies');
//output: Cookies cost 100 rupees

groceryPrice('Fruits');
//output: Fruits cost 300 rupees

groceryPrice('Peanut');
//output: Peanut is not available right now

```
## Loops:
### while()
```javascript
var i = 1;
while (i <= 10) {
 console.log(i);
 i++;
}
```
### do...while()
```javascript
let i = 1;
do {
    console.log(i);
    i++;
} while(i <= 10);
```
### for()
```javascript
for (var i=1;i<=10;i++){
console.log(i)
}
```
### For...in
* used to iterate over those properties of objects that have been keyed
```javascript
const patient = {
    name: 'Isabel',
    height: 164, //in cm
    weight: 60,  //in kg
    disease: 'hypertension'
    
}
for ( let key in patient) {
    console.log(`${key} => ${patient[key]}`);
}
```
### For...of
* used to iterate over values
```javascript
const patients = ['Isabel', 'Marie', 'Skylar'];

for ( let the element of patients ) {

    // print
    console.log(element);
}
```
### For-await-of statement
* used to create loops that iterate over async and sync objects like arrays, map-sets, etc
* used only inside an async function
```javascript
for await (variable of iterable) { statement }
```
```javascript
async function main() {
    for await (const x of ['apple', 'mango']) {
        console.log(x);
    }
}
main();
```
