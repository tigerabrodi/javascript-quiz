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

6. **What is event bubbling in the context of the DOM?**

7. **Can you explain the concept of hoisting in JavaScript?**

8. **What is the difference between `==` and `===` in JavaScript?**

9. **How do you make a function wait for the completion of a Promise?**

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
