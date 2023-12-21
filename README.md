# JavaScript Quiz

A rapid quiz with questions and answers.

1. **What is the difference between `var`, `let`, and `const` in JavaScript?**

var is function scoped, let and const are block scoped. var can be redeclared and updated, let can be updated but not redeclared, const can neither be updated nor redeclared. They are all hoisted to the top of their scope. var and let can be declared without being initialized, const must be initialized during declaration.

This is what redeclaration looks like:

```javascript
var name = "David";
var name = "John";
console.log(name); // John
```

2. **How does JavaScript handle asynchronous operations?**

Handled using callbacks, Promises, and async/await. These constructs allow JavaScript to perform non-blocking operations.

Non-blocking operations are operations that allow other code to be executed while they are being processed.

**How does it work under the hood?**

JavaScript has a single thread, which means it can only execute a single task at a time. However, if it encounters an asynchronous operation, instead of waiting for it to complete, it registers a callback function and moves to the next task. When the asynchronous operation completes, it looks up the appropriate callback function and executes it. This way, it can handle multiple asynchronous operations at a time.

**Where does it register the callback function?**

In the event loop. That is a queue of callback functions that are waiting to be executed.

**How does it know when the async operation is completed?**

It uses the event loop to monitor the program’s execution stack and callback queue. When the stack is empty, it takes the first callback from the queue and pushes it onto the stack.

**What happens if the stack is not empty?**

The callback will have to wait in the queue until the stack is empty.

3. **Can you explain what a closure is in JavaScript?**

Closure in JavaScript is when a function is able to remember and access its lexical scope even when that function is executing outside its lexical scope.

**What is the lexical scope?**

Lexical scope refers to the visibility of variables. In JavaScript, a variable defined outside a function can be accessed inside another function defined after the variable declaration. But the opposite is not true. A variable defined inside a function is not accessible outside the function.

**What does it mean for a function to remember and access its lexical scope?**

It means that a function can access variables defined outside of it. For example:

```javascript
function outer() {
  const name = "David"; // name is a lexical variable

  function inner() {
    console.log(name); // inner can access the name variable of the outer function
  }

  return inner;
}

const foo = outer();
foo(); // Here, inner is executed outside its lexical scope
```

**Where is the outside part of lexical scope?**

The outside part refers to `inner` function being executed outside the `outer` function.

4. **What is the purpose of a `Promise` in JavaScript?**

A `Promise` is an object that represents the eventual completion or failure of an asynchronous operation. It allows us to write asynchronous code that looks like synchronous code.

The result of a `Promise` acts as a placeholder for the value that will be available in the future.

5. **How would you check if an object is an array in JavaScript?**

```javascript
Array.isArray(obj);
```

6. **What is event bubbling in the context of the DOM?**

Event bubbling refers to the order in which events are handled. Let's say we have a `<div>` element inside a `<form>` element, both of which have an `onclick` event handler attached to them. If we click on the `<div>` element, the event will bubble up from the `<div>` to the `<form>` element. This means that the `<div>` element's `onclick` event handler will be executed first, followed by the `<form>` element's `onclick` event handler.

The event bubbles up from the innermost element to the outermost element. This is called event bubbling.

7. **Can you explain the concept of hoisting in JavaScript?**

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. This means that if we try to access a variable before it is declared, it will not throw an error. Instead, it will return `undefined`.

For `var` and `function` declarations, JavaScript moves them to the top of their scope before code execution. This means that we can access them before they are declared. However, note that only the declarations are hoisted, not the initializations.

For `let` and `const` declarations, JavaScript does not move them to the top of their scope. This means that we cannot access them before they are declared. You will get a `ReferenceError` if you try to access them before they are declared.

For function expressions and arrow functions, they are not hoisted. This means that we cannot access them before they are declared. You will get a `ReferenceError` if you try to access them before they are declared.

For class declarations, they are not hoisted.

8. **What is the difference between `==` and `===` in JavaScript?**

`==` is used for comparison, while `===` is used for strict comparison. The difference between them is that `==` converts the operands to the same type before making the comparison. This is called type coercion. `===` does not perform type coercion.

9. **How do you make a function wait for the completion of a Promise?**

Using the `await` keyword. The `await` keyword can only be used inside an `async` function. It makes the function wait for the completion of a Promise before moving on to the next line of code.

If you do not want to wait for the completion of a Promise, you can use the `then()` method instead.

```javascript
fetch("https://api.example.com/data")
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
// Code here will execute without waiting for the fetch to complete
```

10. **What are template literals in JavaScript?**

Template literals are string literals that allow embedded expressions. They are enclosed by the backtick (`) character instead of double or single quotes.

11. **Could you explain the prototype inheritance in JavaScript?**

Every object in JavaScript has a prototype. The prototype is an object that contains properties and methods that the object can access. When we try to access a property or method of an object, JavaScript first looks at the object itself. If it cannot find the property or method, it looks at the object's prototype. If it still cannot find the property or method, it looks at the prototype's prototype. This process continues until it reaches the end of the prototype chain.

12. **What is the execution context in JavaScript and how is it created?**

The execution context is an abstract concept that holds information about the environment in which the current code is being executed. It consists of the scope chain, variable declarations, function declarations, and the value of the `this` keyword.

13. **What is the difference between an arrow function and a regular function in JavaScript?**

The arrow function is a shorthand for a regular function. It does not have its own `this` keyword, so it uses the `this` keyword of its surrounding lexical scope.

Function declarations are hoisted, while arrow functions are not.

Function declarations have their own `this` keyword.

14. **How would you implement inheritance in JavaScript?**

Using the `extends` keyword. The `extends` keyword allows us to create a child class that inherits from a parent class.

We can also use the `Object.create()` method to create an object that inherits from another object.

How to use `Object.create()` with objects:

```javascript
const parent = {
  name: "David",
  age: 30,
};

const child = Object.create(parent);
console.log(child.name); // David
console.log(child.age); // 30
```

15. **Can you describe what a JavaScript 'class' is and how it works under the hood?**

Classes are a way to create objects with the same properties and methods. They are syntactic sugar for the constructor function pattern.

Classes don't exist in JavaScript like other programming languages. They are just syntactic sugar for the constructor function pattern. When you create a class, JavaScript creates a constructor function and a prototype object for you.

16. **What is event delegation and why is it useful?**

Event delegation is a technique where we attach a single event listener to a parent element instead of attaching multiple event listeners to multiple child elements. This is useful because it allows us to attach event listeners to dynamically added elements.

An example would be where parent captures different types of events from its children. For example, if we have a `<ul>` element with multiple `<li>` elements inside it, we can attach a single event listener to the `<ul>` element instead of attaching multiple event listeners to each `<li>` element.

Each `li` element could have a `data-id` attribute that identifies it. When the event is triggered, we can check the `data-id` attribute of the target element to determine which `<li>` element was clicked.

17. **How does the `this` keyword work in JavaScript?**

The `this` keyword refers to the object that is executing the current function. It is determined by how a function is called.

If a function is called with the `new` keyword, `this` refers to the newly created object.

If a function is called with the `call()` or `apply()` method, `this` refers to the object that is passed as the first argument.

If a function is called with the `bind()` method, `this` refers to the object that is passed as the first argument.

If a function declaration, then `this` refers to the global object.

If an arrow function, then `this` refers to the surrounding lexical scope.

If a function is called as a method of an object, `this` refers to the object that the method is called on.

Let's take a look at call, apply and bind:

```javascript
const person = {
  name: "David",
  age: 30,
};

function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

greet.call(person, "Hello"); // Hello, my name is David
greet.apply(person, ["Hello"]); // Hello, my name is David
greet.bind(person, "Hello")(); // Hello, my name is David
```

- `call()` takes the object as the first argument, followed by the arguments to the function.
- `apply()` takes the object as the first argument, followed by an array of arguments to the function.
- `bind()` returns a new function with the object as the `this` keyword.
