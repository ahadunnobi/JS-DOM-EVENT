# HTML DOM (Document Object Model)

The **HTML DOM** is an Object Model and programming interface for HTML documents. When a web page loads, the browser creates a tree-like representation of the document.



## DOM Nodes
Every part of the document is a **Node** in this tree:
* **Document:** The owner of all nodes (the root).
* **Elements:** HTML tags (e.g., `<html>`, `<body>`, `<h1>`, `<a>`).
* **Attributes:** Properties of tags (e.g., `href`, `id`).
* **Text:** The actual text inside an element.

## The DOM API
The DOM API allows JavaScript to interact with HTML elements through the `document` object. 
* **Method (Action):** Something you *do* to an element (e.g., `getElementById()`).
* **Property (Value):** Something you *get or set* on an element (e.g., `innerHTML`).

### What you can do with the API:
* Find and select elements.
* Change element content, attributes, and CSS styles.
* Add, remove, or modify elements.
* Add event listeners to react to user input.

## Selecting HTML Elements
To manipulate HTML, you must first select the element using the `document` object:

| Method | Description |
| :--- | :--- |
| `document.getElementById(id)` | Finds a single element by its unique `id`. |
| `document.getElementsByTagName(name)` | Finds elements by their tag name. |
| `document.getElementsByClassName(name)` | Finds elements by their class name. |
| `document.querySelector(selector)` | Finds the **first** element that matches a CSS selector. |
| `document.querySelectorAll(selector)` | Finds **all** elements that match a CSS selector. |

## Quick Example

```html
<p id="demo"></p>

<script>
  // 1. Method: Find the element using the document object
  const myPara = document.getElementById("demo");

  // 2. Property: Change the content of the element
  myPara.innerHTML = "Hello World!";
</script>
