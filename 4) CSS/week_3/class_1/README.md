# 📘 CSS Flexbox and Media Queries

## 🧭 Introduction

**Flexbox (Flexible Box Layout)** is a powerful **one-dimensional layout model** introduced in CSS3.
It allows developers to design flexible and responsive layouts easily — aligning and distributing space among items in a container, **either in a row or a column**.

Before Flexbox, creating vertically centered or evenly spaced elements required complex CSS tricks.
Flexbox simplifies that process by providing intuitive alignment and spacing properties.

---

## 🏗️ Enabling Flexbox

To start using Flexbox, apply `display: flex;` to the **parent container**.
All direct children of that container automatically become **flex items**.

```css
.container {
  display: flex;
}
```

---

## ⚙️ Main Concepts

### 🔹 Flex Container

The parent element where `display: flex` or `display: inline-flex` is applied.

### 🔹 Flex Items

The **direct child elements** inside the flex container that are arranged and aligned by Flexbox rules.

---

## 🎛️ Container Properties

These properties are applied **to the flex container**.

### 1. **display**

| Value         | Description                             |
| ------------- | --------------------------------------- |
| `flex`        | Creates a block-level flex container.   |
| `inline-flex` | Creates an inline-level flex container. |

---

### 2. **flex-direction**

Defines the **direction of the main axis** (how items are placed inside the container).

| Value            | Description                           |
| ---------------- | ------------------------------------- |
| `row`            | (Default) Items placed left to right. |
| `row-reverse`    | Items placed right to left.           |
| `column`         | Items placed top to bottom.           |
| `column-reverse` | Items placed bottom to top.           |

```css
.container {
  flex-direction: row;
}
```

---

### 3. **flex-wrap**

Controls whether flex items stay in one line or wrap onto multiple lines.

| Value          | Description                             |
| -------------- | --------------------------------------- |
| `nowrap`       | (Default) All items stay in one line.   |
| `wrap`         | Items wrap to next line when necessary. |
| `wrap-reverse` | Items wrap in reverse order.            |

```css
.container {
  flex-wrap: wrap;
}
```

---

### 4. **flex-flow (shorthand)**

Combines `flex-direction` and `flex-wrap` in one line.

```css
.container {
  flex-flow: row wrap;
}
```

---

### 5. **justify-content**

Aligns items along the **main axis** (horizontal in `row`, vertical in `column`).

| Value           | Description                            |
| --------------- | -------------------------------------- |
| `flex-start`    | Items packed at start.                 |
| `flex-end`      | Items packed at end.                   |
| `center`        | Items centered.                        |
| `space-between` | Equal space between items.             |
| `space-around`  | Equal space around items.              |
| `space-evenly`  | Equal space between and outside items. |

```css
.container {
  justify-content: space-between;
}
```

---

### 6. **align-items**

Aligns items along the **cross axis** (perpendicular to main axis).

| Value        | Description                                    |
| ------------ | ---------------------------------------------- |
| `stretch`    | (Default) Items stretch to fill the container. |
| `flex-start` | Align items to the top (in a row).             |
| `flex-end`   | Align items to the bottom (in a row).          |
| `center`     | Vertically center items.                       |
| `baseline`   | Align by the text baseline.                    |

```css
.container {
  align-items: center;
}
```

---

### 7. **align-content**

Controls spacing between **multiple lines** (only applies when items wrap).

| Value           | Description                            |
| --------------- | -------------------------------------- |
| `flex-start`    | Lines packed at start.                 |
| `flex-end`      | Lines packed at end.                   |
| `center`        | Lines centered.                        |
| `space-between` | Even space between lines.              |
| `space-around`  | Even space around lines.               |
| `stretch`       | (Default) Lines stretch to fill space. |

```css
.container {
  align-content: space-around;
}
```

---

### 8. **gap / row-gap / column-gap**

Defines spacing between flex items.

```css
.container {
  display: flex;
  gap: 20px; /* space between items */
}
```

---

### 9. **place-content (shorthand)**

Combines `align-content` and `justify-content`.

```css
.container {
  place-content: center space-between;
}
```

---

## 🎯 Item Properties

These properties are applied **to the flex items (children)**.

---

### 1. **order**

Defines the display order of flex items (default is 0).
Items with smaller values appear first.

```css
.item1 {
  order: 2;
}
.item2 {
  order: 1;
}
```

---

### 2. **flex-grow**

Defines how much a flex item can **grow** relative to the others.

| Value | Description                            |
| ----- | -------------------------------------- |
| `0`   | (Default) Item will not grow.          |
| `1`   | Item can grow to fill remaining space. |

```css
.item {
  flex-grow: 1;
}
```

---

### 3. **flex-shrink**

Defines how much a flex item can **shrink** when space is limited.

| Value | Description                |
| ----- | -------------------------- |
| `1`   | (Default) Item can shrink. |
| `0`   | Item will not shrink.      |

```css
.item {
  flex-shrink: 0;
}
```

---

### 4. **flex-basis**

Defines the **initial size** of the flex item before space distribution.

| Example | Description                              |
| ------- | ---------------------------------------- |
| `200px` | Item starts with a width of 200px.       |
| `auto`  | Size based on content or width property. |

```css
.item {
  flex-basis: 150px;
}
```

---

### 5. **flex (shorthand)**

Combines `flex-grow`, `flex-shrink`, and `flex-basis`.

```css
.item {
  flex: 1 1 200px;
}
```

> 💡 **Tip:** The shorthand `flex: 1;` is equal to `flex: 1 1 0;`

---

### 6. **align-self**

Overrides the container’s `align-items` for a specific item.

| Value        | Description                 |
| ------------ | --------------------------- |
| `auto`       | Uses the container’s value. |
| `flex-start` | Align to start.             |
| `flex-end`   | Align to end.               |
| `center`     | Align to center.            |
| `stretch`    | Fill the container.         |
| `baseline`   | Align with text baseline.   |

```css
.item3 {
  align-self: flex-end;
}
```

---

## 🧩 Complete Flexbox Example

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
  background: #f5f5f5;
  padding: 20px;
}

.item {
  flex: 1 1 200px;
  background: #007bff;
  color: white;
  text-align: center;
  padding: 20px;
  border-radius: 8px;
}
```

---

## 📱 Flexbox and Responsiveness

Flexbox automatically adapts to screen sizes, making it ideal for **responsive web design**.

Example:

```css
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.item {
  flex: 1 1 250px;
}
```

When the screen width shrinks, items automatically wrap to the next line — maintaining a fluid layout without breaking the design.

---

## 🏁 Conclusion

Flexbox provides a **powerful, modern, and efficient** way to design web layouts.

✅ Simplifies alignment and spacing.
✅ Handles both horizontal and vertical centering.
✅ Makes layouts responsive without complex floats or positioning.
✅ Perfect for navigation bars, cards, footers, and UI components.

---

# 📘 CSS Media Queries

## 1. 🌐 Introduction

### 🔹 What Are Media Queries?

Media Queries are a **CSS feature** that allows developers to apply styles conditionally — based on the **device’s characteristics**, such as screen size, width, height, resolution, or orientation.

They are a core part of **responsive web design**, helping websites adapt seamlessly across **mobiles, tablets, and desktops**.

---

## 2. 🎯 Why Use Media Queries?

Modern users access websites from various devices.
Without media queries, your site might look **perfect on desktop** but **break on mobile**.

✅ Media Queries help you:

* Improve **user experience** across devices.
* Maintain **readability** and **accessibility**.
* Avoid horizontal scrolling or distorted layouts.
* Create **device-specific designs** within one stylesheet.

---

## 3. ⚙️ Syntax of Media Queries

```css
@media (condition) {
  /* CSS rules here */
}
```

You can use **logical operators** like `and`, `or`, and `not` to combine multiple conditions.

Example:

```css
@media (min-width: 768px) and (max-width: 1200px) {
  body {
    background-color: lightblue;
  }
}
```

---

## 4. 💡 Common Breakpoints (Recommended)

| Device              | Breakpoint Range    | Example Usage                |
| ------------------- | ------------------- | ---------------------------- |
| Extra Small Devices | `max-width: 480px`  | Small mobile phones          |
| Small Devices       | `max-width: 768px`  | Large phones / small tablets |
| Medium Devices      | `max-width: 992px`  | Tablets / small laptops      |
| Large Devices       | `max-width: 1200px` | Desktops                     |
| Extra Large         | `min-width: 1201px` | Big monitors or TVs          |

---

## 5. 📱 Practical Use Cases

1. **Change navigation layout** for mobile (hamburger menu).
2. **Adjust font size** for readability on small screens.
3. **Hide or show elements** based on screen width.
4. **Switch grid or flex layout** on different devices.
5. **Adjust images or videos** to fit smaller screens.

---

## 6. ⚡ Tips for Effective Responsive Design

✅ Always start with **mobile-first design**:
Begin with smaller screens and scale up.

✅ Use **relative units** (`em`, `rem`, `%`) instead of fixed (`px`).

✅ Always include this meta tag in HTML:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

✅ Test your design on **multiple devices** and browser dev tools.

---

## Conclusion

Media Queries are the **backbone of responsive web design**.
They allow one website to adapt dynamically to any screen size, ensuring **usability, readability, and visual balance** on all devices.
