# How do you read attributes from the element in the event listener function?

To read attributes from an element within an event listener function in JavaScript, you can access the `event` object that is passed to the event listener. The `event` object has a property called `target`, which references the element that triggered the event. From there, you can use standard DOM methods like `getAttribute`, or directly access properties of the element to read its attributes.

### Example:

Suppose you have a button element with a custom attribute `data-info`, and you want to read it when the button is clicked:

```html
<button id="myButton" data-info="Some Info">Click Me</button>
```

You can use the following JavaScript:

```javascript
document.getElementById("myButton").addEventListener("click", function (event) {
  // Access the element that triggered the event
  const element = event.target;
  // Read the 'data-info' attribute
  const info = element.getAttribute("data-info");

  // Alternatively, you can use dataset for data-* attributes
  // const info = element.dataset.info;

  console.log(info); // Outputs: 'Some Info'
});
```

# How do you read attributes from the element in the event listener function?

To set attributes to an element within an event listener function in JavaScript, you can use the `setAttribute` method or directly assign values to the properties of the element. The process is similar to reading attributes, but instead, you modify or add attributes.

### Example:

Suppose you want to set a `data-info` attribute to a button element when it’s clicked:

```html
<button id="myButton">Click Me</button>
```

You can use the following JavaScript:

```javascript
document.getElementById("myButton").addEventListener("click", function (event) {
  // Access the element that triggered the event
  const element = event.target;

  // Set the 'data-info' attribute
  element.setAttribute("data-info", "Updated Info");

  // Alternatively, for standard attributes like 'id', you can set it directly
  // element.id = 'newButtonId';

  console.log(element.getAttribute("data-info")); // Outputs: 'Updated Info'
});
```

# What is Event.preventDefault()?

# What is Event.stopPropagation()?

# What is Event.stopImmediatePropagation()?

# How do they work with forms, buttons, etc?

### 1. **`Event.preventDefault()`**

**Definition:**
`Event.preventDefault()` is a method that cancels the default action that belongs to the event. For example, if you click on a link, the default action is to navigate to the linked URL. By using `preventDefault()`, you can stop this navigation.

**How It Works:**
When an event is triggered on an element (like submitting a form, clicking a link, or pressing a button), the browser performs a default action. `preventDefault()` can be used to prevent this action.

**Example with a Form:**

```html
<form id="myForm">
  <input type="text" placeholder="Enter something" />
  <button type="submit">Submit</button>
</form>
```

```javascript
document.getElementById("myForm").addEventListener("submit", function (event) {
  event.preventDefault(); // Prevents the form from submitting
  alert("Form submission has been prevented!");
});
```

**Use Cases:**

- Preventing form submission to validate input via JavaScript.
- Preventing link navigation for custom behavior.
- Disabling context menu (right-click) or other default browser actions.

### 2. **`Event.stopPropagation()`**

**Definition:**
`Event.stopPropagation()` stops the event from bubbling up the event chain. This means that the event is not propagated to parent elements.

**How It Works:**
When an event occurs, it normally propagates (or bubbles) up from the target element to its parent elements. Using `stopPropagation()` will stop this from happening, so the event won't trigger handlers on parent elements.

**Example with Nested Elements:**

```html
<div id="parent">
  <button id="child">Click Me</button>
</div>
```

```javascript
document.getElementById("parent").addEventListener("click", function () {
  alert("Parent clicked");
});

document.getElementById("child").addEventListener("click", function (event) {
  event.stopPropagation(); // Prevents the click event from reaching the parent
  alert("Button clicked");
});
```

**Use Cases:**

- Preventing parent elements from reacting to child element events.
- Controlling event flow in complex UI structures.

### 3. **`Event.stopImmediatePropagation()`**

**Definition:**
`Event.stopImmediatePropagation()` stops the event from being propagated to any other event listeners attached to the same element or any other elements. Unlike `stopPropagation()`, which only prevents event bubbling, `stopImmediatePropagation()` prevents all subsequent event listeners from executing.

**How It Works:**
When an event is triggered, all event listeners on the element are called in the order they were added. `stopImmediatePropagation()` stops any other listeners from being called, including those on the same element.

**Example:**

```html
<button id="myButton">Click Me</button>
```

```javascript
document.getElementById("myButton").addEventListener("click", function () {
  alert("First listener");
});

document.getElementById("myButton").addEventListener("click", function (event) {
  event.stopImmediatePropagation(); // Stops all other listeners
  alert("Second listener and stopping");
});

document.getElementById("myButton").addEventListener("click", function () {
  alert("Third listener - this will not run");
});
```

**Use Cases:**

- Preventing other listeners on the same element from executing.
- Fine-tuning complex event-driven interactions.
