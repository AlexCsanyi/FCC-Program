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
