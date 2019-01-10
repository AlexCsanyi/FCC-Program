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

```
