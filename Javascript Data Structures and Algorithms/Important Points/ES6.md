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
* 