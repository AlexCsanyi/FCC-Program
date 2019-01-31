### TASK:

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
