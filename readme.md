# HTML DOM & JavaScript – Compact Notes

## 🌳 HTML DOM (Document Object Model)

The **HTML DOM** is a tree-like structure created by the browser when a page loads.
It represents the document so JavaScript can interact with it.

### 🔹 DOM Nodes

Every part of the page is a **node**:

* **Document** → Root node (owner of all nodes)
* **Elements** → HTML tags (`<body>`, `<p>`, `<a>`)
* **Attributes** → Tag properties (`id`, `href`, `class`)
* **Text** → Content inside elements

---

## 🔹 DOM API (Using `document`)

JavaScript interacts with the DOM through the `document` object.

### ✔ Method vs Property

* **Method** → action
  `document.getElementById()`
* **Property** → value
  `element.innerHTML`

### ✔ What You Can Do

* Select elements
* Change content & attributes
* Modify CSS styles
* Add/remove elements
* Handle user events

---

## 📌 Selecting HTML Elements

| Method                     | Use                        |
| -------------------------- | -------------------------- |
| `getElementById()`         | One element by ID          |
| `getElementsByClassName()` | Elements by class          |
| `getElementsByTagName()`   | Elements by tag            |
| `querySelector()`          | First match (CSS selector) |
| `querySelectorAll()`       | All matches                |

---

## 📌 Quick Example

```html
<p id="demo"></p>

<script>
const myPara = document.getElementById("demo");
myPara.innerHTML = "Hello World!";
</script>
```

---

# 🔎 Finding HTML Elements (Detailed)

### By ID

```js
const el = document.getElementById("intro");
```

### By Tag

```js
const els = document.getElementsByTagName("p");
```

### By Class

```js
const els = document.getElementsByClassName("intro");
```

### By CSS Selector

```js
const el = document.querySelector(".demo");      // first
const els = document.querySelectorAll("p.intro"); // all
```

---

# ✏️ Manipulating Elements

## Change Content

```js
document.getElementById("p1").innerHTML = "New text!";
```

## Change Attribute

```js
document.getElementById("myImage").src = "image.jpg";
```

## Dynamic Content

```js
document.getElementById("demo").innerHTML = "Date: " + Date();
```

---

# ➕ Adding & Removing Nodes

## Create & Append

```js
const newP = document.createElement("p");
newP.innerHTML = "New paragraph";
document.body.appendChild(newP);
```

## Insert Before

```js
parent.insertBefore(newNode, existingNode);
```

## Remove Element

```js
element.remove();
```

---

# ⚠️ document.write()

```js
document.write("Hello");
```

❌ Avoid after page loads — it overwrites the document.

---

# ⚠️ Common Mistakes

* Using `#` in `getElementById()`
* Accessing elements before DOM loads
* Forgetting quotes around IDs
* Expecting `querySelector()` to return multiple elements

---

# ✅ Quick Reference

| Task             | Method                     |
| ---------------- | -------------------------- |
| Find by ID       | `getElementById()`         |
| Find by class    | `getElementsByClassName()` |
| Find by tag      | `getElementsByTagName()`   |
| CSS selector     | `querySelector()`          |
| Change content   | `innerHTML`                |
| Change attribute | `.attribute = value`       |
| Create element   | `createElement()`          |
| Remove element   | `.remove()`                |

---

## 🧠 Rule of Thumb

* Use **ID** → single element
* Use **querySelector** → flexible selection
* Use **innerHTML** → change content
* Avoid **document.write()**

---
