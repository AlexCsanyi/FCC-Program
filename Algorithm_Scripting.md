### TASK 1:

Return an array consisting of the largest number from each provided sub-array.
```javascript
function largestOfFour(arr) {
  // You can do this!
  let maxArray = arr.map(function(item){
    return Math.max.apply(null, item);
  });
  return maxArray
}

console.log(largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]));
// returns [5, 27, 39, 1001]
```

### TASK 2:

Return the length of the longest word in the provided sentence. Your response should be a number.
```javascript
function findLongestWordLength(str) {  
  
  // split the string into an array of words
  let myArray = str.split(' ');
  
  // sort the new array by the length of its elements 
  myArray.sort(function(a,b){      
    return a.length - b.length;    
  });
  
  // get the last element in the array
  let lastElement = myArray[myArray.length - 1];  
 
  // return the length of the last element 
  return lastElement.length;
};
   
console.log(findLongestWordLength("The quick brown fox jumped over the lazy dog"));

// returns 6
```

### TASK 3:

Check if a string (first argument, str) ends with the given target string (second argument, target).

This can be solved with the .endsWith() method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.
```javascript
function confirmEnding(str, target) {
  
  // get the length of target and store it as a variable 
  let lengthOfTarget = target.length;
  
  /* using the substr method return the required segment of the string.
  Minus (-) ensures we start at the end of the string. 
  The segment will be as long as the length of the target.
  If the target variable is the same as the end of the string, return true, else return false */
  
  if(str.substr(-lengthOfTarget) === target){
    return true;
  } else {return false};
}

console.log(confirmEnding("Open sesame", "same"));
// returns true
```

### TASK 4:

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). 
Return the truncated string with a ... ending.

truncateString("Peter Piper picked a peck of pickled peppers", 11) should return "Peter Piper...".

```javascript
function truncateString(str, num) {
  
  // create a variable to store the new truncated string (strings are immutable)
  let shortStr = "";
  
  /* using substring as long as num is shorter than the length of the string we truncate and add "..."
     else we return the string */
     
  if(num < str.length){
    shortStr = str.substring(0,num) + "...";
    return shortStr;
  } else {
    return str;
  }
}

console.log(truncateString("A-tisket a-tasket A green and yellow basket", 45));
// returns A-tisket a-tasket A green and yellow basket

console.log(truncateString("Peter Piper picked a peck of pickled peppers", 11))
// returns Peter Piper...
```

### TASK 5:

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument). If no element passes the test, return undefined.

findElement([1, 3, 5, 8, 9, 10], function(num) { return num % 2 === 0; }) should return 8.

```javascript
// using filter() method
function findElement(arr, func) {
  
  // store elements that fulfill the function in an array 
  let myArr = arr.filter(func);
  
  // check if array is empty
  if(myArr.length == 0){
    return undefined; // if it is return undefined
  }else{
    return myArr[0]; // if it has at least 1 element return the first one
  } 
}

console.log(findElement([1, 3, 5, 9], function(num) { return num % 2 === 0; }));
// returns undefined
```

### TASK 6:

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.
For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".

```javascript
function titleCase(str) {

  // new variable where all characters are lower case
  let myStr = str.toLowerCase();
  
  // split the new str into an array of words
  let myArr = myStr.split(' ');
  
  /* using for loop iterate through all words and turn the first letter to uppercase
     using charAt() and toUpperCase() add the rest of the letter with slice()
     slice(): returns a copy of a portion of an array into a new array object
     push the new words into the newArr */
     
  let newArr = []
  for(let i = 0; i < myArr.length; i++){
    newArr.push(myArr[i].charAt(0).toUpperCase() + myArr[i].slice(1));
  }
  
  // return the new array and join the elements into 1 string using join()
  return newArr.join(' ')
}

console.log(titleCase("sHoRt AnD sToUt"));
// returns: Short And Stout
```

### TASK 7:
Remove all falsy values from an array.

Falsy values in JavaScript are false, null, 0, "", undefined, and NaN.
(converting each value to a Boolean.)

```javascript
function bouncer(arr) {
  /* using filter()
     we covert the elements of the array to boolean using !! operator
     if they are not false (!=) we store them in a new array */
  
  let trueOnly = arr.filter(val => !!val != false);
  
  // we return the new array
  return trueOnly;
}

console.log(bouncer([1, null, NaN, 2, undefined]));
// returns [1, 2]
```

### TASK 8:
Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

For example, getIndexToIns([1,2,3,4], 1.5) should return 1 because it is greater than 1 (index 0), but less than 2 (index 1).

```javascript
function getIndexToIns(arr, num) {
  // push item in the array at the end
  arr.push(num);
  
  // sort array from smallest to highest
  arr.sort((a,b) => a - b);
  
  // return the index of num
  let index = arr.indexOf(num);
  return index;
}

console.log(getIndexToIns([2, 5, 10], 15));
// reutrns 3 - the index of num

/* one line solution
return arr.concat(num).sort((a,b) => a-b).indexOf(num);
*/
```

### TASK 9:
Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array.

For example, ["hello", "Hello"], should return true because all of the letters in the second string are present in the first, ignoring case.

The arguments ["hello", "hey"] should return false because the string "hello" does not contain a "y".

Lastly, ["Alien", "line"], should return true because all of the letters in "line" are present in "Alien".

```javascript
function mutation(arr) {

  // first I split the first and second element into arrays of letters
  let newArr = arr[0].split('');
  let secondArr = arr[1].split('');
  
  // then I turn all elements into lowercase
  let arrOneLowercase = newArr.map(item => item.toLowerCase());
  let arrTwoLowercase = secondArr.map(item => item.toLowerCase());
  
  /* then I run a for loop to test if each element is included from the 2nd array in the first array
     I save the matching elements in matchArr */
  let matchArr = []
  for(let i = 0; i < arrTwoLowercase.length; i++){
    if(arrOneLowercase.includes(arrTwoLowercase[i])){
      matchArr.push(arrTwoLowercase[i]);
    }
  }
  
  // I test if the array is the same as the second array of letters
  if(arrTwoLowercase.length == matchArr.length){
    return true;
  } else { return false }
}

console.log(mutation(["zyxwvutsrqponmlkjihgfedcba", "qrstu"]));
// returns true
```
