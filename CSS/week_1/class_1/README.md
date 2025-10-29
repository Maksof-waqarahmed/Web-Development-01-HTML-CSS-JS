# 🎨 **CSS (Cascading Style Sheets)**

## 🟢 **Introduction**

**CSS (Cascading Style Sheets)** is a stylesheet language that controls the **presentation**, **layout**, and **visual design** of web pages written in HTML. It enables developers to separate **content** from **design**, ensuring cleaner code and easier maintenance.

| Property            | Details                                                         |
| ------------------- | --------------------------------------------------------------- |
| **Creator**         | Håkon Wium Lie                                                  |
| **Introduced**      | 1996 (Standardized by W3C)                                      |
| **Purpose**         | To style and layout web content                                 |
| **Full Form**       | Cascading Style Sheets                                          |
| **Cascade Meaning** | Determines which style takes priority when multiple rules apply |

---

## 🧩 **Ways to Apply CSS**

There are **three main methods** to include CSS in an HTML document:

### 1️⃣ **Inline CSS**

* Applied directly to an element using the `style` attribute.
* Best for **one-time** styling.

```html
<h1 style="color: red; font-size: 22px;">Hello CSS!</h1>
```

**Priority:** 🔺 Highest — overrides both internal and external CSS.

---

### 2️⃣ **Internal CSS**

* Written inside a `<style>` tag within the `<head>` section.
* Used to style elements on a **single page**.

```html
<style>
  h1 {
    color: blue;
    font-size: 24px;
  }
</style>
```

**Priority:** ⚙️ Medium — overrides external but not inline styles.

---

### 3️⃣ **External CSS**

* Stored in a separate `.css` file and linked to HTML using `<link>`.
* Ideal for **reusability** across multiple pages.

```html
<link rel="stylesheet" href="style.css">
```

**style.css**

```css
h1 {
  color: green;
  font-size: 28px;
}
```

**Priority:** 🔽 Lowest — but **best practice** for maintainable design.

---

## ⚖️ **CSS Specificity & Priority Rules**

When multiple CSS rules target the same element, the following **order of precedence** applies:

| Priority | Type         | Example                                   |
| -------- | ------------ | ----------------------------------------- |
| 1️⃣      | Inline CSS   | `<h1 style="color:red;">`                 |
| 2️⃣      | Internal CSS | Inside `<style>` tag                      |
| 3️⃣      | External CSS | In linked `.css` file                     |
| 🔒       | `!important` | `color: blue !important;` → overrides all |

---

## 🧱 **CSS Syntax**

Every CSS rule consists of:

```css
selector {
  property: value;
}
```

| Component    | Description             | Example              |
| ------------ | ----------------------- | -------------------- |
| **Selector** | Targets HTML elements   | `p`, `.class`, `#id` |
| **Property** | Defines what to style   | `color`, `font-size` |
| **Value**    | Defines how to style it | `red`, `16px`        |

**Example:**

```css
p {
  color: blue;
  font-size: 18px;
}
```

---

## 🎯 **Types of CSS Selectors**

| Selector Type  | Symbol     | Description                   | Example                                |
| -------------- | ---------- | ----------------------------- | -------------------------------------- |
| Universal      | `*`        | Targets all elements          | `* { margin: 0; }`                     |
| Element        | `tag`      | Targets by tag name           | `h1 { color: red; }`                   |
| Class          | `.class`   | Targets elements with a class | `.highlight { background: yellow; }`   |
| ID             | `#id`      | Targets a unique element      | `#main { font-size: 20px; }`           |
| Group          | `,`        | Targets multiple selectors    | `h1, p { font-family: Arial; }`        |
| Descendant     | (space)    | Targets nested elements       | `div p { color: green; }`              |
| Child          | `>`        | Targets direct children only  | `div > p { color: blue; }`             |
| Pseudo-class   | `:hover`   | Targets element states        | `a:hover { color: orange; }`           |
| Pseudo-element | `::before` | Targets part of element       | `p::first-letter { font-size: 30px; }` |

---

## ✍️ **Text-Related CSS Properties**

| Property             | Description                    | Example                                   |
| -------------------- | ------------------------------ | ----------------------------------------- |
| **color**            | Sets the text color            | `color: #ff0000;`, `color: rgb(255,0,0);` |
| **font-family**      | Defines font type              | `font-family: "Arial", sans-serif;`       |
| **font-size**        | Controls text size             | `font-size: 18px;`                        |
| **font-weight**      | Adjusts boldness               | `font-weight: 700;`                       |
| **font-style**       | Italic or normal text          | `font-style: italic;`                     |
| **font (shorthand)** | Sets all font properties       | `font: italic bold 16px Arial;`           |
| **text-align**       | Aligns text horizontally       | `text-align: center;`                     |
| **text-decoration**  | Adds underline, overline, etc. | `text-decoration: underline dotted red;`  |
| **text-transform**   | Changes letter case            | `text-transform: uppercase;`              |
| **letter-spacing**   | Controls character spacing     | `letter-spacing: 2px;`                    |
| **word-spacing**     | Controls space between words   | `word-spacing: 5px;`                      |
| **line-height**      | Adjusts line spacing           | `line-height: 1.5;`                       |
| **text-shadow**      | Adds shadow to text            | `text-shadow: 2px 2px 5px gray;`          |
| **direction**        | Text direction (LTR/RTL)       | `direction: rtl;`                         |
| **text-overflow**    | Handles overflowing text       | `text-overflow: ellipsis;`                |

---

## 🧠 **Example — Text Styling**

```css
p {
  color: #333;
  font-family: "Poppins", sans-serif;
  font-size: 18px;
  line-height: 1.6;
  text-align: justify;
  text-transform: capitalize;
  letter-spacing: 0.5px;
  text-shadow: 1px 1px 3px lightgray;
}
```

---

## 💎 **Color Formats in CSS**

| Format | Example                | Description                |
| ------ | ---------------------- | -------------------------- |
| Named  | `red`                  | Simple color name          |
| HEX    | `#ff0000`              | Hexadecimal format         |
| RGB    | `rgb(255,0,0)`         | Red, Green, Blue values    |
| RGBA   | `rgba(255,0,0,0.5)`    | RGB + Alpha (transparency) |
| HSL    | `hsl(0,100%,50%)`      | Hue, Saturation, Lightness |
| HSLA   | `hsla(0,100%,50%,0.5)` | HSL + Alpha transparency   |

---

## 🎯 **Conclusion**

✅ CSS transforms plain HTML into **visually appealing, structured, and responsive** designs.
✅ Use **External CSS** for professional projects.
✅ Follow **specificity rules** to manage style conflicts.
✅ Leverage **text-related properties** for better typography.
✅ Combine CSS with responsive design (media queries) for a modern web experience.

---