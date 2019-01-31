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
