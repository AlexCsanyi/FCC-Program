# Multidimensional Arrays
Example
```javascript
var myFirstSubarray = [["this", "is"], ["super", "cool"]];
```
Print out all of the values -> loop inside a loop
```javascript
var myArr = [[1, 2], [3, 4]];
for (var i = 0; i < nestedArr.length; i++) {
  console.log(myArr[i]);
}

// this will log out:
// [1,2]
// [3,4]

// Once inside the outer array a loop inside the loop is needed to access the inner array
var myArr = [[1, 2], [3, 4]];
for (var i = 0; i < nestedArr.length; i++) {
  for (var j = 0; j < myArr[i].length; i++) {
    console.log(myArr[i][j]);
  }
}

// this will log out:
// 1
// 2
// 3
// 4
```
Practice exercises

```javascript
/* a function called printEvens that console.logs all of the even numbers */
var nestedArr = [[1, 2, 3], [4, 5, 6], [7, 8], [9, 10, 11, 12]];
function printEvens() {
  for (var i = 0; i < nestedArr.length; i++) {
    for (var j = 0; j < nestedArr[i].length; j++) {
      if (nestedArr[i][j] % 2 === 0) {
        console.log(nestedArr[i][j]);
      }
    }
  }
}

/* a function called sumTotal returns the sum of all numbers in the array */
var nestedArr = [[1, 2], [3, 4], [5, 6]];
var total = 0;
function sumTotal() {
  for (var i = 0; i < nestedArr.length; i++) {
    for (var j = 0; j < nestedArr[i].length; j++) {
      total += nestedArr[i][j];
    }
  }
  return total;
}

/* The function should check if name is an actual contact's firstName;
and the given property (prop) is a property of that contact.
If both are true, then return the "value" of that property.
If name does not correspond to any contacts then return "No such contact"
If prop does not correspond to any valid properties of a contact found to match name;
then return "No such property"
*/

//Setup
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["JavaScript", "Gaming", "Foxes"]
    }
];


function lookUpProfile(name, prop){
  for (var i = 0; i < contacts.length; i++) {
    if (contacts[i].firstName === name) {
      if (contacts[i].hasOwnProperty(prop)){
        return contacts[i][prop];
      }
      else {
        return "No such property"
      }
    }
  }
  return "No such contact"

}

// Change these values to test your function
lookUpProfile("Akira", "likes");
```
