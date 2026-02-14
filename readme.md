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
# DOM Styling, Validation & Animation (Compact)

## 🎨 Changing CSS with JavaScript

Use the `style` property to modify inline styles.

```js
document.getElementById(id).style.property = value;
```

### Common Properties

* `color`
* `backgroundColor`
* `fontSize`
* `visibility`
* `display`
* `position`, `top`, `left`

### Example

```js
element.style.color = "blue";
element.style.visibility = "hidden";
```

---

## ⚡ Style Changes with Events

Execute style changes when events occur.

```js
button.onclick = () => element.style.color = "red";
```

Common events:

* `click`
* `input`
* `submit`
* `load`

---

## 👁️ Show / Hide Elements

```js
element.style.visibility = "hidden"; // hide
element.style.visibility = "visible"; // show

element.style.display = "none"; // remove space
element.style.display = "block";
```

---

## 📝 JavaScript Form Validation

Prevent form submission if input is invalid.

```js
function validateForm() {
  let name = document.forms["myForm"]["fname"].value;
  if (name === "") {
    alert("Name required");
    return false;
  }
}
```

### Numeric Validation

```js
let num = document.getElementById("num").value;
if (isNaN(num) || num < 1 || num > 10) {
  alert("Enter number 1–10");
}
```

---

## ✅ HTML5 Constraint Validation

### Attributes

* `required`
* `min`, `max`
* `pattern`
* `type`

### CSS Pseudo-classes

* `:valid`
* `:invalid`
* `:required`
* `:optional`

---

## 🎞️ DOM Animation (JavaScript)

Animation = gradual style change using `setInterval`.

```js
let id = setInterval(frame, 5);

function frame() {
  if (pos == 350) clearInterval(id);
  else {
    pos++;
    elem.style.left = pos + "px";
    elem.style.top = pos + "px";
  }
}
```

### Requirements

* Container → `position: relative`
* Animated element → `position: absolute`

---

## 🧠 Quick Tips

* Use `visibility` to hide but keep space.
* Use `display: none` to remove layout space.
* Always `clearInterval()` to stop animation.
* Combine HTML5 validation + JS for best results.

---
# HTML DOM Reference (Document & Element)

## 📘 Document Object — Key Properties & Methods

### 🔹 Core Accessors

| Name              | Description                  |
| ----------------- | ---------------------------- |
| `activeElement`   | Currently focused element    |
| `body`            | Returns `<body>` element     |
| `head`            | Returns `<head>` element     |
| `documentElement` | Returns `<html>` root        |
| `title`           | Get/set document title       |
| `URL`             | Full page URL                |
| `domain`          | Domain name                  |
| `referrer`        | URL that linked to this page |
| `lastModified`    | Last modified date           |
| `readyState`      | Loading state                |

---

### 🔹 Element Collections

| Name      | Returns                        |
| --------- | ------------------------------ |
| `forms`   | All `<form>` elements          |
| `images`  | All `<img>` elements           |
| `links`   | All `<a>` & `<area>` with href |
| `scripts` | All `<script>` elements        |
| `embeds`  | All `<embed>` elements         |

---

### 🔹 Node Creation

| Method                     | Purpose             |
| -------------------------- | ------------------- |
| `createElement()`          | Create element node |
| `createTextNode()`         | Create text node    |
| `createComment()`          | Create comment      |
| `createAttribute()`        | Create attribute    |
| `createDocumentFragment()` | Create fragment     |

---

### 🔹 DOM Search Methods

| Method                     | Description     |
| -------------------------- | --------------- |
| `getElementById()`         | Find by ID      |
| `getElementsByClassName()` | Find by class   |
| `getElementsByTagName()`   | Find by tag     |
| `getElementsByName()`      | Find by name    |
| `querySelector()`          | First CSS match |
| `querySelectorAll()`       | All CSS matches |

---

### 🔹 Document Events

| Method                  | Purpose      |
| ----------------------- | ------------ |
| `addEventListener()`    | Attach event |
| `removeEventListener()` | Remove event |
| `hasFocus()`            | Check focus  |

---

### 🔹 Output Stream

| Method      | Description        |
| ----------- | ------------------ |
| `open()`    | Open output stream |
| `close()`   | Close stream       |
| `write()`   | Write HTML         |
| `writeln()` | Write with newline |

---

## 📗 Element Object — Key Properties & Methods

### 🔹 Element Navigation

| Property                 | Description          |
| ------------------------ | -------------------- |
| `parentElement`          | Parent element       |
| `children`               | Child elements       |
| `childNodes`             | All child nodes      |
| `firstElementChild`      | First child element  |
| `lastElementChild`       | Last child element   |
| `nextElementSibling`     | Next sibling element |
| `previousElementSibling` | Previous sibling     |

---

### 🔹 Content & Attributes

| Property/Method     | Description       |
| ------------------- | ----------------- |
| `innerHTML`         | HTML content      |
| `textContent`       | Text content      |
| `innerText`         | Visible text      |
| `outerHTML`         | Element + content |
| `getAttribute()`    | Get attribute     |
| `setAttribute()`    | Set attribute     |
| `removeAttribute()` | Remove attribute  |
| `attributes`        | Attribute list    |

---

### 🔹 Class & Styling

| Property    | Description      |
| ----------- | ---------------- |
| `className` | Class string     |
| `classList` | Class operations |
| `style`     | Inline styles    |

---

### 🔹 DOM Modification

| Method                 | Purpose             |
| ---------------------- | ------------------- |
| `append()`             | Add nodes           |
| `appendChild()`        | Add child node      |
| `before()` / `after()` | Insert relative     |
| `insertBefore()`       | Insert before child |
| `replaceChild()`       | Replace child       |
| `remove()`             | Remove element      |
| `removeChild()`        | Remove child        |
| `cloneNode()`          | Clone element       |

---

### 🔹 Element Position & Size

| Property                  | Description        |
| ------------------------- | ------------------ |
| `clientWidth/Height`      | Size incl. padding |
| `offsetWidth/Height`      | Size incl. border  |
| `offsetTop/Left`          | Position offset    |
| `getBoundingClientRect()` | Size & position    |

---

### 🔹 Scrolling

| Property           | Description       |
| ------------------ | ----------------- |
| `scrollTop`        | Vertical scroll   |
| `scrollLeft`       | Horizontal scroll |
| `scrollHeight`     | Full height       |
| `scrollWidth`      | Full width        |
| `scrollIntoView()` | Scroll to element |

---

### 🔹 Events & Interaction

| Method                  | Purpose        |
| ----------------------- | -------------- |
| `addEventListener()`    | Attach handler |
| `removeEventListener()` | Remove handler |
| `click()`               | Simulate click |
| `focus()`               | Focus element  |
| `blur()`                | Remove focus   |

---

### 🔹 Node Information

| Property        | Description   |
| --------------- | ------------- |
| `nodeName`      | Node name     |
| `nodeType`      | Node type     |
| `nodeValue`     | Node value    |
| `ownerDocument` | Root document |

---

## ⚠️ Deprecated (Avoid Using)

* `anchors`, `applets`, `documentMode`
* `execCommand()`
* `normalizeDocument()`
* `isSupported()`

---

## 🧠 Usage Note

Use this section as a **quick reference** when working with:

* DOM traversal
* Element creation
* Attribute management
* Layout measurements
* Event handling

---
