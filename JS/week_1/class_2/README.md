# 📌 How to Connect JavaScript Files to HTML & JavaScript Output

---

## 1️⃣ Ways to include JavaScript in HTML

1. **✍️ Inline script inside HTML**

```html
<!-- inline script -->
<script>
  console.log('Hello from inline script');
</script>
```

2. **📂 External script (default)**

```html
<script src="app.js"></script>
```

3. **⚡ Async / ⏳ Defer attributes**

```html
<!-- async example -->
<script async src="analytics.js"></script>

<!-- defer example -->
<script defer src="app.js"></script>
```

---

## 2️⃣ Where to put the `<script>` tag and why

### 🟢 A. At end of `<body>` (classic approach)

```html
<!-- index.html -->
<body>
  <!-- page content -->
  <script src="app.js"></script>
</body>
```

* 🖥️ Browser downloads the HTML, builds DOM, then downloads & executes the script.
* ✅ Simple and works for scripts that need the DOM.
* ⚠️ But it blocks painting while the script loads and executes at that point.

### 🟡 B. In `<head>` without attributes

```html
<head>
  <script src="app.js"></script>
</head>
```

* ⏸️ The browser pauses HTML parsing to download and run the script.
* ❌ This can delay page rendering (bad for performance) if the script is large.

### 🔵 C. In `<head>` with `defer`

```html
<head>
  <script defer src="app.js"></script>
</head>
```

* 📥 Browser downloads script while parsing HTML, but **executes it after the DOM is fully parsed** (before `DOMContentLoaded`).
* 📌 Preserves the order of scripts.
* 👍 Great for application code that needs the DOM.

### 🔴 D. In `<head>` with `async`

```html
<head>
  <script async src="analytics.js"></script>
</head>
```

* ⬇️ Browser downloads the script while parsing HTML and **executes it as soon as it finishes downloading** — order is *not* guaranteed.
* 🎯 Use for independent scripts (analytics, ads), not for scripts that rely on DOM or other scripts.

---

🖼️ **Diagram:**

![Script Placement](../../../images/w.png)

---

## 3️⃣ DOM events: `DOMContentLoaded` vs `load`

* ⚡ `DOMContentLoaded` fires when the HTML is parsed and DOM tree is built (stylesheets/images might still be loading).
* 🖼️ `load` fires when the whole page, including images and sub-resources, has fully loaded.

```html
<script>
  document.addEventListener('DOMContentLoaded', () => {
    console.log('DOM ready — safe to query elements');
  });

  window.addEventListener('load', () => {
    console.log('Page fully loaded — images and other resources ready');
  });
</script>
```

* ✅ If you use `defer`, your scripts run **before** `DOMContentLoaded` fires.

---

## 4️⃣ When to place `<script>` in `<head>` vs. before `</body>`

* 🟦 Use `<head>` + `defer` for predictable, ordered execution and fast DOM availability.
* 🟨 Use `<head>` + `async` for independent scripts (ads, analytics).
* 🟩 Place script before `</body>` only if you cannot use `defer` and your script needs the DOM.

---

## 5️⃣ Performance tips

* ✂️ Minify and compress JS (gzip / brotli).
* 🚀 Use HTTP/2 or HTTP/3 to allow parallel downloads.
* 🔗 Combine critical small inline config and defer large app scripts.
* 🎯 Use `preload` for important resources if needed:

```html
<link rel="preload" href="/js/app.js" as="script">
```
---
---

# 📢 JavaScript Output & Code Basics

---

## 1️⃣ Output Methods

### 🛑 1. `alert()`

The `alert()` function in JavaScript is used to display a pop-up message box to the user. It is typically used to provide information or warnings.

**Syntax:**

```js
alert(message);
```

**Parameters:**

* `message`: A string or value to be displayed in the alert box.

**Example:**

```js
alert("Welcome to JavaScript!");
```

---

### 📝 2. `document.write()`

The `document.write()` method writes text, HTML, or JavaScript code directly to the web page. It is used to dynamically display content during the page loading process.

**Syntax:**

```js
document.write(content);
```

**Parameters:**

* `content`: A string of text or HTML to be written to the document.

**Example:**

```js
document.write("<h2>Hello, World!</h2>");
```

⚠️ **Note:** Using `document.write()` after the page has fully loaded can overwrite the entire document.

---

### 🖥️ 3. `console.log()`

The `console.log()` method is used to print messages, variables, or any data to the browser's console. It is primarily used for debugging purposes.

**Syntax:**

```js
console.log(message);
```

**Parameters:**

* `message`: Any value (string, variable, object, etc.) you want to log to the console.

**Example:**

```js
console.log("Debugging message");
```

---

## 2️⃣ Statements & Comments

### 📌 Statements

In programming, a **statement** is a single line or instruction that performs a specific action.

**Example:**

```js
console.log("Adult");
```

---

### 💬 Comments

Comments are **non-executable lines** of text in a program that provide explanations, descriptions, or notes for developers. They are ignored by the compiler or interpreter and do not affect the program's functionality.

#### ✅ Types of Comments:

1. **Single-line Comments**
   Used for short explanations or notes.

```js
// This is a single line comment
console.log("Hello");
```

🔹 Name: `/` (Forward Slash)

---

2. **Multi-line Comments**
   Used for longer descriptions or notes.

```js
/*
This is a multi-line comment.
It can span multiple lines.
*/
console.log("Hello Again");
```

🔹 Name: `*` (Asterisk) + `/` (Forward Slash)

---

## 3️⃣ Diagram – JavaScript Output Flow

```mermaid
graph TD;
  A[👨‍💻 Developer Writes Code] --> B[alert() - Pop-up Box];
  A --> C[document.write() - Writes to Webpage];
  A --> D[console.log() - Logs in Console];
```

---

✨ Now you know how to **show output, write statements, and add comments** in JavaScript!
