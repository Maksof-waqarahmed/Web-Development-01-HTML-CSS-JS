# 📘 HTML Tables

HTML **tables** are used to organize and display **tabular data** — information arranged in rows and columns.
They are ideal for presenting **structured data** such as marksheets, price lists, product comparisons, or schedules.

> ⚠️ **Note:**
> Tables should *not* be used for web page layout. Use **CSS Grid** or **Flexbox** for that purpose.
> Tables are meant only for **data representation**.

---

## 🏗️ 1. Basic Table Structure

Every HTML table is built using rows (`<tr>`) and cells (`<td>` or `<th>`).
A basic example:

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

### 🔹 Key Elements

| Tag       | Purpose                                                   |
| --------- | --------------------------------------------------------- |
| `<table>` | Defines the table container.                              |
| `<tr>`    | Represents a single row.                                  |
| `<th>`    | Defines a **header cell** (bold and centered by default). |
| `<td>`    | Defines a **data cell**.                                  |

🟢 **Result:** Displays a simple, bordered table with one header row and one data row.

---

## 📑 2. Additional Table Elements

### 2.1 `<caption>`

Adds a **title** or **label** above the table to describe its content.

```html
<table border="1">
  <caption>Student Marks</caption>
  <tr><th>Name</th><th>Marks</th></tr>
  <tr><td>Ayesha</td><td>95</td></tr>
</table>
```

✅ **Tip:** `<caption>` improves accessibility and readability.

---

### 2.2 `<thead>`, `<tbody>`, and `<tfoot>`

These tags divide a table into **logical sections**, making it easier to style and manage.

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

💡 **Benefits:**

* Improves code readability
* Enhances accessibility for screen readers
* Allows independent styling (e.g., sticky headers)

---

## ⚙️ 3. Table Attributes

Although many are deprecated (replaced by CSS), it’s useful to understand them.

### 🔹 `<table>` Attributes

| Attribute         | Description           | Modern Alternative      |
| ----------------- | --------------------- | ----------------------- |
| `border`          | Sets border thickness | Use `border` in CSS     |
| `cellspacing`     | Space between cells   | `border-spacing` (CSS)  |
| `cellpadding`     | Space inside cells    | `padding` (CSS)         |
| `width`, `height` | Defines table size    | `width`, `height` (CSS) |

---

### 🔹 `<th>` and `<td>` Attributes

| Attribute | Description                       | Example                |
| --------- | --------------------------------- | ---------------------- |
| `colspan` | Merge cells horizontally          | `<td colspan="2">`     |
| `rowspan` | Merge cells vertically            | `<td rowspan="2">`     |
| `align`   | Horizontal alignment (deprecated) | `text-align` (CSS)     |
| `valign`  | Vertical alignment (deprecated)   | `vertical-align` (CSS) |

#### Example — Using `colspan` and `rowspan`

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

🟢 **Output:** The “Marks” header spans two columns, and the “Name” header spans two rows.

---

## 🎯 Conclusion

* HTML **tables** organize data into clear rows and columns.
* Use **semantic sections** like `<thead>`, `<tbody>`, and `<tfoot>` for structure.
* Use **`rowspan`** and **`colspan`** to merge cells.
* Add **captions** and **column groups** for better readability.
* Always use **CSS for styling** instead of old HTML attributes.

> ✅ In modern web design, tables remain powerful tools for **data representation** — not layout.

---
