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

Using the Fetch API, which returns a Pr### Call Stack and Event Loop in JavaScript

#### Call Stack
- **Call Stack**: Keeps track of function calls. Functions are added (pushed) to the stack when invoked and removed (popped) when they return.

#### Event Loop
- **Event Loop**: Manages asynchronous operations. Checks the call stack for empty status and then processes tasks from the queues.

#### Example Execution:
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

![microtask3-a2c6b052fe90284a88f725ac0037a3f1](https://github.com/user-attachments/assets/9ed07470-9825-4b75-a5ca-f1ea608a7d24)

- **Call Stack**: The call stack is a data structure used by the JavaScript engine to keep track of function calls. When a function is invoked, it is added to the top of the stack. When the function returns, it is removed from the top of the stack. The call stack ensures that the functions execute in the correct order.

- **Event Loop**: The event loop is a mechanism that allows JavaScript to perform non-blocking operations by offloading operations to the system (such as I/O operations) and then placing the results of these operations in a task queue once they complete. The event loop constantly checks the call stack to see if it’s empty. If the call stack is empty, it checks the task queues (macro and micro task queues) and pushes the first task to the call stack for execution.

- **Execution Steps**

1. `console.log('Start!')` is executed and prints "Start!" to the console.
2. `setTimeout(() => { console.log('Timeout!'); }, 0)` is called. This schedules the provided callback function to be executed after 0 milliseconds, and the function is placed in the Web API environment.
3. `Promise.resolve('Promise!')` creates a resolved promise and the provided `.then` callback is placed in the microtask queue.
4. `console.log('End!')` is executed and prints "End!" to the console.

**After Synchronous Code Execution Completes:**

1. The event loop finds the microtask queue is not empty and executes the `.then` callback, printing "Promise!" to the console.
2. Then, the event loop moves to the macrotask queue and finds the `setTimeout` callback, executing it and printing "Timeout!" to the console.




