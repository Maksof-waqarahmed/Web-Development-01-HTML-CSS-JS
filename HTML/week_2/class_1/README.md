# 📘 HTML Tables

## 🟢 Introduction

Tables in HTML are used to display **tabular data** (rows and columns).
A table is made up of rows (`<tr>`), and each row contains cells (`<td>` or `<th>`).

> ⚠️ **Note**: Tables should not be used for page layout (use CSS instead). They are mainly for **structured data** like marksheets, price charts, schedules, etc.

---

## 🏗️ Basic Structure of a Table

```html
<table border="1">
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>City</th>
  </tr>
  <tr>
    <td>Ali</td>
    <td>20</td>
    <td>Karachi</td>
  </tr>
</table>
```

### 🔹 Elements

* `<table>` → Defines the table.
* `<tr>` → Table row.
* `<th>` → Table header cell (bold, centered by default).
* `<td>` → Table data cell (normal cell).

---

## 📑 Additional Table Elements

### 1. `<caption>`

* Purpose: Adds a title/label to the table.
* Example:

  ```html
  <table border="1">
    <caption>Student Marks</caption>
    <tr><th>Name</th><th>Marks</th></tr>
    <tr><td>Ayesha</td><td>95</td></tr>
  </table>
  ```

---

### 2. `<thead>`, `<tbody>`, `<tfoot>`

* Purpose: Groups table sections. Useful for styling and accessibility.

Example:

```html
<table border="1">
  <thead>
    <tr><th>Subject</th><th>Marks</th></tr>
  </thead>
  <tbody>
    <tr><td>Math</td><td>90</td></tr>
    <tr><td>English</td><td>85</td></tr>
  </tbody>
  <tfoot>
    <tr><td>Total</td><td>175</td></tr>
  </tfoot>
</table>
```

---

### 3. `<colgroup>` and `<col>`

* Purpose: Apply styles/attributes to specific columns.

Example:

```html
<table border="1">
  <colgroup>
    <col style="background-color:lightblue">
    <col style="background-color:lightyellow">
  </colgroup>
  <tr><th>Name</th><th>Age</th></tr>
  <tr><td>Ali</td><td>20</td></tr>
  <tr><td>Ayesha</td><td>22</td></tr>
</table>
```

---

## 🎛️ Table Attributes

### 🔹 `<table>` Attributes

* `border` → Thickness of border (deprecated, use CSS).
* `cellspacing` → Space between cells (deprecated, use CSS `border-spacing`).
* `cellpadding` → Space inside cells (deprecated, use CSS `padding`).
* `width` / `height` → Size of table (use CSS instead).

### 🔹 `<th>` and `<td>` Attributes

* `colspan` → Merge cells horizontally.
* `rowspan` → Merge cells vertically.
* `align` → Align text (`left`, `center`, `right`) (deprecated, use CSS).
* `valign` → Vertical alignment (`top`, `middle`, `bottom`) (deprecated, use CSS).

Example with `colspan` and `rowspan`:

```html
<table border="1">
  <tr>
    <th rowspan="2">Name</th>
    <th colspan="2">Marks</th>
  </tr>
  <tr>
    <th>Math</th>
    <th>English</th>
  </tr>
  <tr>
    <td>Ahsan</td>
    <td>85</td>
    <td>90</td>
  </tr>
</table>
```
---

## 🎯 Conclusion

* **HTML Tables** organize data into rows and columns.
* Use `<thead>`, `<tbody>`, `<tfoot>` for structure.
* Use `rowspan` and `colspan` to merge cells.
* Use `<caption>`, `<colgroup>`, and `<col>` for extra meaning and styling.
* Modern best practice: **Use CSS for styling, not HTML attributes.**