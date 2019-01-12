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
