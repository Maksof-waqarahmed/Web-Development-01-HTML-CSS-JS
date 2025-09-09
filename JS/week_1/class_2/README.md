# 📌 How to Connect JavaScript Files to HTML

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
