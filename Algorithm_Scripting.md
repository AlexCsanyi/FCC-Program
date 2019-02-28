### TASK 1:

Return an array consisting of the largest number from each provided sub-array.
```javascript
function largestOfFour(arr) {
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

### TASK 10:
Write a function that splits an array (first argument) into groups the length of size (second argument) and returns them as a two-dimensional array.

chunkArrayInGroups([0, 1, 2, 3, 4, 5, 6], 3) should return [[0, 1, 2], [3, 4, 5], [6]].

```javascript
function chunkArrayInGroups(arr, size) {
  let chunks = []
  while (arr.length){
    chunks.push(arr.splice(0, size));
  }
  return chunks;
}
```

### TASK 11:
We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them.

The lowest number will not always come first.

```javascript
function sumAll(arr) {
  return arr.sort((a,b) => a - b).reduce((a,b) => (a + b) * (b - a + 1) / 2); 
};

console.log(sumAll([1, 4])); // returns 10
console.log(sumAll([10, 5])); // returns 45
``` 

### TASK 12:
Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

You can return the array with its elements in any order.

```javascript
function diffArray(arr1, arr2) {
  var newArr = arr1.concat(arr2);
  return newArr.filter(a => newArr.indexOf(a) === newArr.lastIndexOf(a));
}

console.log(diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5])); // returns 4
```

### TASK 13:
You will be provided with an initial array (the first argument in the destroyer function), followed by one or more arguments. Remove all elements from the initial array that are of the same value as these arguments.

Note
You have to use the arguments object.

```javascript
function destroyer(arr) {
  // declare new array of arguments from index 1
  let args = [...arguments].slice(1);
  
  // use ES6 filter method to find unique values only between the 2 arrays
  let newArr = arr.filter(a => args.indexOf(a) == -1); 
  return newArr;
}

console.log(destroyer([1, 2, 3, 1, 2, 3], 2, 3)); // returns 1,1
```

### TASK 14:
Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

Note
Preserve the case of the first character in the original word when you are replacing it. For example if you mean to replace the word "Book" with the word "dog", it should be replaced as "Dog"

```javascript
function myReplace(str, before, after) {
  let myRegex = new RegExp(before, "gi");

  var index = str.indexOf(before)
  if (str.charAt(index).toUpperCase() === str.charAt(index)) { 
    return str.replace(myRegex, after.charAt(0).toUpperCase() + after.slice(1)) } else {
      return str.replace(myRegex, after)
    }
}

console.log(myReplace("He is Sleeping on the couch", "Sleeping", "sitting"));
// returns He is Sitting on the couch
```

### TASK 15:
The DNA strand is missing the pairing element. Take each character, get its pair, and return the results as a 2d array.

Base pairs are a pair of AT and CG. Match the missing element to the provided character.

Return the provided character as the first element in each array.

For example, for the input GCG, return [["G", "C"], ["C","G"],["G", "C"]]

The character and its pair are paired up in an array, and all the arrays are grouped into one encapsulating array.

```javascript
function pairElement(str) {

  // using "split" to break down the str into an array of letters
  let splitStr = str.split('');
  
  // an empty array where the subarrays can be stored
  let arr = [];
  
  /* a for loop to iterate through each letter in splitStr 
  and declare an empty array; there will be multiple subarrays */
  for (let i = 0; i < str.length; i++) {
    let subArr = [];
  
  /* use a switch statement to avoid multiple if statements; 
  and match each letter with its DNA pair and push them into subarrays */
    switch (str[i]) {
      case 'G':
        subArr.push('G', 'C');
        break;
      case 'C':
        subArr.push('C', 'G');
        break;
      case 'A':
        subArr.push('A','T');
        break;
      case 'T':
        subArr.push('T', 'A');
        break;
    }
    
    // push the subarrays declared aobve into the parent array
    arr.push(subArr);
  }
  
  // finally return the parent array
  return arr;
}

console.log(pairElement("TTGAG")); 
```

### TASK 16:

```javascript
function fearNotLetter(str) {
  // created a new array of the alphabet
  let abc = "abcdefghijklmnopqrstuvwxyz".split('')
  
  // array of the str
  let splitStr = str.split('')
  
  // declaring the indexes of the first and last elemnts
  let index1 = abc.indexOf(splitStr[0]);
  let index2 = abc.indexOf(splitStr[splitStr.length - 1]);
  
  // declaring the temp array that is our desired array
  let tempArr = abc.slice(index1, index2+1) 

  // using filter - i find the difference between the 2 arrays and return it as string
  let newArr = tempArr.filter(i => splitStr.indexOf(i) < 0).toString();
  
  // if there is no difference return undefined
  if (newArr.length == 0) {
    return undefined
  } else {
    return newArr
  }
}

console.log(fearNotLetter("bcdf"));
```

### TASK 17: 
Write a function that takes two or more arrays and returns a new array of unique values in the order of the original provided arrays.

In other words, all values present from all arrays should be included in their original order, but with no duplicates in the final array.

The unique numbers should be sorted by their original order, but the final array should not be sorted in numerical order.

```javascript
function uniteUnique(...arr) {

let myArr = [].concat(...arr)
return [...new Set(myArr)]
}

console.log(uniteUnique([1, 3, 2], [1, [5]], [2, [4]]));
```

### TASK 18:
Given the array arr, iterate through and remove each element starting from the first element (the 0 index) until the function func returns true when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise, arr should be returned as an empty array.

```javascript
function dropElements(arr, func) {
 
  // filter the arr if the func is true
  let myArr = arr.filter(i => func(i) === true)

  // define the index as the first occurance where func is true in arr
  let index = arr.indexOf(myArr[0])


  // if the func is never true return myArr (empty)
  if (myArr.length == 0 || myArr == undefined) {
    return myArr
    
    // or return the arr from index
  } else {
    return arr.slice(index)
  }
}

console.log(dropElements([1, 2, 3, 4], function(n) {return n > 5;}));  // returns the empty myArr
```
