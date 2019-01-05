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
