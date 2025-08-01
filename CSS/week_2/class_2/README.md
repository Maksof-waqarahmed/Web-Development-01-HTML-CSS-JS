# 📘 CSS Tables, Position, Display, and Overflow

## 1. 📊 CSS Tables

HTML tables (`<table>`, `<tr>`, `<td>`, `<th>`) can be styled with CSS to improve readability and design.

### 🔹 Common Properties

#### 1. **border**

* Purpose: Controls table and cell borders.
* Values: `1px solid black`, `2px dashed red`, etc.
* Example:

  ```css
  table, th, td {
    border: 1px solid black;
  }
  ```

#### 2. **border-collapse**

* Purpose: Defines whether table borders are separated or collapsed.
* Values:

  * `separate` → Default, borders are separated.
  * `collapse` → Adjacent borders merge into a single border.

#### 3. **border-spacing**

* Purpose: Sets spacing between table cells (works only with `border-collapse: separate`).
* Values: `10px`, `5px 15px` (horizontal, vertical).

#### 4. **table-layout**

* Purpose: Defines how table columns are sized.
* Values:

  * `auto` → Default, width adjusts to content.
  * `fixed` → Width fixed by table width and first row cells.

#### 5. **caption-side**

* Purpose: Sets the position of a table caption.
* Values:

  * `top` → Default, above the table.
  * `bottom` → Below the table.

#### 6. **empty-cells**

* Purpose: Defines if borders and background should show for empty cells.
* Values: `show` (default), `hide`.

#### 7. **vertical-align** (for cells)

* Purpose: Aligns content vertically inside `<td>`/`<th>`.
* Values: `top`, `middle`, `bottom`, `baseline`.

---

## 2. 📍 CSS Position

The `position` property defines how elements are placed in a page.

### 🔹 position

* **Values**:

  * `static` → Default, element in normal flow.
  * `relative` → Positioned relative to its normal position (can use `top`, `left`, etc.).
  * `absolute` → Positioned relative to nearest positioned ancestor (removed from normal flow).
  * `fixed` → Positioned relative to the viewport (stays on screen while scrolling).
  * `sticky` → Acts like relative until a scroll point, then sticks.

### 🔹 offset properties

* Used with `position`:

  * `top`, `right`, `bottom`, `left`.
* Example:

  ```css
  .box {
    position: absolute;
    top: 50px;
    left: 20px;
  }
  ```

### 🔹 z-index

* Purpose: Controls stacking order of elements (which appears in front).
* Values:

  * `auto` → Default.
  * Numbers: `1`, `10`, `999` → Higher = closer to front.

---

## 3. 📐 CSS Display

The `display` property defines how an element is displayed in the layout.

### 🔹 Common Values

* `block` → Takes full width, starts on new line (`div`, `p`).
* `inline` → Only takes as much width as needed (`span`, `a`).
* `inline-block` → Behaves like inline but allows block properties (margin, width, height).
* `none` → Hides the element completely.
* `flex` → Enables Flexbox layout.
* `grid` → Enables CSS Grid layout.
* `inline-flex` → Flexbox but inline level.
* `inline-grid` → Grid but inline level.
* `list-item` → Behaves like `<li>`.
* `table` → Behaves like `<table>`.
* `contents` → Makes the element disappear but keeps its children.

### 🔹 Example

```css
.box1 {
  display: block;
}
.box2 {
  display: inline-block;
  width: 100px;
  height: 50px;
}
```

---

## 4. 📦 CSS Overflow

The `overflow` property controls what happens when content is too large for its container.

### 🔹 overflow

* **Values**:

  * `visible` → Default, content spills out.
  * `hidden` → Extra content is clipped (not visible).
  * `scroll` → Adds scrollbars (always, even if not needed).
  * `auto` → Adds scrollbars only when needed.

### 🔹 overflow-x / overflow-y

* Purpose: Control horizontal (`x`) or vertical (`y`) overflow separately.
* Values: `visible`, `hidden`, `scroll`, `auto`.

### 🔹 text-overflow (for inline text)

* Purpose: Handles overflowing inline text.
* Values:

  * `clip` → Cuts off text.
  * `ellipsis` → Shows `...` for overflow.

### 🔹 white-space (related)

* Purpose: Controls text wrapping.
* Values: `normal`, `nowrap`, `pre`, `pre-line`, `pre-wrap`.

### 🔹 Example

```css
.box {
  width: 200px;
  height: 100px;
  overflow: auto;
}
```

---

## 🎯 Conclusion

* **Tables**: Use CSS to style borders, spacing, layout, and captions.
* **Position**: Controls element placement (`static`, `relative`, `absolute`, `fixed`, `sticky`).
* **Display**: Defines how elements behave in layout (`block`, `inline`, `flex`, `grid`).
* **Overflow**: Manages content that doesn’t fit into its box (`hidden`, `scroll`, `auto`).