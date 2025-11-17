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

<img src="./images/w.PNG" alt="Script Placement">

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

The `alert()` function in JavaScript is used to display a **pop-up message box** to the user. It is typically used to provide **information or warnings**.

**Syntax:**

```js
alert(message);
```

**Parameters:**

* `message`: A string (text) to be displayed in the alert box.

**Example:**

```js
alert("Welcome to JavaScript!");
```

---

### 📝 2. `document.write()` & `document.writeln()`

> ⚠️ **Note:** `document.write()` is **deprecated** in HTML5 — it should be avoided in modern websites.

The `document.write()` or `document.writeln()` method writes **text, HTML, or JavaScript code** directly to the **web page**. It is used to **dynamically display content** during the **page loading process**.

**Syntax:**

```js
document.write(content);
document.writeln(content);
```

**Parameters:**

* `content`: A string of text or HTML to be written to the document.

**Example:**

```js
document.write("<h2>Hello, World!</h2>");
document.writeln("<h2>Hello, World!</h2>");
```

⚠️ **Note:** Using `document.write()` or `document.writeln()` after the page has fully loaded can overwrite the entire document.

### 🧠 **Explanation:**

`document.write()` and `document.writeln()` are JavaScript functions used to **write HTML directly into a webpage**.

However, if you use them **after the page has fully loaded** (for example, inside `window.onload` or on a button click),
they will **erase all existing content** on the page and display only the new content written by them.

---

### 🔍 **Example 1 — (Safe use before the page loads):**

```html
<script>
  document.write("<h1>Hello Rana!</h1>");
</script>
```

✅ This code runs while the page is loading, so it’s fine.
The page will render `<h1>Hello Rana!</h1>` properly.

---

### 🚫 **Example 2 — (Problematic use after the page loads):**

```html
<body>
  <h1>Welcome to My Website</h1>
  <button onclick="addText()">Click Me</button>

  <script>
    function addText() {
      document.write("You clicked the button!");
    }
  </script>
</body>
```

🧨 When you click the button:

* The entire page **gets replaced**
* Only `"You clicked the button!"` is displayed
* Everything else (like the heading and button) **disappears**

---

### ✅ **Better Alternative:**

Instead of using `document.write()`, always use **DOM manipulation methods**, such as:

```html
<p id="msg"></p>
<button onclick="addText()">Click Me</button>

<script>
  function addText() {
    document.getElementById("msg").textContent = "You clicked the button!";
  }
</script>
```

👉 This method only updates the text **inside the paragraph**, without removing the rest of the page content.

---

### 🧩 **In short:**

| Situation                                    | Result                       |
| -------------------------------------------- | ---------------------------- |
| Use `document.write()` while page is loading | ✅ OK                         |
| Use `document.write()` after page is loaded  | ⚠️ Overwrites whole document |
| Use DOM methods instead                      | ✅ Safe & modern way          |

---

### 🖥️ 3. `console.log()`

The `console.log()` method is used to print **messages, variables, or any data** to the **browser's console**. It is primarily used for **debugging purposes**.

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

🧠 **Why use it?**
Because it doesn’t interrupt the user experience like alerts — it helps developers quietly check what’s happening in the code.

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

Comments are **non-executable lines** used to **explain your code**.
They make your code readable for others (and for your future self).
JavaScript ignores comments during execution.

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

🧠 **Symbols Used:**
`/*` → Start of comment
`*/` → End of comment
---

### 💡 Why Comments Are Important

| Type                 | Purpose                                      |
| -------------------- | -------------------------------------------- |
| `//` Single-line     | Add short notes beside code                  |
| `/*...*/` Multi-line | Write detailed explanations or documentation |

**Example:**

```js
// Calculate total marks
let total = 85 + 90 + 78;

/*
Display result in console.
If needed, we can apply conditions here later.
*/
console.log("Total Marks:", total);
```

---

## 🧾 Summary

| Concept            | Purpose / Use                                     |
| ------------------ | ------------------------------------------------- |
| `alert()`          | Show popup message to user                        |
| `document.write()` | Write HTML/text to page (avoid after load)        |
| `console.log()`    | Print info for developers in browser console      |
| **Statements**     | Perform specific actions (e.g., print, calculate) |
| **Comments**       | Add notes or explanations in code                 |

---

### 🎯 Final Tip

🔹 Use `alert()` for simple notifications.
🔹 Avoid `document.write()` — use DOM manipulation instead.
🔹 Use `console.log()` to test your code like a pro.
🔹 Always write comments — **good code explains itself!**

---

✨ Now you know how to **show output, write statements, and add comments** in JavaScript!
