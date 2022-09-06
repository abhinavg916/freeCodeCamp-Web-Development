# JavaScript Data Structures and Algorithms Notes

## Contents

- Basic JavaScript
- ES6
- Regular Expressions
- Debugging
- Basic Data Structures
- Basic Algorithm Scripting
- Object Oriented Programming
- Functional Programming
- Intermediate Algorithm Scripting
- JavaScript Algorithms and Data Structures Project

### Projects

- [Project]()
- [Project]()
- [Project]()
- [Project]()
- [Project]()

### Certificate

![Certificate]()

---

## Basic JavaScript

### Declare JavaScript Variables

- JavaScript provides eight different data types which are undefined, null, boolean, string, symbol, bigint, number, and object

### Understanding Uninitialized Variables

- When JavaScript variables are declared, they have an initial value of undefined.
- If you do a mathematical operation on an undefined variable your result will be NaN which means "Not a Number"
- If you concatenate a string with an undefined variable, you will get a literal string of "undefined"

### Understanding Case Sensitivity in Variables

- Best Practice - The variable names in JavaScript in camelCase. In camelCase, multi-word variable names have the first word in lowercase and the first letter of each subsequent word is capitalized.

### Declare String Variables Passed

- String is a series of zero or more characters enclosed in single or double quotes

### Escaping Literal Quotes in Strings

- In JavaScript, you can escape a quote from considering it as an end of string quote by placing a backslash (`\`) in front of the quote
- Quoting Strings with Single Quotes - `conversation = 'Finn exclaims to Jake, "Algebraic!"';` => Acceptable
- However, this becomes a problem if you need to use the outermost quotes within it. Remember, a string has the same kind of quote at the beginning and end. But if you have that same quote somewhere in the middle, the string will stop early and throw an error

```
goodStr = 'Jake asks Finn, "Hey, let\'s go on an adventure?"';
badStr = 'Finn responds, "Let's go!"'; // Throws an error
```

### Escape Sequences in Strings

```
\'	single quote
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	word boundary
\f	form feed
```

### Concatenating Strings with the Plus Equals Operator

- Js supports the use of `+=` operator to concatenate a string onto the end of an existing string variable.

### Appending Variables to StringsPassed

- Append variables to a string using the plus equals `+=` operator

```
var anAdjective = "awesome!";
var ourStr = "freeCodeCamp is ";
ourStr += anAdjective;
// ourStr is now "freeCodeCamp is awesome!"
```

### Use of Bracket Notation to Find the Character in a String

```
var firstName = "Charles";
var firstLetter = firstName[0]; // firstLetter is "C
```

### Find the Length of a String

- The length of a String value by writing `.length` after the string variable or string literal

### Understand String Immutability

- In JavaScript, String values are immutable, which means that they cannot be altered once created
- The individual characters of a string literal cannot be changed
- The only way to change myStr would be to assign it with a new string

```
var myStr = "Bob";
myStr[0] = "J"; // Error
```

```
var myStr = "Bob";
myStr = "Job"; // Correct
```

### Store Multiple Values in one Variable using JavaScript Arrays

- It can contain multiple data type into one arraly like both a string and a number

```
var sandwich = ["peanut butter", "jelly", "bread", 100];
```

### Nest one Array within Another Array

- You can also nest arrays within other arrays, like below:

```
[["Bulls", 23], ["White Sox", 45]]
```

### Access Multi-Dimensional Arrays With Indexes

- One way to think of a multi-dimensional array, is as an array of arrays
- When you use brackets to access your array, the first set of brackets refers to the entries in the outer-most (the first level) array, and each additional pair of brackets refers to the next level of entries inside

```
var arr = [
  [1,2,3],
  [4,5,6],
  [7,8,9],
  [[10,11,12], 13, 14]
];
arr[3]; // equals [[10,11,12], 13, 14]
arr[3][0]; // equals [10,11,12]
arr[3][0][1]; // equals 11
```

- Note - There shouldn't be any spaces between the array name and the square brackets, like array [0][0] and even this array [0] [0] is not allowed. Although JavaScript is able to process this correctly, this may confuse other programmers reading your code

### Manipulate Arrays With push()

- An easy way to append data to the end of an array is via the push() function
- `.push()` takes one or more parameters and "pushes" them onto the end of the array

```
var arr1 = [1,2,3];
arr1.push(4);
// arr1 is now [1,2,3,4]

var arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
// arr2 now equals ["Stimpson", "J", "cat", ["happy", "joy"]]
```

### Manipulate Arrays With pop()

- `.pop()` is used to "pop" a value off of the end of an array. We can store this "popped off" value by assigning it to a variable. In other words, .pop() removes the last element from an array and returns that element
- Any type of entry can be "popped" off of an array - numbers, strings, even nested arrays

```
var threeArr = [1, 4, 6];
var oneDown = threeArr.pop();
console.log(oneDown); // Returns 6
console.log(threeArr); // Returns [1, 4]
```

### Manipulate Arrays With shift()

- pop() always removes the last element of an array. What if you want to remove the first?
- That's where `.shift()` comes in. It works just like .pop(), except it removes the first element instead of the last

```
var ourArray = ["Stimpson", "J", ["cat"]];
var removedFromOurArray = ourArray.shift();
// removedFromOurArray now equals "Stimpson" and ourArray now equals ["J", ["cat"]].
```

### Manipulate Arrays With unshift()

- Not only can you shift elements off of the beginning of an array, you can also unshift elements to the beginning of an array i.e. add elements in front of the array
- `.unshift()` works exactly like .push(), but instead of adding the element at the end of the array, unshift() adds the element at the beginning of the array

```
var ourArray = ["Stimpson", "J", "cat"];
ourArray.shift(); // ourArray now equals ["J", "cat"]
ourArray.unshift("Happy");
// ourArray now equals ["Happy", "J", "cat"]
Add ["Paul",35] to the beginning of the myArray variable using unshift().
```

### Write Reusable JavaScript with Functions

- In JavaScript, we can divide up our code into reusable parts called functions

```
function functionName() {
  console.log("Hello World");
}
```

- You can call or invoke this function by using its name followed by parentheses, like this: functionName(); Each time the function is called it will print out the message "Hello World" on the dev console. All of the code between the curly braces will be executed every time the function is called

### Passing Values to Functions with Arguments

- Parameters are variables that act as placeholders for the values that are to be input to a function when it is called
- When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or "passed") into a function when it is called are known as arguments

```
function testFun(param1, param2) {
  console.log(param1, param2);
}
```

- Then we can call testFun: testFun("Hello", "World"); We have passed two arguments, "Hello" and "World". Inside the function, param1 will equal "Hello" and param2 will equal "World". Note that you could call testFun again with different arguments and the parameters would take on the value of the new arguments.

### Global Scope and Functions

- In JavaScript, scope refers to the visibility of variables. Variables which are defined outside of a function block have Global scope. This means, they can be seen everywhere in your JavaScript code.
- Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var.

### Local Scope and Functions

- Variables which are declared within a function, as well as the function parameters have local scope. That means, they are only visible within that function.
- Here is a function myTest with a local variable called loc.

```
function myTest() {
  var loc = "foo";
  console.log(loc);
}
myTest(); // logs "foo"
console.log(loc); // loc is not defined
loc is not defined outside of the function.
```

- The editor has two console.logs to help you see what is happening. Check the console as you code to see how it changes. Declare a local variable myVar inside myLocalScope and run the tests.
- Note: The console will still have 'ReferenceError: myVar is not defined', but this will not cause the tests to fail.

### Global vs. Local Scope in Functions

- It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

```
var someVar = "Hat";
function myFun() {
  var someVar = "Head";
  return someVar;
}
```

- The function myFun will return "Head" because the local version of the variable is present.

### Understanding Undefined Value returned from a Function

- A function can include the return statement but it does not have to. In the case that the function doesn't have a return statement, when you call it, the function processes the inner code but the returned value is undefined.

```
var sum = 0;
function addSum(num) {
  sum = sum + num;
}
addSum(3); // sum will be modified but returned value is undefined
```

- addSum is a function without a return statement. The function will change the global sum variable but the returned value of the function is undefined.

### Stand in Line

- In Computer Science a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue.

```
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
  return arr.shift();
  // Only change code above this line
}

// Setup
var testArr = [1,2,3,4,5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

### Add === Operator

### Multiple Identical Options in Switch Statements

- If the break statement is omitted from a switch statement's case, the following case statement(s) are executed until a break is encountered. If you have multiple inputs with the same output, you can represent them in a switch statement like this:

```
switch(val) {
  case 1:
  case 2:
  case 3:
    result = "1, 2, or 3";
    break;
  case 4:
    result = "4 alone";
}
```

- Cases for 1, 2, and 3 will all produce the same result.

### Replacing If Else Chains with Switch

- Switch Cases comparision in JavaScript uses strictly `===` comparision operator
- If you have many options to choose from, a switch statement can be easier to write than many chained if/else if statements. The following:

```
if (val === 1) {
  answer = "a";
} else if (val === 2) {
  answer = "b";
} else {
  answer = "c";
}
can be replaced with:

switch(val) {
  case 1:
    answer = "a";
    break;
  case 2:
    answer = "b";
    break;
  default:
    answer = "c";
}
```

### Returning Boolean Values from Functions

- You may recall from Comparison with the Equality Operator that all comparison operators return a boolean true or false value.
- Sometimes people use an if/else statement to do a comparison, like this:

```
function isEqual(a,b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:

function isEqual(a,b) {
  return a === b;
}
```

### Build JavaScript ObjectsPassed

- You may have heard the term object before.
- Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.
- Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.
- Here's a sample cat object:

```
var cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```

### Accessing Object Properties with Dot Notation

- There are two ways to access the properties of an object: dot notation (.) and bracket notation ([]), similar to an array.
- Dot notation is what you use when you know the name of the property you're trying to access ahead of time.
- Here is a sample of using dot notation (.) to read an object's property:

```
var myObj = {
  prop1: "val1",
  prop2: "val2"
};
var prop1val = myObj.prop1; // val1
var prop2val = myObj.prop2; // val2
```

- The second way to access the properties of an object is bracket notation ([]). If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.
- However, you can still use bracket notation on object properties without spaces.
- Here is a sample of using bracket notation to read an object's property:

```
var myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock",
  "NoSpace": "USS Enterprise"
};
myObj["Space Name"]; // Kirk
myObj['More Space']; // Spock
myObj["NoSpace"];    // USS Enterprise
```

### Updating Object Properties

- After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.
- For example, let's look at ourDog:

```
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```

- Since he's a particularly happy dog, let's change his name to "Happy Camper". Here's how we update his object's name property: ourDog.name = "Happy Camper"; or ourDog["name"] = "Happy Camper"; Now when we evaluate ourDog.name, instead of getting "Camper", we'll get his new name, "Happy Camper".

### Add New Properties to a JavaScript Object

- You can add new properties to existing JavaScript objects the same way you would modify them.
- Here's how we would add a "bark" property to ourDog:

```
ourDog.bark = "bow-wow";

or

ourDog["bark"] = "bow-wow";
```

- Now when we evaluate ourDog.bark, we'll get his bark, "bow-wow".
- Example:

```
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```

### Delete Properties from a JavaScript Object

- We can also delete properties from objects like this: `delete ourDog.bark;`
- Example:

```
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};

delete ourDog.bark;
```

### Using Objects for Lookups Passed

- Objects can be thought of as a key/value storage, like a dictionary. If you have tabular data, you can use an object to "lookup" values rather than a switch statement or an if/else chain. This is most useful when you know that your input data is limited to a certain range.
- Here is an example of a simple reverse alphabet lookup:

```
var alpha = {
  1:"Z",
  2:"Y",
  3:"X",
  4:"W",
  ...
  24:"C",
  25:"B",
  26:"A"
};
alpha[2]; // "Y"
alpha[24]; // "C"

var value = 2;
alpha[value]; // "Y"
```

### Testing Objects for Properties

- Sometimes it is useful to check if the property of a given object exists or not. We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.
- Example

```
var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top");    // true
myObj.hasOwnProperty("middle"); // false
```

### Manipulating Complex Objects

- Sometimes you may want to store data in a flexible Data Structure. A JavaScript object is one way to handle flexible data. They allow for arbitrary combinations of strings, numbers, booleans, arrays, functions, and objects.
- Here's an example of a complex data structure:

```
var ourMusic = [
  {
    "artist": "Daft Punk",
    "title": "Homework",
    "release_year": 1997,
    "formats": [
      "CD",
      "Cassette",
      "LP"
    ],
    "gold": true
  }
];
```

- This is an array which contains one object inside. The object has various pieces of metadata about an album. It also has a nested "formats" array. If you want to add more album records, you can do this by adding records to the top level array. Objects hold data in a property, which has a key-value format. In the example above, "artist": "Daft Punk" is a property that has a key of "artist" and a value of "Daft Punk". JavaScript Object Notation or JSON is a related data interchange format used to store data.

```
{
  "artist": "Daft Punk",
  "title": "Homework",
  "release_year": 1997,
  "formats": [
    "CD",
    "Cassette",
    "LP"
  ],
  "gold": true
}
```

- Note - You will need to place a comma after every object in the array, unless it is the last object in the array.

### Accessing Nested Objects

- The sub-properties of objects can be accessed by chaining together the dot or bracket notation.
- Here is a nested object:

```
var ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": {
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};
ourStorage.cabinet["top drawer"].folder2;  // "secrets"
ourStorage.desk.drawer; // "stapler"
```

### Accessing Nested Arrays

- As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, Array bracket notation can be chained to access nested arrays.
- Here is an example of how to access a nested array:

```
var ourPets = [
  {
    animalType: "cat",
    names: [
      "Meowzer",
      "Fluffy",
      "Kit-Cat"
    ]
  },
  {
    animalType: "dog",
    names: [
      "Spot",
      "Bowser",
      "Frankie"
    ]
  }
];
ourPets[0].names[1]; // "Fluffy"
ourPets[1].names[0]; // "Spot"
```

### Record Collection

- You are given a JSON object representing a part of your musical album collection. Each album has several properties and a unique id number as its key. Not all albums have complete information.
- Write a function which takes an album's id (like 2548), a property prop (like "artist" or "tracks"), and a value (like "Addicted to Love") to modify the data in this collection.

```
// Setup
var collection = {
  2548: {
    album: "Slippery When Wet",
    artist: "Bon Jovi",
    tracks: [
      "Let It Rock",
      "You Give Love a Bad Name"
    ]
  },
  2468: {
    album: "1999",
    artist: "Prince",
    tracks: [
      "1999",
      "Little Red Corvette"
    ]
  },
  1245: {
    artist: "Robert Palmer",
    tracks: [ ]
  },
  5439: {
    album: "ABBA Gold"
  }
};

// Only change code below this line
function updateRecords(id, prop, value) {


  return collection;
}

updateRecords(5439, "artist", "ABBA");
```

### Iterate with JavaScript While Loops

- Add Elements to array

```
// Setup
var myArray = [];
var i = 5;
while( i >= 0){
  myArray.push(i);
  i--;
}

// Only change code below this line
```

### Nesting For Loops

- If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:

```
var arr = [
  [1,2], [3,4], [5,6]
];
for (var i=0; i < arr.length; i++) {
  for (var j=0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}
```

### Generate Random Fractions with JavaScript

- JavaScript has a Math.random() function that generates a random decimal number between 0 (inclusive) and not quite up to 1 (exclusive). Thus Math.random() can return a 0 but never quite return a 1

### Generate Random Whole Numbers within a Range

- To do this, we'll define a minimum number min and a maximum number max.
- Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing: `Math.floor(Math.random() * (max - min + 1)) + min`

### Use the parseInt Function

- The parseInt() function parses a string and returns an integer. Here's an example:

```
var a = parseInt("007");`// The above function converts the string "007" to an integer 7. If the first character in the string can't be converted into a number, then it returns NaN.
```

### Use the parseInt Function with a Radix

- The parseInt() function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.
- The function call looks like:

```
parseInt(string, radix);
```

- And here's an example:

```
var a = parseInt("11", 2);
```

- The radix variable says that "11" is in the binary system, or base 2. This example converts the string "11" to an integer 3.

### Use the Conditional (Ternary) Operator

- The conditional operator, also called the ternary operator, can be used as a one line if-else expression.
- The syntax is:

```
condition ? statement-if-true : statement-if-false;
```

### Use Multiple Conditional (Ternary) Operators

- The following function uses if, else if, and else statements to check multiple conditions:

```
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
```

- The above function can be re-written using multiple conditional operators:

```
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal"
    : (a > b) ? "a is greater"
    : "b is greater";
}
```

- It is considered best practice to format multiple conditional operators such that each condition is on a separate line, as shown above. Using multiple conditional operators without proper indentation may make your code hard to read. For example:

```
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
}
```

---

## ES6 Notes

### Introduction to the ESCMAScript and ES6

- ECMAScript is a standardized version of JavaScript with the goal of unifying the language's
  specifications and features.
- ECMAScript 5 (ES5) specification of the language, finalized in 2009.
- All major browsers and JavaScript-runtimes follow this specification, the term ECMAScript is interchangeable with the term JavaScript.
- But JavaScript is an evolving programming language. As features are added and revisions are made, new versions of the language are released for use by developers.
- The most recent standardized version is called ECMAScript 6 (ES6), released in 2015. This new version of the language adds some powerful features that will be covered in this section of challenges, including:
  - Arrow functions
  - Classes
  - Modules
  - Promises
  - Generators
  - `let` and `const`
- Note: Not all browsers support ES6 features. If you use ES6 in your own projects, you may need to use a program (transpiler) to convert your ES6 code into ES5 until browsers support ES6.

### Differences Between the var and let Keywords

- `var` keyword is that you can overwrite variable declarations without an error
- In a small application, you might not run into this type of problem, but when your code becomes larger, you might accidentally overwrite a variable that you did not intend to overwrite. Because this behavior does not throw an error, searching and fixing bugs becomes more difficult.
- A new keyword called `let` was introduced in ES6 to solve this potential issue with the `var` keyword.

```
let camper = 'James';
let camper = 'David'; // throws an error
```

- Unlike `var`, when using `let`, a variable with the same name can only be declared once.
- The `"use strict"`, This enables Strict Mode, which catches common coding mistakes and "unsafe" actions.

```
"use strict";
x = 3.14; // throws an error because x is not declared
```

### Compare Scopes of the var and let Keywords

- When you declare a variable with the var keyword, it is declared globally, or locally if declared inside a function.
- The let keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.

```
var numArray = [];
for (var i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);
// returns [0, 1, 2]
console.log(i);
// returns 3
```

- This behavior will cause problems if you were to create a function and store it for later use inside a for loop that uses the i variable. This is because the stored function will always refer to the value of the updated global i variable.

```
var printNumTwo;
for (var i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
// returns 3
```

- As you can see, printNumTwo() prints 3 and not 2. This is because the value assigned to i was updated and the printNumTwo() returns the global i and not the value i had when the function was created in the for loop. The let keyword does not follow this behavior:

```
'use strict';
let printNumTwo;
for (let i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
// returns 2
console.log(i);
// returns "i is not defined"
```

- i is not defined because it was not declared in the global scope. It is only declared within the for loop statement. printNumTwo() returned the correct value because three different i variables with unique values (0, 1, and 2) were created by the let keyword within the loop statement.

### Declare a Read-Only Variable with the const Keyword

- The keyword let is not the only new way to declare variables. In ES6, you can also declare variables using the const keyword.

- const has all the awesome features that let has, with the added bonus that variables declared using const are read-only. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned.

```
"use strict";
const FAV_PET = "Cats";
FAV_PET = "Dogs"; // returns error
```

- A common practice when naming constants (or variabls with const) is to use all uppercase letters, with words separated by an underscore.
- Note: It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays).

### Mutate an Array Declared with const

- It is important to understand that objects (including arrays and functions) assigned to a variable using const are still mutable. Using the const declaration only prevents reassignment of the variable identifier.

```
"use strict";
const s = [5, 6, 7];
s = [1, 2, 3]; // throws error, trying to assign a const
s[2] = 45; // works just as it would with an array declared with var or let
console.log(s); // returns [5, 6, 45]
```

- As you can see, you can mutate the object [5, 6, 7] itself and the variable s will still point to the altered array [5, 6, 45]. Like all arrays, the array elements in s are mutable, but because const was used, you cannot use the variable identifier s to point to a different array using the assignment operator.

### Prevent Object Mutation

- const declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.
- Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error.

```
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad"; // will be ignored. Mutation not allowed
obj.newProp = "Test"; // will be ignored. Mutation not allowed
console.log(obj);
// { name: "FreeCodeCamp", review:"Awesome"}
```

### Use Arrow Functions to Write Concise Anonymous Functions

- In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.
- To achieve this, we often use the following syntax:

```
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
```

- ES6 provides us with the syntactic sugar to not have to write anonymous functions this way. Instead, you can use arrow function syntax:

```
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```

- When there is no function body, and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:

```
const myFunc = () => "value";
```

- This code will still return value by default.

### Write Arrow Functions with Parameters

- Just like a regular function, you can pass arguments into an arrow function.

```
// doubles input value and returns it
const doubler = (item) => item * 2;
```

- If an arrow function has a single argument, the parentheses enclosing the argument may be omitted.

```
// the same function, without the argument parentheses
const doubler = item => item * 2;
```

- It is possible to pass more than one argument into an arrow function.

```
// multiplies the first input value by the second and returns it
const multiplier = (item, multi) => item * multi;
```

### Set Default Parameters for Your Functions

- In order to help us create more flexible functions, ES6 introduces default parameters for functions.

```
const greeting = (name = "Anonymous") => "Hello " + name;

console.log(greeting("John")); // Hello John
console.log(greeting()); // Hello Anonymous
```

- The default parameter kicks in when the argument is not specified (it is undefined). As you can see in the example above, the parameter name will receive its default value "Anonymous" when you do not provide a value for the parameter. You can add default values for as many parameters as you want.

### Use the Rest Parameter with Function Parameters

- In order to help us create more flexible functions, ES6 introduces the rest parameter for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

```
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2)); // You have passed 3 arguments.
console.log(howMany("string", null, [1, 2, 3], { })); // You have passed 4 arguments.
```

- The rest parameter eliminates the need to check the args array and allows us to apply map(), filter() and reduce() on the parameters array.

### Use the Spread Operator to Evaluate Arrays In-Place

- ES6 introduces the spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.
- The ES5 code below uses apply() to compute the maximum value in an array:

```
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr); // returns 89
```

- We had to use Math.max.apply(null, arr) because Math.max(arr) returns NaN. Math.max() expects comma-separated arguments, but not an array. The spread operator makes this syntax much better to read and maintain.

```
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr); // returns 89
```

- `...arr` returns an unpacked array. In other words, it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal

### Use Destructuring Assignment to Extract Values from Objects

- Destructuring assignment is special syntax introduced in ES6, for neatly assigning values taken directly from an object.

```
const user = { name: 'John Doe', age: 34 };
const name = user.name; // name = 'John Doe'
const age = user.age; // age = 34
```

- Here's an equivalent assignment statement using the ES6 destructuring syntax:

```
const { name, age } = user;
// name = 'John Doe', age = 34
```

- Here, the name and age variables will be created and assigned the values of their respective values from the user object. You can see how much cleaner this is.
- You can extract as many or few values from the object as you want.

### Use Destructuring Assignment to Assign Variables from Objects

- Destructuring allows you to assign a new variable name when extracting values. You can do this by putting the new name after a colon when assigning the value.

```
const user = { name: 'John Doe', age: 34 };
Here's how you can give new variable names in the assignment:

const { name: userName, age: userAge } = user;
// userName = 'John Doe', userAge = 34
```

- You may read it as "get the value of user.name and assign it to a new variable named userName" and so on.

### Use Destructuring Assignment to Assign Variables from Nested Objects

- You can use the same principles from the previous two lessons to destructure values from nested objects.

```
const user = {
  johnDoe: {
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};
```

- Here's how to extract the values of object properties and assign them to variables with the same name:

```
const { johnDoe: { age, email }} = user;
```

- And here's how you can assign an object properties' values to variables with different names:

```
const { johnDoe: { age: userAge, email: userEmail }} = user;
```

### Use Destructuring Assignment to Assign Variables from Arrays

- ES6 makes destructuring arrays as easy as destructuring objects.
- One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.
- Destructuring an array lets us do exactly that:

```
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b); // 1, 2
```

- The variable a is assigned the first value of the array, and b is assigned the second value of the array. We can also access the value at any index in an array with destructuring by using commas to reach the desired index:

```
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c); // 1, 2, 5
```

### Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements

- In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.
- The result is similar to Array.prototype.slice(), as shown below:

```
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]
```

- Variables a and b take the first and second values from the array. After that, because of the rest parameter's presence, arr gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest parameter to catch a subarray that leaves out the last element of the original array.

### Use Destructuring Assignment to Pass an Object as a Function's Parameters

- In some cases, you can destructure the object in a function argument itself.
- Consider the code below:

```
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;
  // do something with these variables
}
```

- This effectively destructures the object sent into the function. This can also be done in-place:

```
const profileUpdate = ({ name, age, nationality, location }) => {
  /* do something with these fields */
}
```

- This removes some extra lines and makes our code look neat. This has the added benefit of not having to manipulate an entire object in a function — only the fields that are needed are copied inside the function.

### Create Strings using Template Literals

- Template literals allow you to create multi-line strings and to use string interpolation features to create strings.

- Consider the code below:

```
const person = {
  name: "Zodiac Hasbro",
  age: 56
};

// Template literal with multi-line and string interpolation
const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`;

console.log(greeting); // prints
// Hello, my name is Zodiac Hasbro!
// I am 56 years old.
```

- A lot of things happened there. Firstly, the example uses backticks (`), not quotes (' or "), to wrap the string. Secondly, notice that the string is multi-line, both in the code and the output. This saves inserting \n within strings. The ${variable} syntax used above is a placeholder. Basically, you won't have to use concatenation with the + operator anymore. To add variables to strings, you just drop the variable in a template string and wrap it with ${ and }. Similarly, you can include other expressions in your string literal, for example \${a + b}. This new way of creating strings gives you more flexibility to create robust strings.

### Use \* to Import Everything from a File

- Suppose you have a file and you wish to import all of its contents into the current file. This can be done with the import \* as syntax. Here's an example where the contents of a file named math_functions.js are imported into a file in the same directory:

```
import * as myMathModule from "./math_functions.js";
```

- The above import statement will create an object called myMathModule. This is just a variable name, you can name it anything. The object will contain all of the exports from math_functions.js in it, so you can access the functions like you would any other object property. Here's how you can use the add and subtract functions that were imported:

```
myMathModule.add(2,3);
myMathModule.subtract(5,3);
```

### Create an Export Fallback with export default

- There is another export syntax you need to know, known as export default. Usually you will use this syntax if only one value is being exported from a file. It is also used to create a fallback value for a file or module.

- Below are examples using export default:

```
// named function
export default function add(x, y) {
  return x + y;
}

// anonymous function
export default function(x, y) {
  return x + y;
}
```

- Since export default is used to declare a fallback value for a module or file, you can only have one value be a default export in each module or file. Additionally, you cannot use export default with var, let, or const

### Import a Default Export

- In the last challenge, you learned about export default and its uses. To import a default export, you need to use a different import syntax. In the following example, add is the default export of the math_functions.js file. Here is how to import it:

```
import add from "./math_functions.js";
```

- The syntax differs in one key place. The imported value, add, is not surrounded by curly braces ({}). add here is simply a variable name for whatever the default export of the math_functions.js file is. You can use any name here when importing a default.

### Create a JavaScript Promise

- A promise in JavaScript is exactly what it sounds like - you use it to make a promise to do something, usually asynchronously. When the task completes, you either fulfill your promise or fail to do so. Promise is a constructor function, so you need to use the new keyword to create one. It takes a function, as its argument, with two parameters - resolve and reject. These are methods used to determine the outcome of the promise. The syntax looks like this:

```
const myPromise = new Promise((resolve, reject) => {

});
```

### Complete a Promise with resolve and reject

### Handle a Fulfilled Promise with then

- Promises are most useful when you have a process that takes an unknown amount of time in your code (i.e. something asynchronous), often a server request. When you make a server request it takes some amount of time, and after it completes you usually want to do something with the response from the server. This can be achieved by using the then method. The then method is executed immediately after your promise is fulfilled with resolve. Here’s an example:

```
myPromise.then(result => {
  // do something with the result.
});
```

- result comes from the argument given to the resolve method.

### Handle a Rejected Promise with catch

- catch is the method used when your promise has been rejected. It is executed immediately after a promise's reject method is called. Here’s the syntax:

```
myPromise.catch(error => {
  // do something with the error.
});
```

- error is the argument passed in to the reject method.
- Note: the then and catch methods can be chained to the promise declaration if you choose.
