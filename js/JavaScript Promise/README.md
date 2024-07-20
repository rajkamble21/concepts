# Javascript Promise

---

## How JS executes the code?

JavaScript execution involves two main stages: creation and execution. These stages are managed within special environments called execution contexts.

**1. Creation Phase (Setting Up the Stage)**

* **Global Execution Context (GEC):** When your JavaScript code starts, the browser's JavaScript engine creates a global execution context (GEC). This context acts as the main container for your entire script.
  * **Global Object:** The GEC creates a special object, often called the "window" object in browsers and "global" in Node.js. This object holds global variables and functions accessible throughout your code.
  * **Memory Allocation:** Space is allocated in memory for variables and functions. Initially, variables are assigned the value "undefined" until they are assigned a real value.

**2. Execution Phase (Running the Play)**

* **Code Execution:** The JavaScript engine starts reading your code line by line within the GEC. It performs actions based on the code's instructions, like assigning values to variables, calling functions, and performing operations.
  * **Function Execution Contexts:** Whenever a function is called, a new execution context is created specifically for that function. This context keeps track of the function's arguments, local variables, and its own variable/function bindings.
  * **Call Stack:** The JavaScript engine uses a call stack to manage the order of function executions. When a function is called, its context is pushed onto the stack. When the function finishes running (usually by reaching a `return` statement), its context is popped from the stack, and execution resumes in the context where the function was called.

## Difference between Sync & Async code?

| Feature                | Synchronous (Sync) Code                             | Asynchronous (Async) Code                        |
|------------------------|-----------------------------------------------------|--------------------------------------------------|
| **Execution Flow**     | Executes tasks sequentially, one after the other.  | Executes tasks concurrently, allowing multiple tasks to run without waiting for previous ones to complete. |
| **Blocking**           | Blocks the execution until the current task is completed. | Non-blocking; tasks can be initiated and run in the background. |
| **Efficiency**         | Less efficient for I/O-bound tasks due to waiting time. | More efficient for I/O-bound tasks as it can handle other operations while waiting. |
| **Complexity**         | Simpler and easier to understand and debug.         | More complex, requires handling of callbacks, promises, or async/await syntax. |
| **Use Cases**          | Suitable for CPU-bound tasks and scenarios where tasks depend on the completion of previous tasks. | Ideal for I/O-bound tasks, such as network requests, file operations, or any scenario with potential waiting periods. |
| **Concurrency**        | Limited concurrency; each task must wait for the previous one to complete. | High concurrency; multiple tasks can be in progress simultaneously. |
| **Programming Languages** | Supported in all programming languages.            | Requires language or library support for async operations (e.g., JavaScript's Promises, Python's `asyncio`). |
| **Error Handling**     | Errors are easier to track and handle due to linear flow. | Error handling can be more complex due to the non-linear flow and multiple points of failure. |
| **Examples**           | Reading a file, processing it, and then writing it back. | Making multiple API calls, waiting for responses while continuing with other operations. |

## Ways to convert into Async code?

**1. Using Promises to Make an API Call in JavaScript**

```javascript
console.log('Start!');

setTimeout(() => {
  console.log('Timeout!');
}, 0);

Promise.resolve('Promise!')
  .then(res => console.log(res));

console.log('End!');
omise:

```javascript
function fetchData() {
  return fetch("https://api.example.com/data")
    .then(response => {
      if (!response.ok) {
        throw new Error('Network response was not ok ' + response.statusText);
      }
      return response.json();
    });
}

fetchData()
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Fetch error:', error);
  });
```

**2. Using async/await**

Using the Fetch API with async/await:

```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    if (!response.ok) {
      throw new Error('Network response was not ok ' + response.statusText);
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Fetch error:', error);
  }
}

fetchData();
```

**3. Using Axios**

Using Axios a third party library for making an API call:

```javascript
const axios = require('axios');

async function fetchData() {
  try {
    const response = await axios.get("https://api.example.com/data");
    console.log(response.data);
  } catch (error) {
    console.error('Axios error:', error);
  }
}

fetchData();
```

## What is the callstack & event loop?

- **Call Stack**: The call stack is a data structure used by the JavaScript engine to keep track of function calls. When a function is invoked, it is added to the top of the stack. When the function returns, it is removed from the top of the stack. The call stack ensures that the functions execute in the correct order.

- **Event Loop**: The event loop is a mechanism that allows JavaScript to perform non-blocking operations by offloading operations to the system (such as I/O operations) and then placing the results of these operations in a task queue once they complete. The event loop constantly checks the call stack to see if it’s empty. If the call stack is empty, it checks the task queues (macro and micro task queues) and pushes the first task to the call stack for execution.

  <img src="https://github.com/user-attachments/assets/9ed07470-9825-4b75-a5ca-f1ea608a7d24" alt="RESTAPI" style="width:700px; height:400px;" />

- **Execution Steps**

1. `console.log('Start!')` is executed and prints "Start!" to the console.
2. `setTimeout(() => { console.log('Timeout!'); }, 0)` is called. This schedules the provided callback function to be executed after 0 milliseconds, and the function is placed in the Web API environment.
3. `Promise.resolve('Promise!')` creates a resolved promise and the provided `.then` callback is placed in the microtask queue.
4. `console.log('End!')` is executed and prints "End!" to the console.

**After Synchronous Code Execution Completes:**

1. The event loop finds the microtask queue is not empty and executes the `.then` callback, printing "Promise!" to the console.
2. Then, the event loop moves to the macrotask queue and finds the `setTimeout` callback, executing it and printing "Timeout!" to the console.

## What is Async and how callback will be useful for it?


In JavaScript, **async** refers to asynchronous programming, which allows tasks to run in the background without blocking the main execution thread. This is crucial for tasks like fetching data from a server, where waiting for a response would otherwise freeze the application.

A **callback** is a function passed as an argument to another function, which is then executed after the completion of an operation. Callbacks are a fundamental part of handling asynchronous behavior in JavaScript.

- How **Callbacks Are Useful**

1. **Non-blocking**: Callbacks allow you to perform operations without stopping the execution of other code.
2. **Event Handling**: Commonly used in event-driven programming to execute code in response to user actions.
3. **Chaining**: Can be used to perform sequential asynchronous operations.

```javascript
function fetchData(callback) {
  setTimeout(() => {
    const data = "Data fetched";
    callback(data);
  }, 1000);
}

function handleData(data) {
  console.log(data);
}

fetchData(handleData);
```

## What is inversion of control and callback hell?

**Inversion of Control (IoC)** is a design principle where the control of objects or portions of a program is transferred to a framework or another part of the code. In the context of JavaScript, this often occurs when you pass functions (callbacks) to other functions or libraries that then control when and how those callbacks are executed.

**Callback Hell** refers to the situation where callbacks are nested within other callbacks, creating a pyramid-like structure that makes code difficult to read and maintain. This can happen when multiple asynchronous operations are chained together.

```javascript
doSomething(data => {
  doSomethingElse(data, moreData => {
    doAnotherThing(moreData, finalData => {
      doFinalThing(finalData, () => {
        console.log("All done!");
      });
    });
  });
});
```

## What is promise and what problem does promise is solving?

A **Promise** in JavaScript is an object that represents the eventual completion or failure of an asynchronous operation. Promises provide a cleaner and more manageable way to handle asynchronous tasks compared to callbacks.

1. **Readability**: Promises allow for chaining operations, making code more readable and organized.
2. **Error Handling**: Promises provide a structured way to handle errors with `.catch()`.
3. **Avoiding Callback Hell**: By flattening nested callbacks, Promises reduce complexity and improve code structure.

```javascript
let promise = new Promise((resolve, reject) => {
  // Asynchronous operation
  let success = true;
  
  if (success) {
    resolve("Operation successful");
  } else {
    reject("Operation failed");
  }
});

promise
  .then(result => {
    console.log(result); // "Operation successful"
  })
  .catch(error => {
    console.error(error); // "Operation failed"
  });
```

## What are different stages in promise?

A Promise in JavaScript can be in one of three states:

1. **Pending**: The initial state, neither fulfilled nor rejected.
2. **Fulfilled**: The operation completed successfully, and the promise is resolved with a result.
3. **Rejected**: The operation failed, and the promise is rejected with an error.

```javascript
let promise = new Promise((resolve, reject) => {
  let success = true;

  if (success) {
    resolve("Operation successful"); // Transition to Fulfilled
  } else {
    reject("Operation failed"); // Transition to Rejected
  }
});

promise
  .then(result => {
    console.log(result); // "Operation successful" if Fulfilled
  })
  .catch(error => {
    console.error(error); // "Operation failed" if Rejected
  });
```

## How to create a promise? How to consume a promise?

A promise can be created using the `Promise` constructor, which takes a function with two parameters: `resolve` and `reject`. Here's an example:

```javascript
// Create a new promise
const myPromise = new Promise((resolve, reject) => {
  // Simulate an asynchronous operation using setTimeout
  setTimeout(() => {
    const success = true; // Change to false to simulate a rejection

    if (success) {
      resolve("Operation was successful!"); // Resolves the promise
    } else {
      reject("Operation failed!"); // Rejects the promise
    }
  }, 2000); // 2 seconds delay
});
```

You can consume a promise using the `.then()`, `.catch()`, and `.finally()` methods. These methods allow you to handle the resolved value, handle errors, and execute code regardless of the outcome, respectively.

```javascript
// Consume the promise
myPromise
  .then((message) => {
    console.log("Success:", message); // Handle the resolved value
  })
  .catch((error) => {
    console.error("Error:", error); // Handle any error
  })
  .finally(() => {
    console.log("Promise has been handled."); // Execute code regardless of outcome
  });
```

## Chaining of promise using .then?

You can chain multiple `.then()` methods to handle a sequence of asynchronous operations. Each `.then()` returns a new promise, allowing for a chain of operations.

```javascript
// Create a promise
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(10); // Resolving with an initial value
  }, 1000); // 1 second delay
});

// Chain of promises using .then()
myPromise
  .then((value) => {
    console.log("First then:", value); // First then: 10
    return value * 2; // Returning a new value
  })
  .then((newValue) => {
    console.log("Second then:", newValue); // Second then: 20
    return newValue + 5; // Returning another new value
  })
  .then((finalValue) => {
    console.log("Final then:", finalValue); // Final then: 25
  })
  .catch((error) => {
    console.error("Error:", error); // Handle any error in the chain
  });
```

## How to handle errors in promises?

Errors in promises can be handled using the `.catch()` method. This method is called when any promise in the chain is rejected. You can also use the `.finally()` method to execute code regardless of whether the promise was fulfilled or rejected.

```javascript
// Create a promise that rejects
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject("Something went wrong!"); // Rejects the promise
  }, 1000); // 1 second delay
});

// Handle errors with .catch()
myPromise
  .then((value) => {
    console.log("This will not be called", value);
  })
  .catch((error) => {
    console.error("Error caught:", error); // Handle the error
  })
  .finally(() => {
    console.log("Promise has been handled."); // Execute code regardless of outcome
  });
```

## How different promise based functions works ( Promise.all, Promise.race etc. )

JavaScript provides several utility functions for working with promises, such as `Promise.all()`, `Promise.race()`, `Promise.allSettled()`, and `Promise.any()`. These functions allow you to handle multiple promises concurrently.

### Promise.all()

`Promise.all()` takes an array of promises and returns a single promise that resolves when all of the promises in the array have resolved. If any promise rejects, the resulting promise rejects with that reason.

```javascript
const promise1 = Promise.resolve(3);
const promise2 = 42;
const promise3 = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, 'foo');
});

Promise.all([promise1, promise2, promise3]).then((values) => {
  console.log(values); // [3, 42, "foo"]
}).catch((error) => {
  console.error("Error:", error);
});
```

### Promise.race()

`Promise.race()` takes an array of promises and returns a single promise that resolves or rejects as soon as one of the promises in the array resolves or rejects.


```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(resolve, 500, 'one');
});
const promise2 = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, 'two');
});

Promise.race([promise1, promise2]).then((value) => {
  console.log(value); // "two"
}).catch((error) => {
  console.error("Error:", error);
});
```

### Promise.allSettled()

`Promise.allSettled()` takes an array of promises and returns a single promise that resolves when all of the promises have settled (either resolved or rejected). The result is an array of objects that each describe the outcome of each promise.

```javascript
const promise1 = Promise.resolve(3);
const promise2 = new Promise((resolve, reject) => {
  setTimeout(reject, 100, 'foo');
});
const promise3 = 42;

Promise.allSettled([promise1, promise2, promise3]).then((results) => {
  results.forEach((result) => console.log(result));
  // { status: 'fulfilled', value: 3 }
  // { status: 'rejected', reason: 'foo' }
  // { status: 'fulfilled', value: 42 }
});
```

### Promise.any()

`Promise.any()` takes an array of promises and returns a single promise that resolves as soon as any of the promises in the array resolves. If all promises reject, it rejects with an `AggregateError` containing all rejection reasons.

```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(reject, 100, 'foo');
});
const promise2 = new Promise((resolve, reject) => {
  setTimeout(resolve, 200, 'bar');
});
const promise3 = new Promise((resolve, reject) => {
  setTimeout(reject, 300, 'baz');
});

Promise.any([promise1, promise2, promise3]).then((value) => {
  console.log(value); // "bar"
}).catch((error) => {
  console.error("All promises rejected:", error.errors);
  // AggregateError: All promises were rejected
  // error.errors: ["foo", "baz"]
});
```

## What is async..await & why do we use it?

`async` and `await` are syntax features in JavaScript that allow you to write asynchronous code in a more readable and synchronous-looking manner. They are built on top of promises and provide a way to work with asynchronous operations using a more imperative style.

The `async` keyword is used to define an asynchronous function. An `async` function always returns a promise. If the function returns a value, the promise is resolved with that value. If the function throws an error, the promise is rejected with that error.

The `await` keyword is used to pause the execution of an `async` function until a promise is settled (resolved or rejected). It can only be used inside `async` functions.

**Why do we use `async`/`await`?**

- **Readability**: `async`/`await` makes asynchronous code look and behave more like synchronous code, which is easier to read and understand.
- **Error Handling**: You can use `try...catch` blocks to handle errors in `async` functions, similar to synchronous code.
- **Maintainability**: Code written with `async`/`await` tends to be easier to maintain and debug.

```javascript
// Simulate an asynchronous operation using a promise
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Data fetched successfully!");
    }, 2000); // 2 seconds delay
  });
}

// Define an async function
async function getData() {
  try {
    console.log("Fetching data...");
    const data = await fetchData(); // Wait for the promise to resolve
    console.log(data); // Logs: "Data fetched successfully!"
  } catch (error) {
    console.error("Error:", error);
  }
}

// Call the async function
getData();
```




