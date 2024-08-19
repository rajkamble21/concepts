# Mastering DOM

Mastering DOM

## What is DOM

DOM, or Document Object Model, is a programming interface that represents structured documents like HTML and XML as a tree of objects. It defines how to access, manipulate, and modify document elements using scripting languages like JavaScript.

So basically Document Object Model is an API that represents and interacts with HTML or XML documents.

The DOM is a W3C (World Wide Web Consortium) standard and it defines a standard for accessing documents.

The W3C Dom standard is divided into three different parts:

- Core DOM : standard model for all document types
- XML DOM : standard model for XML documents
- HTML DOM : standard model for HTML documents

## What is the HTML DOM?

The HTML DOM is a standard object model and programming interface for HTML. It defines:

- The HTML elements as objects
- The properties of all HTML elements
- The methods to access all HTML elements
- The events for all HTML elements
- In other words: The HTML DOM is a standard for how to get, change, add, or delete HTML elements.

## Fundamental data types

following table provides a concise overview of the fundamental data types and interfaces used in the DOM.

| **Data Type (Interface)** | **Description**                                                                                                                                                                                       |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Document**              | The root document object. For example, `ownerDocument` returns the document to which an element belongs. It represents the entire HTML or XML document.                                               |
| **Node**                  | Every object within a document is a node (e.g., element node, text node, attribute node). Nodes form the tree structure of the DOM.                                                                   |
| **Element**               | An element is a specific type of node. Methods like `document.createElement()` return an element. Elements implement both the DOM `Element` interface and the basic `Node` interface.                 |
| **NodeList**              | An array-like collection of nodes, such as those returned by `document.querySelectorAll()`. Items in a NodeList can be accessed by index using either `list.item(1)` or `list[1]`.                    |
| **Attr**                  | Attributes are nodes in the DOM, returned by methods like `createAttribute()`. They have a special interface but are less commonly manipulated as nodes.                                              |
| **NamedNodeMap**          | A collection of nodes that can be accessed by name or index. Items are unordered, and the collection has methods like `item()` for retrieval. Items can also be added or removed from a NamedNodeMap. |

## Methods of Document Object

DOM provides various methods that allows users to interact with and manipulate the document. Some commonly used DOM methods are:

Here's the information about the methods of the `Document` object, summarized in a table format:

| **Method**                   | **Description**                                                 |
| ---------------------------- | --------------------------------------------------------------- |
| **write("string")**          | Writes the given string directly into the document.             |
| **getElementById()**         | Returns the element with the specified ID value.                |
| **getElementsByName()**      | Returns a collection of elements with the specified name value. |
| **getElementsByTagName()**   | Returns a collection of elements with the specified tag name.   |
| **getElementsByClassName()** | Returns a collection of elements with the specified class name. |

### Example: Using `getElementById()` Method

Here’s a simple example demonstrating the use of the `getElementById()` method:

```html
<div id="content">Hello, World!</div>

<script>
  const element = document.getElementById("content");
  element.textContent = "DOM is powerful!";
</script>
```

In this example, the `getElementById()` method is used to select the `div` element with the ID of `content`, and the `textContent` property is used to change its content.

## DOM Events

Events in the DOM are actions that occur in the web browser, such as clicks, keypresses, or form submissions. The DOM allows us to listen to these events and respond accordingly.

### Event Flow

Event flow describes how events are propagated through the DOM. There are two phases:

1. **Capturing Phase**: The event starts from the document root and flows down to the target element.
2. **Bubbling Phase**: After reaching the target element, the event bubbles up to the document root.

### Example: Handling Click Events

Here’s an example of how to handle a click event on a button:

```html
<button id="myButton">Click Me</button>

<script>
  const button = document.getElementById("myButton");
  button.addEventListener("click", function () {
    alert("Button was clicked!");
  });
</script>
```

In this example, the `addEventListener` method is used to attach a click event to the button. When the button is clicked, an alert message is displayed.

## DOM Traversal and Manipulation

DOM traversal refers to navigating through the DOM tree, while manipulation refers to modifying the structure of the DOM.

### Traversal Methods

- `parentNode`: Returns the parent node of the specified node.
- `childNodes`: Returns a live NodeList of all child nodes of the specified node.
- `firstChild`: Returns the first child node of the specified node.
- `lastChild`: Returns the last child node of the specified node.
- `nextSibling`: Returns the node immediately following the specified node.
- `previousSibling`: Returns the node immediately before the specified node.

### Example: Creating and Appending Elements

```html
<ul id="myList">
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

<script>
  const list = document.getElementById("myList");
  const newItem = document.createElement("li");
  newItem.textContent = "Item 3";
  list.appendChild(newItem);
</script>
```

In this example, the `createElement()` method is used to create a new `li` element, which is then appended to the list using `appendChild()`.

## Working with Forms and Input Elements

Form elements are commonly accessed and manipulated through the DOM to validate user input, gather data, or provide feedback.

### Example: Simple Form Validation

```html
<form id="myForm">
  <input type="text" id="name" placeholder="Enter your name" />
  <input type="submit" value="Submit" />
</form>

<script>
  const form = document.getElementById("myForm");
  form.addEventListener("submit", function (event) {
    const name = document.getElementById("name").value;
    if (name === "") {
      alert("Name is required!");
      event.preventDefault();
    }
  });
</script>
```

In this example, the form submission is intercepted, and if the `name` input is empty, an alert is displayed, and the form submission is prevented.

## Conclusion

The DOM is a powerful API that underpins the interaction between web pages and scripts. By understanding and mastering DOM manipulation, event handling, and efficient coding practices, developers can create dynamic, responsive, and performant web applications.

## Reference

- https://www.w3schools.com/js/js_htmldom_methods.asp
- https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction#fundamental_data_types
- https://www.geeksforgeeks.org/dom-document-object-model/
