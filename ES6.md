# ECMAScript 6 (ES6)

#### Standardized version of JavaScript with the goal of unifying the language's specifications and features.

One of the biggest problems with declaring variables with the var keyword is that:
you can overwrite variable declarations without an error.

```javascript
var camper = 'James';
var camper = 'David';
console.log(camper);
// logs 'David'
```

A new keyword called let was introduced in ES6

```javascript
let camper = 'James';
let camper = 'David'; // throws an error
```
So unlike var, when using let, a variable with the same name can only be declared once.

"var" vs "let"
```javascript
// var
var printNumTwo;
for (var i = 0; i < 3; i++) {
  if(i === 2){
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
// returns 3

// let
'use strict';
let printNumTwo;
for (let i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
// returns 2
console.log(i);
// returns "i is not defined"
```
"const" has all the awesome features that let has, with the added bonus that variables declared using const are read-only. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned.

ES6: Arrow Functions with Parameters

```javascript
const myConcat = function(arr1, arr2) {
  "use strict";
  return arr1.concat(arr2);
};

// the abov function using Arrow Functions
const myConcat = (arr1, arr2) => arr1.concat(arr2);

```
Higher order functions:

Traversy Media - Youtube Course:
```javascript
// predefined arrays
const companies = [
  {name: "Company One", category: "Finance", start: 1981, end: 2003},
  {name: "Company Two", category: "Retail", start: 1981, end: 2003},
  {name: "Company Three", category: "Auto", start: 1981, end: 2003},
  {name: "Company Four", category: "Retail", start: 1981, end: 2003},
  {name: "Company Five", category: "Technology", start: 1981, end: 2003},
  {name: "Company Six", category: "Finance", start: 1981, end: 2003},
  {name: "Company Seven", category: "Auto", start: 1981, end: 2003},
  {name: "Company Eight", category: "Technology", start: 1981, end: 2003},
  {name: "Company Nine", category: "Retail", start: 1981, end: 2003}
];

const ages = [53, 12, 28, 33, 11, 21, 46, 89, 99
```
