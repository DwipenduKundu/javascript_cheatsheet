# JavaScript Concepts Technical Paper 


## 1. Different Datatypes in JavaScript
- **Primitive**: `Number`, `String`, `Boolean`, `Undefined`, `Null`, `Symbol`, `BigInt`
- **Non-Primitive**: `Object`, `Array`, `Function`, `Date`, etc.


## 2. let, var, const
- `var`: Function-scoped, hoisted, can be redeclared.
- `let`: Block-scoped, not hoisted the same way, cannot be redeclared in same scope.
- `const`: Block-scoped, must be initialized during declaration, immutable binding.


## 3. Why We Must Not Use var
- Allows redeclaration.
- Function-scoped causes unexpected behavior.
- Hoisting may lead to `undefined` issues.
- Confusing in block-scoped logic like loops or conditions.


## 4. Why Using Global Variables is Bad
- Increases risk of naming conflicts.
- Makes debugging harder.
- Pollutes the global namespace.
- Difficult to trace the source of bugs.


## 5. Truthy and Falsy Values
**Falsy** values:
- `false`, `0`, `""`, `null`, `undefined`, `NaN`

Everything else is **truthy**.


## 6. Function Hoisting
- Printing a variable before declaring that variable
- Function declarations are hoisted entirely.
- Function expressions (especially with `const` or `let`) are not hoisted.

```js
greet();

function greet() {
  console.log("Hello!");
}
```


## 7. What Happens When a Function Does Not Have a Return Statement
- Returns `undefined` by default.


## 8. Different Ways of Declaring a Function
- Function Declaration
  ```js
  function functionName(parameter1, parameter2, ...) {
  // Code
  return value;
  }
  ```
- Function Expression 
  ```js
  const x = function (a, b) {return a * b};
  ```
  
- Arrow Function (=>)
  ```js
  const multiplyArrow = (a, b) => {
  return a * b;
  };
  ```
- Anonymous Function
  ```js
  let myFunction = function(parameters) {
  // Function body
  };
  ```


## 9. Pass by Reference and Pass by Value
- **Primitive values**: Passed by value.
- **Objects/arrays/functions**: Passed by reference.


## 10. Different Types of For Loops
- `for` loop (traditional numeric loop)
- `for..in` (iterates over object keys)
- `for..of` (iterates over iterable values)
- `forEach` (method for arrays)


## 11. Searching MDN
- MDN fullform is Mozilla Developer Network
- The purpose of MDN in JavaScript is to serve as a comprehensive, reliable, and up-to-date documentation resource for developers


## 12. Popular Array Utility Methods
- `map()`
- `filter()`
- `reduce()`
- `find()`
- `indexOf`
- `includes()`
- `sort`
- `forEach()`
- `some()`, `every()`
- `push()`, `pop()`, `shift()`, `unshift()`





## 13. Popular String Utility Methods
- `split()`, `join()`
- `slice()`,`splice` ,`substring()`, `substr()`
- `replace()`
- `includes()`
- `trim()`
- `toLowerCase()`, `toUpperCase()`


## 14. Popular Object Utility Methods
- `Object.keys()`
- `Object.values()`
- `Object.entries()`
- `Object.assign()`
- `Object.freeze()`
- `Object.hasOwnProperty()`


## 15. When to Use forEach, map, filter, reduce
- `forEach()`: Execute logic, no return value.
- `map()`: Return new transformed array.
- `filter()`: Return new array with matching condition i.e it filter according to the condition and return the array.
- `reduce()`: Return single accumulated value.


## 16. Immutable and Mutable Methods
- **Immutable**: `map`, `filter`, `reduce`, `concat`, `slice`
- **Mutable**: `push`, `pop`, `splice`, `sort`, `reverse`


## 17. Error Handling (try-catch)
```js
try {
  // code that may throw error
} catch (err) {
  console.error(err.message);
}
```


## 18. Throwing Errors
```js
throw new Error("Something went wrong");
throw "String-based error";
```


## 19. Difference Between `throw new Error()` and `throw "string"`
- `new Error()` provides stack trace and structured error.
- Throwing a string provides no context.


## 20. Reading Error Messages and Stack Trace
- Stack trace shows where the error occurred.
- Helps trace bugs across function calls and file names.


## 21. Importance of Catch Block
- Prevents application from crashing.
- Allows fallback, error logging, user messages.


## 22. Spread Operator
```js
const arr = [1, 2];
const copy = [...arr];
```

Used for:
- Copying arrays/objects
- Merging
- Function arguments


## 23. Template Literals
```js
const name = "Dwipendu";
console.log(`Hello, ${name}`);
```


## 24. Default Parameters
```js
function greet(name = "Guest") {
  console.log(`Hi ${name}`);
}
```

## 25. Destructuring
```js
const obj = { name: "Dwipendu", age: 25 };
const { name, age } = obj;
```


## 26. Closures
- A function that remembers its lexical scope even when invoked outside.
```js
function outer() {
  let count = 0;
  return function inner() {
    return ++count;
  };
}
```


## 27. Arrow Functions vs Regular Functions
- No `this`, `arguments`, `super`, or `new.target`
- Cannot be used as constructor
- More concise syntax


## 28. === vs ==
- `==` allows type coercion.
- `===` checks both value and type (strict equality).


## 29. Why Use `value === undefined` Instead of `!value`
- `!value` returns true for `null`, `0`, `""`, `false`, `NaN` too.
- `=== undefined` is more precise.


## 30. Array Utility Method Chaining
```js
const result = arr
  .filter(x => x > 0)
  .map(x => x * 2)
  .reduce((a, b) => a + b);
```


## 31. null vs undefined
- `undefined`: Variable declared but not assigned.
- `null`: Assigned by developer to indicate empty value.


## 32. Importing/Exporting Modules using `require` and `module.exports`
```js
// file.js
module.exports = function() {...};

// main.js
const myFunc = require('./file.js');
```


## 33. console Methods
- `console.log()`
- `console.error()`
- `console.info()`
- `console.warn()`
- `console.table()`
- `console.time()` / `console.timeEnd()`

## 34. Best Practices
- Proper indentation
- Meaningful variable names
- Consistent loop variable naming
- Avoid globals
- Use `const` when possible
- Handle errors properly


## 35. Passing Functions to Other Functions
```js
function greet(name) {
  console.log("Hi", name);
}

function callFunction(fn, value) {
  fn(value);
}

callFunction(greet, "Dwipendu");
```


## 36. Named vs Anonymous Functions
- **Named**: Easier to debug, has identifier.
- **Anonymous**: Commonly used in callbacks or expressions.


## 37. Variable Number of Arguments to Functions
```js
function sum(...args) {
  return args.reduce((a, b) => a + b, 0);
}
```

