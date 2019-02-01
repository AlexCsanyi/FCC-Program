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
