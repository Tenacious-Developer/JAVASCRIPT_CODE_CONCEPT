# Conditional Flow:
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
# Loops:
### while():
```javascript
var i = 1;
while (i <= 10) {
 console.log(i);
 i++;
}
```
### do...while():
```javascript
let i = 1;
do {
    console.log(i);
    i++;
} while(i <= 10);
```
### for():
```javascript
for (var i=1;i<=10;i++){
console.log(i)
}
```
```javascript
for (var i=1;i<=10;i++){
console.log(i)
}
```
