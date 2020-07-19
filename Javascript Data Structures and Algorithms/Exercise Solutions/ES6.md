# ES6
## Differences Between the var and let Keywords
```
let catName;
let quote;
function catTalk() {
  "use strict";
  catName = "Oliver";
  quote = catName + " says Meow!";
}
catTalk();
```

## Compare Scopes of the var and let Keywords
```
function checkScope() {
  'use strict';
  let i = 'function scope';
  if (true) {
    let i = 'block scope';
    console.log('Block scope i is: ', i);
  }
  console.log('Function scope i is: ', i);
  return i;
}
```

## Declare a Read-Only Variable with the const Keyword
```
function printManyTimes(str) {
  "use strict";
  // Only change code below this line
  const SENTENCE = str + " is cool!";
  for (let i = 0; i < str.length; i+=2) {
    console.log(SENTENCE);
  }
  // Only change code above this line
}
printManyTimes("freeCodeCamp");
```

## Mutate an Array Declared with const
```
const s = [5, 7, 2];
function editInPlace() {
  'use strict';
  // Only change code below this line
  s[0] = 2;
  s[1] = 5;
  s[2] = 7;
  // Only change code above this line
}
editInPlace();
```

## Prevent Object Mutation
```
function freezeObj() {
  'use strict';
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // Only change code below this line
  Object.freeze(MATH_CONSTANTS);
  // Only change code above this line
  try {
    MATH_CONSTANTS.PI = 99;
  } catch(ex) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```

## Use Arrow Functions to Write Concise Anonymous Functions
```
const magic = () => {
  return new Date();
};
```

## Write Arrow Functions with Parameters
```
const myConcat = (arr1, arr2) => arr1.concat(arr2);
console.log(myConcat([1, 2], [3, 4, 5]));
```

## Set Default Parameters for Your Functions
```
// Only change code below this line
const increment = (number = 1, value = 1) => number + value;
// Only change code above this line
```

## Use the Rest Parameter with Function Parameters
```
const sum = (...args) => {
  return args.reduce((a, b) => a + b, 0);
}
```

## Use the Spread Operator to Evaluate Arrays In-Place
```
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;
arr2 = [...arr1];  // Change this line
console.log(arr2);

```

## Use Destructuring Assignment to Extract Values from Objects 
```
const HIGH_TEMPERATURES = {
  yesterday: 75,
  today: 77,
  tomorrow: 80
};
// Only change code below this line
// const today = HIGH_TEMPERATURES.today;
// const tomorrow = HIGH_TEMPERATURES.tomorrow;
const { today, tomorrow } = HIGH_TEMPERATURES;
// Only change code above this line
```

## Use Destructuring Assignment to Assign Variables from Objects
```
const HIGH_TEMPERATURES = {
  yesterday: 75,
  today: 77,
  tomorrow: 80
};

// Only change code below this line
const { today: highToday, tomorrow: highTomorrow} = HIGH_TEMPERATURES;  
// Only change code above this line
```

## Use Destructuring Assignment to Assign Variables from Nested Objects
```
const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};

// Only change code below this line
const { today: { low: lowToday, high: highToday}} = LOCAL_FORECAST;

// Only change code above this line
```

## Use Destructuring Assignment to Assign Variables from Arrays
```
let a = 8, b = 6;
// Only change code below this line
[b, a] = [a, b];
```

## Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements
```
const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list) {
  "use strict";
  // Only change code below this line
  const [a,b, ...arr] = list;
  // Only change code above this line
  return arr;
}
const arr = removeFirstTwo(source);
```

## Use Destructuring Assignment to Pass an Object as a Function's Parameters
```
const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85
};

// Only change code below this line
const half = ( { max, min } ) => (max + min) / 2.0;
// Only change code above this line

```

## Create Strings using Template Literals
```
const result = {
  success: ["max-length", "no-amd", "prefer-arrow-functions"],
  failure: ["no-var", "var-on-top", "linebreak"],
  skipped: ["id-blacklist", "no-dup-keys"]
};
function makeList(arr) {
  "use strict";

  // Only change code below this line
  const resultDisplayArray = [];
  for (let i = 0; i < arr.length; i++) {
    resultDisplayArray.push(`<li class="text-warning">${arr[i]}</li>`);
  }
  // Only change code above this line

  return resultDisplayArray;
}

const resultDisplayArray = makeList(result.failure);
```

## Write Concise Object Literal Declarations Using Object Property Shorthand
```
const createPerson = (name, age, gender) => ({
 
  // Only change code below this line
  name, age, gender
  // Only change code above this line
});

```

## Write Concise Declarative Functions with ES6
```
// Only change code below this line
const bicycle = {
  gear: 2,
  setGear (newGear) { return this.gear = newGear; }
};
// Only change code above this line
bicycle.setGear(3);
console.log(bicycle.gear);
```

## Use class Syntax to Define a Constructor Function
```
// Only change code below this line
class Vegetable {
  constructor(name){
    this.name = name;
  }
}
// Only change code above this line

const carrot = new Vegetable('carrot');
console.log(carrot.name); // Should display 'carrot'
```

## Use getters and setters to Control Access to an Object
```
// Only change code below this line
class Thermostat {
  constructor(fahrenheit){
    this.fahrenheit = fahrenheit;
  }

  get temperature(){
     return (5 / 9) * (this.fahrenheit - 32);
  }

  set temperature(celsius){
    this.fahrenheit = (celsius * 9.0) / 5 + 32;
  }
}
// Only change code above this line

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```

## Create a Module Script
```
<html>
  <body>
    <!-- Only change code below this line -->
  <script type="module" src="index.js"></script>
    <!-- Only change code above this line -->
  </body>
</html>
```

## Use export to Share a Code Block 
```
const uppercaseString = (string) => {
  return string.toUpperCase();
}

const lowercaseString = (string) => {
  return string.toLowerCase()
}

export { uppercaseString, lowercaseString };
```

## Rseuse JavaScript Code Using import
```
import { uppercaseString, lowercaseString } from './string_functions.js';  
// Only change code above this line

uppercaseString("hello");
lowercaseString("WORLD!");
```

## Use * to Import Everything from a File
```
import * as stringFunctions from './string_functions.js';
// Only change code above this line

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

## Create an Export Fallback with export default
```
export default function(x, y) {
  return x - y;
}
```

## Import a Default Export
```
import subtract from './math_functions.js';  
// Only change code above this line

subtract(7,4);
```

## Create a JavaScript Promise
```
const makeServerRequest = new Promise((resolve, reject) => {

});
```

## Complete a Promise with resolve and reject
```
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer represents a response from a server
  let responseFromServer = true;
    
  if(responseFromServer){
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});
```

## Handle a Fulfilled Promise with then
```
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to true to represent a successful response from a server
  let responseFromServer = true;
    
  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});

makeServerRequest.then(result => {
  console.log(result);
});
```

## Handle a Rejected Promise with catch
```
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to false to represent an unsuccessful response from a server
  let responseFromServer = false;
    
  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});

makeServerRequest.then(result => {
  console.log(result);
});

makeServerRequest.catch(error =>{
  console.log(error);
});
```