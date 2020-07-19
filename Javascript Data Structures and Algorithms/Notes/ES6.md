# ES6
## Introduction to the ESCMAScript and ES6
* ECMAScript is a standardized version of JavaScript with the goal of unifying the language's 
specifications and features. 
* ECMAScript 5 (ES5) specification of the language, finalized in 2009. 
* All major browsers and JavaScript-runtimes follow this specification, the term ECMAScript is interchangeable with the term JavaScript.
* But JavaScript is an evolving programming language. As features are added and revisions are made, new versions of the language are released for use by developers.
* The most recent standardized version is called ECMAScript 6 (ES6), released in 2015. This new version of the language adds some powerful features that will be covered in this section of challenges, including:
    * Arrow functions
    * Classes
    * Modules
    * Promises
    * Generators
    * `let` and `const`
* Note: Not all browsers support ES6 features. If you use ES6 in your own projects, you may need to use a program (transpiler) to convert your ES6 code into ES5 until browsers support ES6.

## Differences Between the var and let Keywords
* `var` keyword is that you can overwrite variable declarations without an error
* In a small application, you might not run into this type of problem, but when your code becomes larger, you might accidentally overwrite a variable that you did not intend to overwrite. Because this behavior does not throw an error, searching and fixing bugs becomes more difficult.
* A new keyword called `let` was introduced in ES6 to solve this potential issue with the `var` keyword.
```
let camper = 'James';
let camper = 'David'; // throws an error
```
* Unlike `var`, when using `let`, a variable with the same name can only be declared once.
* The `"use strict"`, This enables Strict Mode, which catches common coding mistakes and "unsafe" actions.
```
"use strict";
x = 3.14; // throws an error because x is not declared
```

## Compare Scopes of the var and let Keywords
* When you declare a variable with the var keyword, it is declared globally, or locally if declared inside a function.
* The let keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.
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
* This behavior will cause problems if you were to create a function and store it for later use inside a for loop that uses the i variable. This is because the stored function will always refer to the value of the updated global i variable.
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
* As you can see, printNumTwo() prints 3 and not 2. This is because the value assigned to i was updated and the printNumTwo() returns the global i and not the value i had when the function was created in the for loop. The let keyword does not follow this behavior: 
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
* i is not defined because it was not declared in the global scope. It is only declared within the for loop statement. printNumTwo() returned the correct value because three different i variables with unique values (0, 1, and 2) were created by the let keyword within the loop statement.

## Declare a Read-Only Variable with the const Keyword
* The keyword let is not the only new way to declare variables. In ES6, you can also declare variables using the const keyword.

* const has all the awesome features that let has, with the added bonus that variables declared using const are read-only. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned.
```
"use strict";
const FAV_PET = "Cats";
FAV_PET = "Dogs"; // returns error
```
* A common practice when naming constants (or variabls with const) is to use all uppercase letters, with words separated by an underscore.
* Note: It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays).

## Mutate an Array Declared with const
* It is important to understand that objects (including arrays and functions) assigned to a variable using const are still mutable. Using the const declaration only prevents reassignment of the variable identifier.
```
"use strict";
const s = [5, 6, 7];
s = [1, 2, 3]; // throws error, trying to assign a const
s[2] = 45; // works just as it would with an array declared with var or let
console.log(s); // returns [5, 6, 45]
```
* As you can see, you can mutate the object [5, 6, 7] itself and the variable s will still point to the altered array [5, 6, 45]. Like all arrays, the array elements in s are mutable, but because const was used, you cannot use the variable identifier s to point to a different array using the assignment operator.

## Prevent Object Mutation
* const declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.
* Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error.
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

## Use Arrow Functions to Write Concise Anonymous Functions
* In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.
* To achieve this, we often use the following syntax:
```
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
```
* ES6 provides us with the syntactic sugar to not have to write anonymous functions this way. Instead, you can use arrow function syntax:
```
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```
* When there is no function body, and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:
```
const myFunc = () => "value";
```
* This code will still return value by default.

## Write Arrow Functions with Parameters
* Just like a regular function, you can pass arguments into an arrow function.
```
// doubles input value and returns it
const doubler = (item) => item * 2;
```
* If an arrow function has a single argument, the parentheses enclosing the argument may be omitted.
```
// the same function, without the argument parentheses
const doubler = item => item * 2;
```
* It is possible to pass more than one argument into an arrow function.
```
// multiplies the first input value by the second and returns it
const multiplier = (item, multi) => item * multi;
```

## Set Default Parameters for Your Functions
* In order to help us create more flexible functions, ES6 introduces default parameters for functions.
```
const greeting = (name = "Anonymous") => "Hello " + name;

console.log(greeting("John")); // Hello John
console.log(greeting()); // Hello Anonymous
```
* The default parameter kicks in when the argument is not specified (it is undefined). As you can see in the example above, the parameter name will receive its default value "Anonymous" when you do not provide a value for the parameter. You can add default values for as many parameters as you want.

## Use the Rest Parameter with Function Parameters
* In order to help us create more flexible functions, ES6 introduces the rest parameter for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.
```
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2)); // You have passed 3 arguments.
console.log(howMany("string", null, [1, 2, 3], { })); // You have passed 4 arguments.
```
* The rest parameter eliminates the need to check the args array and allows us to apply map(), filter() and reduce() on the parameters array.

## Use the Spread Operator to Evaluate Arrays In-Place
* ES6 introduces the spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.
* The ES5 code below uses apply() to compute the maximum value in an array:
```
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr); // returns 89
```
* We had to use Math.max.apply(null, arr) because Math.max(arr) returns NaN. Math.max() expects comma-separated arguments, but not an array. The spread operator makes this syntax much better to read and maintain.
```
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr); // returns 89
```
* `...arr` returns an unpacked array. In other words, it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal

## Use Destructuring Assignment to Extract Values from Objects
* Destructuring assignment is special syntax introduced in ES6, for neatly assigning values taken directly from an object.
```
const user = { name: 'John Doe', age: 34 };
const name = user.name; // name = 'John Doe'
const age = user.age; // age = 34
```
* Here's an equivalent assignment statement using the ES6 destructuring syntax:
```
const { name, age } = user;
// name = 'John Doe', age = 34
```
* Here, the name and age variables will be created and assigned the values of their respective values from the user object. You can see how much cleaner this is.
* You can extract as many or few values from the object as you want.

## Use Destructuring Assignment to Assign Variables from Objects
* Destructuring allows you to assign a new variable name when extracting values. You can do this by putting the new name after a colon when assigning the value.
```
const user = { name: 'John Doe', age: 34 };
Here's how you can give new variable names in the assignment:

const { name: userName, age: userAge } = user;
// userName = 'John Doe', userAge = 34
```
* You may read it as "get the value of user.name and assign it to a new variable named userName" and so on.

## Use Destructuring Assignment to Assign Variables from Nested Objects
* You can use the same principles from the previous two lessons to destructure values from nested objects.
```
const user = {
  johnDoe: { 
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};
```
* Here's how to extract the values of object properties and assign them to variables with the same name:
```
const { johnDoe: { age, email }} = user;
```
* And here's how you can assign an object properties' values to variables with different names:
```
const { johnDoe: { age: userAge, email: userEmail }} = user;
```

## Use Destructuring Assignment to Assign Variables from Arrays
* ES6 makes destructuring arrays as easy as destructuring objects.
* One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.
* Destructuring an array lets us do exactly that:
```
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b); // 1, 2
```
* The variable a is assigned the first value of the array, and b is assigned the second value of the array. We can also access the value at any index in an array with destructuring by using commas to reach the desired index:
```
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c); // 1, 2, 5
```

## Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements
* In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.
* The result is similar to Array.prototype.slice(), as shown below:
```
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]
```
* Variables a and b take the first and second values from the array. After that, because of the rest parameter's presence, arr gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest parameter to catch a subarray that leaves out the last element of the original array.

## Use Destructuring Assignment to Pass an Object as a Function's Parameters
* In some cases, you can destructure the object in a function argument itself.
* Consider the code below:
```
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;
  // do something with these variables
}
```
* This effectively destructures the object sent into the function. This can also be done in-place:
```
const profileUpdate = ({ name, age, nationality, location }) => {
  /* do something with these fields */
}
```
* This removes some extra lines and makes our code look neat. This has the added benefit of not having to manipulate an entire object in a function — only the fields that are needed are copied inside the function.

## Create Strings using Template Literals
* Template literals allow you to create multi-line strings and to use string interpolation features to create strings.

* Consider the code below:
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
* A lot of things happened there. Firstly, the example uses backticks (`), not quotes (' or "), to wrap the string. Secondly, notice that the string is multi-line, both in the code and the output. This saves inserting \n within strings. The ${variable} syntax used above is a placeholder. Basically, you won't have to use concatenation with the + operator anymore. To add variables to strings, you just drop the variable in a template string and wrap it with ${ and }. Similarly, you can include other expressions in your string literal, for example ${a + b}. This new way of creating strings gives you more flexibility to create robust strings.








## Use * to Import Everything from a File
* Suppose you have a file and you wish to import all of its contents into the current file. This can be done with the import * as syntax. Here's an example where the contents of a file named math_functions.js are imported into a file in the same directory:
```
import * as myMathModule from "./math_functions.js";
```
* The above import statement will create an object called myMathModule. This is just a variable name, you can name it anything. The object will contain all of the exports from math_functions.js in it, so you can access the functions like you would any other object property. Here's how you can use the add and subtract functions that were imported:
```
myMathModule.add(2,3);
myMathModule.subtract(5,3);
```

## Create an Export Fallback with export default
* There is another export syntax you need to know, known as export default. Usually you will use this syntax if only one value is being exported from a file. It is also used to create a fallback value for a file or module.

* Below are examples using export default:
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
* Since export default is used to declare a fallback value for a module or file, you can only have one value be a default export in each module or file. Additionally, you cannot use export default with var, let, or const

## Import a Default Export
* In the last challenge, you learned about export default and its uses. To import a default export, you need to use a different import syntax. In the following example, add is the default export of the math_functions.js file. Here is how to import it:
```
import add from "./math_functions.js";
```
* The syntax differs in one key place. The imported value, add, is not surrounded by curly braces ({}). add here is simply a variable name for whatever the default export of the math_functions.js file is. You can use any name here when importing a default.

## Create a JavaScript Promise
* A promise in JavaScript is exactly what it sounds like - you use it to make a promise to do something, usually asynchronously. When the task completes, you either fulfill your promise or fail to do so. Promise is a constructor function, so you need to use the new keyword to create one. It takes a function, as its argument, with two parameters - resolve and reject. These are methods used to determine the outcome of the promise. The syntax looks like this:
```
const myPromise = new Promise((resolve, reject) => {

});
```

## Complete a Promise with resolve and reject

## Handle a Fulfilled Promise with then
* Promises are most useful when you have a process that takes an unknown amount of time in your code (i.e. something asynchronous), often a server request. When you make a server request it takes some amount of time, and after it completes you usually want to do something with the response from the server. This can be achieved by using the then method. The then method is executed immediately after your promise is fulfilled with resolve. Here’s an example:
```
myPromise.then(result => {
  // do something with the result.
});
```
* result comes from the argument given to the resolve method.

## Handle a Rejected Promise with catch
* catch is the method used when your promise has been rejected. It is executed immediately after a promise's reject method is called. Here’s the syntax:
```
myPromise.catch(error => {
  // do something with the error.
});
```
* error is the argument passed in to the reject method.
* Note: the then and catch methods can be chained to the promise declaration if you choose.

# --- THE END ---


