# FCC-Program
### My notes and code snippets during FCC's curriculum

Meaning of data in CS is anything that is meaningful to a computer. JS data types:
  * undefined
  * null
  * boolean
  * string
  * symbol
  * number
  * object

# Basic JS
the 2 expressions below are the same ("i" is a variable and is declared in the first line)
```javascript
var i;
i++;
i = i + 1;
```

remainder is calculated using "%"
What is remainder:
5 % 2 = 1 because
Math.floor(5 / 2) = 2 (Quotient)
2 * 2 = 4
5 - 4 = 1 (Remainder)

The below code calculates the remainder (2)
```javascript
var remainder = 11 % 3;
```
+= operator:
```javascript
var myVar = 1;
myVar += 5;
console.log(myVar); // Returns 6
```
```javascript
var myVar = 1;
myVar = myVar + 5;
console.log(myVar); // This returns 6 as well
```

Code | Output
------------ | -------------
\\' | Single Quote
\\" | Double Quote
\\\ | Backslash
\n	| newline
\r	| carriage return
\t	| tab
\b	| backspace
\f	| form feed

You can find the length of a String value by writing .length after the string variable or string literal.
```javascript
"Alan Peter".length; // 10
```

In order to get the last letter of a string, you can subtract one from the string's length.
For example, if ```var firstName = "Charles" ```, you can get the value of the last letter of the string by using ``` firstName[firstName.length - 1]. ```

Multi-Dimensional Arrays
```javascript
var arr = [
  [1,2,3],
  [4,5,6],
  [7,8,9],
  [[10,11,12], 13, 14]
];
arr[3]; // equals [[10,11,12], 13, 14]
arr[3][0]; // equals [10,11,12]
arr[3][0][1]; // equals 11
```
Manipulating arrays:
```javascript
var arr
arr.push() // addes item to the end of the array
arr.pop() // removes last item and stores it so it can be assigned to a variable
arr.shift() // removes first item
arr.unshift() // addes item to the first place in the array
```
