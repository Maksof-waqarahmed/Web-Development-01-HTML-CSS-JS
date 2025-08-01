# 📘 CSS Flexbox, Grid, and Media Queries

## 1. 📐 Display: Flex (Flexbox)

### 🔹 Purpose

Flexbox is a **one-dimensional layout system** that arranges elements in rows or columns, making alignment and spacing easy.

### 🔹 Enable Flexbox

```css
.container {
  display: flex;
}
```

### 🔹 Properties

#### a. **flex-direction**

* Purpose: Defines the direction of flex items.
* Values:

  * `row` → Default, items left to right.
  * `row-reverse` → Items right to left.
  * `column` → Items top to bottom.
  * `column-reverse` → Items bottom to top.

#### b. **justify-content**

* Purpose: Aligns items along the **main axis**.
* Values:

  * `flex-start` → Items at start.
  * `flex-end` → Items at end.
  * `center` → Items centered.
  * `space-between` → Equal space between items.
  * `space-around` → Equal space around items.
  * `space-evenly` → Equal space including edges.

#### c. **align-items**

* Purpose: Aligns items along the **cross axis**.
* Values:

  * `stretch` → Default, items stretch to fill.
  * `flex-start` → Items at cross-axis start.
  * `flex-end` → Items at cross-axis end.
  * `center` → Items centered.
  * `baseline` → Items align by text baseline.

#### d. **align-content**

* Purpose: Controls space between multiple lines.
* Values: same as `justify-content`.

#### e. **flex-wrap**

* Purpose: Controls wrapping of items.
* Values:

  * `nowrap` → Default, all items in one line.
  * `wrap` → Items wrap onto new lines.
  * `wrap-reverse` → Wrap in reverse order.

#### f. **gap / row-gap / column-gap**

* Purpose: Space between items.
* Example:

  ```css
  gap: 20px;
  ```

#### g. **flex (shorthand for items)**

* Purpose: Defines grow, shrink, and basis for items.
* Syntax: `flex: grow shrink basis;`
* Example: `flex: 1 1 200px;`

---

## 2. 📊 Display: Grid (CSS Grid)

### 🔹 Purpose

Grid is a **two-dimensional layout system** for designing rows and columns.

### 🔹 Enable Grid

```css
.container {
  display: grid;
}
```

### 🔹 Properties

#### a. **grid-template-columns / grid-template-rows**

* Purpose: Defines number and size of rows/columns.
* Values:

  * `100px 100px 100px` → Fixed widths.
  * `1fr 2fr` → Fractional units.
  * `repeat(3, 1fr)` → Repeat 3 equal columns.
  * `auto` → Adjusts based on content.

#### b. **gap / row-gap / column-gap**

* Purpose: Spacing between rows and columns.
* Example: `gap: 20px;`

#### c. **grid-template-areas**

* Purpose: Creates named areas for layout.
* Example:

  ```css
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  ```

#### d. **grid-area**

* Purpose: Assigns items to specific named area.

#### e. **justify-items / align-items**

* Purpose: Aligns items inside their cells.
* Values: `start`, `end`, `center`, `stretch`.

#### f. **justify-content / align-content**

* Purpose: Aligns the whole grid inside the container.
* Values: `start`, `end`, `center`, `space-between`, `space-around`, `space-evenly`.

#### g. **place-items (shorthand)**

* Purpose: Combines `justify-items` and `align-items`.

#### h. **place-content (shorthand)**

* Purpose: Combines `justify-content` and `align-content`.

#### i. **grid-auto-rows / grid-auto-columns**

* Purpose: Defines sizes for implicit rows/columns.

#### j. **grid (shorthand)**

* Purpose: Combines template rows, columns, and areas.

---

## 3. 📱 Media Queries

### 🔹 Purpose

Media queries make websites **responsive** by applying CSS based on device conditions like screen width, height, or orientation.

### 🔹 Syntax

```css
@media (condition) {
  /* CSS rules here */
}
```

### 🔹 Common Conditions

#### a. Screen Width

* `@media (max-width: 600px)` → For devices ≤ 600px wide (mobile).
* `@media (min-width: 768px)` → For devices ≥ 768px (tablet).
* `@media (min-width: 1024px)` → For desktops.

#### b. Orientation

* `@media (orientation: portrait)` → For vertical screens.
* `@media (orientation: landscape)` → For horizontal screens.

#### c. Resolution

* `@media (min-resolution: 2dppx)` → For Retina/HD screens.

### 🔹 Example

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

/* Mobile */
@media (max-width: 600px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

---

## 🎯 Conclusion

* **Flexbox**: Best for **1D layouts** (rows/columns).
* **Grid**: Best for **2D layouts** (rows + columns).
* **Media Queries**: Make designs **responsive** across devices.