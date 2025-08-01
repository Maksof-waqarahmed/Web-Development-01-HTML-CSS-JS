# 📘 HTML (HyperText Markup Language)

## 🟢 Introduction

**HTML (HyperText Markup Language)** is the **standard markup language** used to create the structure of web pages. It tells the browser how to display content like text, images, videos, and links.

* **Inventor**: Tim Berners-Lee
* **Year Introduced**: 1991
* **Purpose**: To define and structure documents on the World Wide Web.
* **Organization**: Standardized by **W3C (World Wide Web Consortium)** and **WHATWG (Web Hypertext Application Technology Working Group)**.

### 🔹 Versions of HTML

1. **HTML 1.0 (1991)** → Very basic, only simple text and links.
2. **HTML 2.0 (1995)** → Standardized, introduced forms and tables.
3. **HTML 3.2 (1997)** → Added scripting support, style elements.
4. **HTML 4.01 (1999)** → Popular version, separated structure from presentation (introduced CSS).
5. **XHTML (2000)** → Stricter syntax version of HTML, based on XML.
6. **HTML5 (2014)** → Current standard, supports multimedia (audio, video), semantic tags (`header`, `footer`, `article`, etc.), canvas, local storage, responsive design.

---

## 🏗️ Basic Structure of an HTML Document

Every HTML document follows this structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First Page</title>
</head>
<body>
  <h1>Hello World</h1>
  <p>This is my first webpage.</p>
</body>
</html>
```

### Breakdown:

* `<!DOCTYPE html>` → Declares the document type (HTML5).
* `<html>` → Root element of the page.
* `<head>` → Contains metadata (title, charset, styles, scripts).
* `<body>` → Contains the visible content of the page.

---

## ✍️ Text-Related Tags

HTML provides tags to display and format text.

### 1. Headings

* **Tags**: `<h1>` to `<h6>`
* **Purpose**: Define headings, `<h1>` is largest, `<h6>` is smallest.
* Example:

  ```html
  <h1>Main Heading</h1>
  <h2>Sub Heading</h2>
  ```

### 2. Paragraph

* **Tag**: `<p>`
* **Purpose**: Defines a block of text.
* Example:

  ```html
  <p>This is a paragraph of text.</p>
  ```

### 3. Line Break

* **Tag**: `<br>`
* **Purpose**: Inserts a single line break.
* Example:

  ```html
  Line one <br> Line two
  ```

### 4. Horizontal Rule

* **Tag**: `<hr>`
* **Purpose**: Creates a horizontal line (divider).
* Example:

  ```html
  <p>Section 1</p>
  <hr>
  <p>Section 2</p>
  ```

### 5. Formatting Tags

* `<b>` → Bold text (without extra meaning).
* `<strong>` → Important text (semantic, accessibility).
* `<i>` → Italic text (without extra meaning).
* `<em>` → Emphasized text (semantic).
* `<u>` → Underlined text.
* `<mark>` → Highlight text.
* `<small>` → Smaller text.
* `<sup>` → Superscript (x²).
* `<sub>` → Subscript (H₂O).
* `<del>` → Deleted text (strikethrough).
* `<ins>` → Inserted text (underlined).

Example:

```html
<p>This is <strong>important</strong> and <em>emphasized</em> text.</p>
<p>Water formula is H<sub>2</sub>O.</p>
```

---

## 📋 Lists in HTML

Lists help organize content. HTML provides three types:

### 1. Ordered List (`<ol>`)

* Purpose: Numbered list.
* Attributes:

  * `type` → Defines numbering style.

    * `1` (default), `A`, `a`, `I`, `i`.
  * `start` → Defines starting number.
  * `reversed` → Reverses numbering order.

Example:

```html
<ol type="A" start="3" reversed>
  <li>First Item</li>
  <li>Second Item</li>
</ol>
```

### 2. Unordered List (`<ul>`)

* Purpose: Bulleted list.
* Attributes:

  * `type` → Defines bullet style (deprecated in HTML5, use CSS instead).

Example:

```html
<ul>
  <li>Apple</li>
  <li>Banana</li>
  <li>Cherry</li>
</ul>
```

### 3. Description List (`<dl>`)

* Purpose: Term/Definition style list.
* Tags:

  * `<dt>` → Definition term.
  * `<dd>` → Definition description.

Example:

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

---

## 🎯 Conclusion

* **HTML** is the backbone of web development.
* It defines structure and meaning (semantics).
* Basic building blocks include **headings, paragraphs, formatting tags, and lists**.
* **HTML5** is the modern version that supports multimedia and responsive design.