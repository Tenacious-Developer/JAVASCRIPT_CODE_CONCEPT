## Operator:
* The == and === operators are used to check the equality of two operands.
* The != and !== operators are used to check the inequality of two operands.
* == and != are loose equality operators, i.e. they perform type conversion on the operands before comparing.
* === and !== are strict equality operator, i.e. they compare the operands without any type conversion, and return false (in case of === operator) even if the data types aren't same.

## Ternary Operator
```javascript
let age = 18;
let message;

message = age >= 16 ? 'You can drive.' : 'You cannot drive.';

console.log(message); // You can drive
```
