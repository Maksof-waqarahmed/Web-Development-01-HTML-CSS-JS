# 📘 CSS Tables, Position, Display, and Overflow

## 1. 📊 CSS Tables

HTML tables (`<table>`, `<tr>`, `<td>`, `<th>`) are used to organize tabular data. CSS enhances their readability, layout, and presentation.

### 🔹 Common Table Properties

#### 1. **border**

Defines the line around table elements.

```css
table, th, td {
  border: 1px solid black;
}
```

**Example values:** `1px solid black`, `2px dashed red`, etc.

---

#### 2. **border-collapse**

Specifies whether table borders are separated or merged.

```css
table {
  border-collapse: collapse;
}
```

**Values:**

* `separate` → (default) borders are distinct.
* `collapse` → adjacent borders combine into one.

---

#### 3. **border-spacing**

Defines space between table cells (only works when `border-collapse: separate`).

```css
table {
  border-spacing: 10px 15px;
}
```

**Values:** single value (uniform spacing) or two values (horizontal vertical).

---

#### 4. **table-layout**

Determines how the browser calculates column widths.

```css
table {
  table-layout: fixed;
  width: 100%;
}
```

**Values:**

* `auto` → adjusts based on content.
* `fixed` → based on the first row or table width.

---

#### 5. **empty-cells**

Controls visibility of borders and background in empty cells.

```css
table {
  empty-cells: hide;
}
```

**Values:** `show` (default) | `hide`

---

## 2. 📍 CSS Position

The `position` property controls how an element is placed in the document flow.

### 🔹 Position Values

| Value      | Description                                                          |
| ---------- | -------------------------------------------------------------------- |
| `static`   | Default positioning (normal flow).                                   |
| `relative` | Positioned relative to its original location.                        |
| `absolute` | Positioned relative to its nearest positioned ancestor.              |
| `fixed`    | Positioned relative to the viewport (stays fixed on scroll).         |
| `sticky`   | Acts like relative until a scroll threshold is reached, then sticks. |

**Example:**

```css
.box {
  position: absolute;
  top: 50px;
  left: 20px;
}
```

---

### 🔹 Offset Properties

Used to shift positioned elements:

* `top`, `right`, `bottom`, `left`

---

### 🔹 z-index

Defines the stacking order (which element appears above others).

```css
.modal {
  position: fixed;
  z-index: 999;
}
```

Higher values appear on top.

---

## 3. 📐 CSS Display

The `display` property defines how an element behaves in layout and how it interacts with other elements.

### 🔹 Common Display Values

| Value          | Behavior                                                       |
| -------------- | -------------------------------------------------------------- |
| `block`        | Starts on a new line and takes full width.                     |
| `inline`       | Stays in line with text, only as wide as content.              |
| `inline-block` | Behaves inline but accepts block properties like width/height. |
| `none`         | Completely hides the element (not rendered).                   |
| `flex`         | Enables Flexbox layout for one-dimensional layouts.            |
| `grid`         | Enables Grid layout for two-dimensional layouts.               |

**Example:**

```css
.box1 {
  display: block;
}

.box2 {
  display: inline-block;
  width: 120px;
  height: 50px;
}
```

---

## 4. 📦 CSS Overflow

The `overflow` property determines how content behaves when it exceeds the container’s boundaries.

### 🔹 Main Property: `overflow`

| Value     | Description                                     |
| --------- | ----------------------------------------------- |
| `visible` | Default — content spills outside the container. |
| `hidden`  | Extra content is clipped and hidden.            |
| `scroll`  | Always adds scrollbars (even if not needed).    |
| `auto`    | Adds scrollbars only when necessary.            |

**Example:**

```css
.box {
  width: 200px;
  height: 100px;
  overflow: auto;
}
```

---

### 🔹 Directional Overflow

* `overflow-x` → Controls horizontal overflow.
* `overflow-y` → Controls vertical overflow.

```css
.container {
  overflow-x: scroll;
  overflow-y: hidden;
}
```

---

### 🔹 Text Overflow

Specifically for handling inline text overflow.

```css
p {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

**Values:**

* `clip` → Cuts off the text.
* `ellipsis` → Shows `...` at the end.

---

## 🎯 Conclusion

| Concept      | Key Purpose                                                    |
| ------------ | -------------------------------------------------------------- |
| **Tables**   | Style and control layout with borders, spacing, and alignment. |
| **Position** | Precisely control element placement and stacking.              |
| **Display**  | Define how elements appear and interact in the layout.         |
| **Overflow** | Manage content that exceeds container limits.                  |

> 🧭 **Mastering these properties** builds a strong foundation for responsive, organized, and visually appealing web layouts.

---