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

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

##
```

```

