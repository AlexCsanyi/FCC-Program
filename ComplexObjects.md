https://stackoverflow.com/questions/11922383/access-process-nested-objects-arrays-or-json

```javascript
var instructorData = {
    name: "Elie",
    additionalData: {
        instructor: true,
        favoriteHobbies: ["Playing Cello", "Tennis", "Coding"],
        moreDetails: {
            favoriteBasketballTeam: "New York Knicks",
            numberOfSiblings: 3,
            isYoungest: true,
            hometown: {
                city: "West Orange",
                state: "NJ",
            },
            citiesLivedIn: ["Seattle", "Providence", "New York"]
        }
    }
};

instructorData.name; // "Elie"
instructorData.additionalData.instructor; // true
instructorData.additionalData.favoriteHobbies[2]; // "Coding"
instructorData.additionalData.moreDetails.favoriteBasketballTeam; // "New York Knicks"
instructorData.additionalData.moreDetails.hometown.state; // "NJ"
instructorData.additionalData.moreDetails.citiesLivedIn[1]; // "Providence"

```
When dynamically setting values in a nested object (when you don't know exactly what the name of the key is going to be), you have to use the bracket notation.

Function that adds a key to the nested object:

```javascript
var programmingLanguages = {
    java: {
        yearCreated: 1995,
        creator: "James Gosling"
    },
    javaScript: {
        yearCreated: 1995,
        creator: "Brendan Eich"
    }
}

function addProgrammingLanguage(nameOfLanguage, yearLanguageCreated, creatorOfLanguage) {
	 programmingLanguages[nameOfLanguage] = {
		 yearCreated: yearLanguageCreated,
       creator: creatorOfLanguage
	 }
}

addProgrammingLanguage("ruby", 1995, "Yukihiro Matsumoto");

```
When adding keys to an object, if you do NOT know exactly what the name of the key will be (meaning that the key will be dynamically created), you HAVE to use the bracket notation.

### Practice Exercises

* A function called displayCities that console.logs all the values in the citiesLivedIn array
* A function called displayHometownData that console.logs all the values inside of the hometown object
* A function called addDetail that accepts two parameters, a key and a value and adds the key and value to the moreDetails object and returns the moreDetails object
* A function called removeDetail that removes a key in the moreDetails object and returns the moreDetails object.

```javascript
var instructorData = {
    name: "Elie",
    additionalData: {
        instructor: true,
        favoriteHobbies: ["Playing Cello", "Tennis", "Coding"],
        moreDetails: {
            favoriteBasketballTeam: "New York Knicks",
            numberOfSiblings: 3,
            isYoungest: true,
            hometown: {
                city: "West Orange",
                state: "NJ",
            },
            citiesLivedIn: ["Seattle", "Providence", "New York"]
        }
    }
};

function displayCities() {
	var cityArray = instructorData.additionalData.moreDetails.citiesLivedIn;
	for (var i=0; i < cityArray.length; i++) {
		console.log(cityArray[i]);
	}
};

function displayHometownData() {
	var hometownObject = instructorData.additionalData.moreDetails.hometown;
	for (var key in hometownObject) {
		console.log(hometownObject[key]);
	}
};

function addDetail(addKey, addValue) {
	var detailsObject = instructorData.additionalData.moreDetails;
    detailsObject[key] = value;
    return detailsObject;
};

function removeDetail(key) {
  var detailsObject = instructorData.additionalData.moreDetails;
  var valueToBeRemoved = detailsObject[key];
  delete detailsObject[key];
  return detailsObject;
};

```

### More Exercises 
https://www.rithmschool.com/courses/intermediate-javascript/javascript-nested-data-structures-objects-exercises

```javascript
var nestedData = {
  innerData: {
    order: ["first", "second", "third"],
    snacks: ["chips", "fruit", "crackers"],
    numberData: {
        primeNumbers: [2,3,5,7,11],
        fibonnaci: [1,1,2,3,5,8,13]
    },
    addSnack: function(snack){
        this.snacks.push(snack);
        return this;
    }
  }
}

/* Using a for loop, console.log all of the numbers in the primeNumbers array. */
function displayPrimeNumbers() {
  var primeNumbersArray = nestedData.innerData.numberData.primeNumbers;
  for (var i=0; i < primeNumbersArray.length; i++) {
    console.log(primeNumbersArray[i]);
  }
};

/* Using a for loop, console.log all of the even Fibonnaci numbers. */
function displayFibonnaci() {
  var fibonnaciArray = nestedData.innerData.numberData.fibonnaci;
  for (var i=0; i < fibonnaciArray.length; i++) {
    if(fibonnaciArray[i] % 2 === 0) {
      console.log(fibonnaciArray[i])
    }
  }
};

/* Console.log the value "second" inside the order array. */
function printSecond() {
  var valueSecond = nestedData.innerData.order[1];
  console.log(valueSecond);
}
/* OR 
console.log(nestedData.innerData.order[1]);
*/

/* Invoke the addSnack function and add the snack "chocolate" */
function newSnack(value) {
  nestedData.innerData.snacks.push(value);
  return nestedData.innerData.snacks;
}
/* OR
nestedData.innerData.addSnack("Chocolate")
*/
```

```javascript
var nestedObject = {
  speakers: [{name:"Elie"},{name:"Tim"},{name:"Matt"}],
  data: {
    continents: {
      europe: {
        countries: {
          switzerland: {
            capital: "Bern",
            population: 8000000
          }
        }
      }
    },
    languages: {
      spanish: {
          hello: "Hola"
      },
      french: {
          hello: "Bonjour"
      }
    }
  }
}

/* Write a function addSpeaker to add a speaker to the array of speakers. The speaker you add must be an object with a key of name and a value of whatever you'd like. */
nestedObject.speakers.push({name: "Alex"})
console.log(nestedObject.speakers)

```
