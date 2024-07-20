### Javascript Promise

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



