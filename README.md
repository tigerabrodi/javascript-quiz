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

10. **What are template literals in JavaScript?**

11. **Could you explain the prototype inheritance in JavaScript?**

12. **What is the execution context in JavaScript and how is it created?**

13. **What is the difference between an arrow function and a regular function in JavaScript?**

14. **How would you implement inheritance in JavaScript?**

15. **Can you describe what a JavaScript 'class' is and how it works under the hood?**

16. **What is event delegation and why is it useful?**

17. **How does the `this` keyword work in JavaScript?**

18. **What are JavaScript modules, and how do they work?**

19. **Can you explain what a RESTful API is and how it relates to JavaScript?**

20. **What are the new features introduced in ES6 (ECMAScript 2015)?**
