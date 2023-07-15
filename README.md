# CoreModuleAssign4

**Q.1 Explain Hoisting in JavaScript**

Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope before the code execution takes place. This means that regardless of where variables and functions are declared in the code, they are treated as if they are declared at the beginning of their scope.

In the case of variable hoisting, only the declaration is hoisted, not the initialization. This means that the variable is assigned the value `undefined` by default until the actual assignment is made later in the code.

For example:

```javascript
console.log(x); // undefined
var x = 10;
```

In the above code, the variable `x` is hoisted to the top, so it is accessible before the actual declaration. However, its value is `undefined` until the assignment is made. Therefore, the first `console.log()` statement prints `undefined`.

Function declarations are also hoisted. This means that you can call a function before its actual declaration in the code.

```javascript
foo(); // "Hello"

function foo() {
  console.log("Hello");
}
```

In the above code, the function `foo` is hoisted to the top, so it can be called before its actual declaration.

It's important to note that hoisting only applies to function declarations and variable declarations using the `var` keyword. Variables declared with `let` and `const` are not hoisted, and they stay in the temporal dead zone until they are declared.

**Q.2 Explain Temporal Dead Zone?**

The Temporal Dead Zone (TDZ) is a behavior that occurs with variables declared using `let` and `const` in JavaScript. It's a phase in the code where variables are not yet initialized and cannot be accessed. It exists from the start of the scope until the declaration is encountered.

During the TDZ, if you try to access a variable declared with `let` or `const`, a `ReferenceError` will be thrown. This behavior is designed to catch potential issues caused by accessing variables before they are assigned a value.

For example:

```javascript
console.log(x); // ReferenceError: x is not defined
let x = 10;
```

In the above code, trying to access the variable `x` before its declaration results in a `ReferenceError` due to the TDZ.

The TDZ is a mechanism to enforce better coding practices and prevent bugs caused by accessing variables before they are initialized. It encourages developers to declare variables at the top of their scope to avoid confusion and potential errors.

**Q.3 Difference between `var` & `let`?**

The main differences between `var` and `let` in JavaScript are as follows:

1. **Scope:** Variables declared with `var` are function-scoped, meaning they are accessible throughout the entire function in which they are defined. On the other hand, variables declared with `let` are block-scoped, which means they are limited to the block (enclosed by curly braces) in which they are defined.

2. **Hoisting:** Variable declarations using `var` are hoisted to the top of their containing function or global scope, allowing them to be accessed before their actual declaration in the code. Declarations using `let` are not hoisted and stay in the temporal dead zone until they are declared.

3. **Reassignment:** Variables declared with `var` can be redeclared and reassigned within their scope. In contrast, variables declared with `let` can be reassigned within their scope but cannot be redeclared in the same scope.

4. **Global scope behavior:** Variables declared with `var` in the global scope become properties of the global object (e.g., `window` object in browsers). Variables declared with `let` in the global scope do not become properties of the global object.

Given these differences, using `let` is generally recommended over `var` because it promotes better scoping and helps prevent issues such as variable hoisting and accidental redeclaration.

**Q.4 What are the major features introduced in ECMAScript 6?**

ECMAScript 6, also known as ES6 or ECMAScript 2015, introduced several significant features and improvements to the JavaScript language. Some of the major features introduced in ES6 are:

1. **Block-Scoped Declarations (`let` and `const`):** The `let` and `const` keywords were introduced to declare variables with block scope, improving scoping and replacing the sometimes problematic behavior of `var`.

2. **Arrow Functions:** Arrow functions provide a concise syntax for writing function expressions. They have a lexically bound `this` value and do not have their own `this`, `arguments`, `super`, or `new.target` bindings.

3. **Classes:** ES6 introduced the `class` syntax for defining classes, providing a more convenient and familiar way to work with prototype-based inheritance. Classes in ES6 are syntactical sugar over JavaScript's existing prototype-based inheritance model.

4. **Modules:** ES6 introduced a standardized module system for JavaScript using the `import` and `export` keywords. Modules allow for better organization of code, encapsulation of functionality, and support for asynchronous loading.

5. **Template Literals:** Template literals provide an improved syntax for creating strings, allowing embedded expressions and multiline strings. They are enclosed by backticks (` `) instead of single or double quotes.

6. **Default Parameters:** Default parameter values allow developers to specify default values for function parameters, reducing the need for manual checks for undefined or missing arguments.

7. **Destructuring Assignment:** Destructuring assignment provides a concise way to extract values from arrays or objects into individual variables. It simplifies code when working with complex data structures.

8. **Spread Operator (`...`):** The spread operator allows for the expansion of iterable objects (e.g., arrays, strings, objects) into multiple elements. It simplifies tasks like copying arrays, merging objects, and passing multiple arguments to functions.

9. **Enhanced Object Literals:** ES6 enhanced object literals with shorthand syntax for defining object properties and methods, computed property names, and the ability to set the prototype of an object.

10. **Promises:** Promises provide a cleaner and more readable syntax for asynchronous programming compared to traditional callback-based approaches. They make it easier to handle asynchronous operations and avoid callback hell.

These are just a few of the major features introduced in ECMAScript 6. ES6 brought significant improvements to JavaScript, making the language more expressive, concise, and developer-friendly.

**Q.5 What is the difference between `let` and `const`?**

The main difference between `let` and `const` in JavaScript is as follows:

- `let`: Variables declared with `let` can be reassigned with a new value. Their value can be changed throughout the program execution.
  
  Example:
  ```javascript
  let x = 10;
  x = 20; // Reassignment is allowed
  ```

- `const`: Variables declared with `const` are constants, which means their value cannot be changed or reassigned after initialization. They are read-only.

  Example:
  ```javascript
  const x = 10;
  x = 20; // Error: Assignment to constant variable
  ```

In summary, `let` is used for variables that can have their values changed during the program execution, while `const` is used for variables that are meant to be

 constant and should not be reassigned. Both `let` and `const` are block-scoped, meaning they are limited to the block (enclosed by curly braces) in which they are defined.

It's important to note that when using `const` with objects and arrays, the variable itself is still constant (cannot be reassigned), but the properties or elements of the object or array can be modified. This is because the constness applies to the binding between the variable name and the value, not the value itself.

**Q.6 What is template literals in ES6 and how do you use them?**

Template literals, introduced in ES6, provide an enhanced way to create strings in JavaScript. They allow for easier interpolation of variables and expressions within strings, multiline strings, and improved readability compared to traditional string concatenation.

Template literals are created using backticks (` `) instead of single or double quotes. Within a template literal, placeholders (expressions) can be embedded using the `${expression}` syntax. The expressions within the placeholders are evaluated and the results are inserted into the string.

Here's an example:

```javascript
const name = "Alice";
const age = 25;

const message = `My name is ${name} and I'm ${age} years old.`;

console.log(message);
```

The output of the above code will be:

```
My name is Alice and I'm 25 years old.
```

In the example, the variables `name` and `age` are embedded within the template literal using `${}`. The expressions inside the placeholders are evaluated and the results are interpolated into the final string.

Template literals also support multiline strings without the need for manual line breaks using escape characters. For example:

```javascript
const multiline = `
  This is a
  multiline
  string.
`;

console.log(multiline);
```

The output will preserve the multiline formatting:

```
  This is a
  multiline
  string.
```

Template literals provide a more flexible and readable way to create strings in JavaScript, especially when working with dynamic content or multiline text.

**Q.7 What's the difference between `map` and `forEach`?**

In JavaScript, both `map` and `forEach` are array methods used for iteration, but they differ in their behavior and purpose:

- `forEach`: The `forEach` method executes a provided callback function once for each element in an array. It does not create a new array but instead iterates over each element and performs the specified action. The return value of the callback function is ignored.

  Example:
  ```javascript
  const numbers = [1, 2, 3];

  numbers.forEach((number) => {
    console.log(number);
  });
  ```

  Output:
  ```
  1
  2
  3
  ```

- `map`: The `map` method creates a new array by applying a provided callback function to each element in an existing array. It performs a transformation on each element and returns a new array with the transformed values. The return value of the callback function for each element becomes the corresponding element in the new array.

  Example:
  ```javascript
  const numbers = [1, 2, 3];

  const doubledNumbers = numbers.map((number) => {
    return number * 2;
  });

  console.log(doubledNumbers);
  ```

  Output:
  ```
  [2, 4, 6]
  ```

In summary, `forEach` is used for iterating over array elements and performing actions for each element, without creating a new array. `map` is used for transforming each element of an array and creating a new array with the transformed values. The choice between `forEach` and `map` depends on whether you need to modify the array or create a new array with transformed values.

**Q.8 How can you destructure objects and arrays in ES6?**

In ES6, destructuring assignment allows you to extract values from objects or arrays and assign them to variables in a concise and convenient way. It simplifies the process of extracting multiple values from complex data structures.

**Destructuring Objects:**

To destructure an object, you use curly braces `{}` and provide the variable names that correspond to the object's property names. The variable names on the left-hand side of the assignment are matched with the property names on the right-hand side.

Here's an example:

```javascript
const person = { name: 'Alice', age: 25 };

const { name, age } = person;

console.log(name); // 'Alice'
console.log(age);  // 25
```

In the example, the `person` object is destructured, and the variables `name` and `age` are assigned the corresponding values from the object.

**Destructuring Arrays:**

To destructure an array, you use square brackets `[]` and provide variable names for the desired elements in the array. The order of the variables corresponds to the order of the array elements.

Here's an example:

```javascript
const numbers = [1, 2, 3];

const [first, second, third] = numbers;

console.log(first);  // 1
console.log(second); // 2
console.log(third);  // 3
```

In the example, the `numbers` array is destructured, and the variables `first`, `second`, and `third` are assigned the corresponding values from the array.

Destructuring can also be used with default values and nested objects or arrays for more complex scenarios.

**Q.9 How can you define default parameter values in ES6 functions?**

In ES6, you can define default parameter values for function parameters using the assignment operator (`=`). Default parameter values allow you to specify values that will be used if the corresponding argument is missing or `undefined`.

Here's an example:

```javascript
function greet(name = 'Guest') {
  console.log(`Hello, ${name}!`);
}

greet();          // Hello, Guest!
greet('Alice');   // Hello, Alice!
```

In the `greet` function, the `name` parameter is assigned a default value of `'Guest'`. If no argument is provided when calling the function, or if the argument is `undefined`, the default value will be used. If an argument is provided, it overrides the default value.

Default parameter values are evaluated at the time of function call, so they can be expressions or even reference other parameters:

```javascript
function calculateTotal(price, quantity = 1, taxRate = 0.1) {
  const total = price * quantity * (1 + taxRate);
  console.log(`Total: $${total}`);
}

calculateTotal(10);              // Total: $11
calculateTotal(20, 2);           // Total: $44
calculateTotal(30, 3, 0.05);     // Total: $94.5
```

In the example, the `calculateTotal` function calculates the total price by multiplying the `price`, `quantity`, and `taxRate` parameters. If `quantity` or `taxRate` are not provided, they will default to `1` and `0.1` respectively.

Default parameter values in ES6 provide a convenient way to handle missing or undefined function arguments, reducing the need for explicit checks within the function body.

**Q.10 What is the purpose of the spread operator (`...`) in ES6?**

In ES6, the spread operator (`...`) is used to expand elements of an iterable (e.g., arrays, strings, objects) into multiple elements. It provides a concise and flexible syntax for working with arrays and function arguments.

The spread operator can be used in different contexts:

**1. Array Spreading:**

```javascript
const numbers = [1, 2, 3];
const expandedNumbers = [...numbers, 4, 5];

console.log(expandedNumbers); // [1, 2, 3, 4, 5]
```

In the example, the spread operator is used to expand the elements of the `numbers` array into individual elements. These elements are then combined with the additional values `[4, 5]` to create the `expandedNumbers` array.

**2. Function Arguments:**

The spread operator can also be used to pass multiple arguments to a function.

```javascript
function sum(a, b, c) {
  return a + b + c;
}

const numbers = [1, 2, 3];
const result = sum(...numbers);

console.log(result); // 6
```

In the example, the spread operator is used to pass the elements of the `numbers` array as individual arguments to the `sum` function. This allows the function to work with the array elements as separate parameters.

**3. Object Spreading:**

In ES9 (ES2018) and later versions, the spread operator can also be used to spread the properties of an object into another object.

```javascript
const obj1 = { x: 1, y: 2 };
const obj2 = { ...obj1, z: 3 };

console.log(obj2); // { x: 1, y: 2, z: 3 }
```

In the example, the spread operator is used to spread the properties of `obj1` into `obj2`, along with the additional property `z: 3`. This creates a new object with all the properties from `obj1` and the added property `z`.

The spread operator is a powerful feature in ES6 that simplifies working with arrays, function arguments, and object properties. It provides a concise syntax for combining, expanding, and manipulating data in various contexts.
