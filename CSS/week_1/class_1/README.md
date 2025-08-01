# 📘 CSS (Cascading Style Sheets)

## 🟢 Introduction

**CSS (Cascading Style Sheets)** is a stylesheet language used to describe the presentation of HTML documents. With CSS, we can control the **look, layout, and design** of web pages, making them visually attractive and user-friendly.

* **Creator**: Håkon Wium Lie
* **Year Introduced**: 1996 (Standardized by W3C)
* **Purpose**: To separate content (HTML) from presentation (design).
* **Full Form**: Cascading Style Sheets
* **Cascade Meaning**: If multiple styles are applied to an element, CSS decides which style has priority based on order, importance, and specificity.

---

### 🔹 Ways to Write CSS

CSS can be written in **three different ways**:

1. **Inline CSS**

   * Written directly inside an HTML element using the `style` attribute.
   * **Purpose**: To apply a style to a single element only.
   * **Syntax**:

     ```html
     <h1 style="color: red; font-size: 20px;">Hello World</h1>
     ```
   * **Priority**: Highest (overrides internal and external CSS).

---

2. **Internal CSS**

   * Written inside the `<style>` tag within the `<head>` section of an HTML document.
   * **Purpose**: To style elements on a single HTML page.
   * **Syntax**:

     ```html
     <style>
       h1 {
         color: blue;
         font-size: 24px;
       }
     </style>
     ```
   * **Priority**: Medium (overridden by inline but overrides external if conflict).

---

3. **External CSS**

   * Written in a separate `.css` file and linked using `<link>` inside `<head>`.
   * **Purpose**: To style multiple web pages consistently with one stylesheet.
   * **Syntax**:

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
   * **Priority**: Lowest (but preferred for maintainability).

---

### 🔹 Priority of CSS (Specificity Rules)

When multiple CSS styles target the same element, **priority** is applied as:

1. **Inline CSS** → Highest priority.
2. **Internal CSS** → Overrides external if conflict.
3. **External CSS** → Lowest priority (but recommended for large projects).
4. **Important Rule**: Adding `!important` after a property value gives it the **highest priority**, even above inline.

   ```css
   p {
     color: red !important;
   }
   ```

---

### 🔹 Syntax of CSS

A CSS rule is made up of **selectors, properties, and values**.

```css
selector {
  property: value;
}
```

* **Selector** → Targets the element(s) (e.g., `h1`, `.class`, `#id`).
* **Property** → The style attribute you want to change (e.g., `color`, `font-size`).
* **Value** → The specific value for the property (e.g., `red`, `16px`).

**Example**:

```css
p {
  color: blue;
  font-size: 18px;
}
```

This will make all `<p>` elements blue and size 18px.

---

### 🔹 Selectors in CSS

Selectors are used to target HTML elements for styling.

1. **Universal Selector (`*`)**

   * Selects all elements.
   * Example:

     ```css
     * {
       margin: 0;
       padding: 0;
     }
     ```

2. **Element Selector**

   * Selects elements by tag name.
   * Example:

     ```css
     h1 {
       color: red;
     }
     ```

3. **Class Selector (`.classname`)**

   * Selects elements with a specific class attribute.
   * Example:

     ```css
     .highlight {
       background: yellow;
     }
     ```

4. **ID Selector (`#idname`)**

   * Selects an element with a specific ID (unique per page).
   * Example:

     ```css
     #main {
       font-size: 20px;
     }
     ```

5. **Group Selector (`,`)**

   * Applies the same style to multiple selectors.
   * Example:

     ```css
     h1, h2, p {
       font-family: Arial;
     }
     ```

6. **Descendant Selector (`space`)**

   * Selects elements inside another element.
   * Example:

     ```css
     div p {
       color: green;
     }
     ```

7. **Child Selector (`>`)**

   * Selects direct children only.
   * Example:

     ```css
     div > p {
       color: blue;
     }
     ```

8. **Pseudo-classes (e.g., `:hover`, `:first-child`)**

   * Select elements in a special state.
   * Example:

     ```css
     a:hover {
       color: orange;
     }
     ```

9. **Pseudo-elements (e.g., `::before`, `::after`)**

   * Select part of an element.
   * Example:

     ```css
     p::first-letter {
       font-size: 30px;
     }
     ```
---

## 📝 Text-Related CSS Properties

### 1. **color**

* **Purpose**: Sets the color of the text.
* **Values**:

  * `red`, `blue`, `green` → Named colors predefined in CSS.
  * `#ff0000` → HEX code, represents colors using hexadecimal values.
  * `rgb(255,0,0)` → RGB format, defines colors using Red, Green, Blue values.
  * `rgba(255,0,0,0.5)` → Same as RGB but with an additional Alpha (transparency).
  * `hsl(0,100%,50%)` → Defines color using Hue, Saturation, and Lightness.
  * `hsla(0,100%,50%,0.5)` → HSL format with Alpha transparency.

---

### 2. **font-family**

* **Purpose**: Defines the font style of the text.
* **Values**:

  * `"Arial"`, `"Times New Roman"` → Specific fonts installed on the system.
  * `serif`, `sans-serif`, `monospace` → Generic font families as fallbacks.

---

### 3. **font-size**

* **Purpose**: Defines the size of the text.
* **Values**:

  * `small`, `medium`, `large` → Predefined keyword sizes.
  * `px`, `pt` → Absolute units for fixed size (pixels, points).
  * `em`, `rem`, `%` → Relative units based on parent, root, or container size.

---

### 4. **font-weight**

* **Purpose**: Defines the thickness (boldness) of the text.
* **Values**:

  * `normal` → Default weight (usually 400).
  * `bold` → Makes text bold (usually 700).
  * `lighter` → Lighter than the parent’s weight.
  * `bolder` → Bolder than the parent’s weight.
  * `100–900` → Numeric scale, where 100 is thinnest and 900 is thickest.

---

### 5. **font-style**

* **Purpose**: Defines the slant or style of the font.
* **Values**:

  * `normal` → Regular text.
  * `italic` → Italicized text, designed font.
  * `oblique` → Slanted version of the text, usually simulated.

---

### 6. **font-variant**

* **Purpose**: Controls text display in small caps.
* **Values**:

  * `normal` → Regular text.
  * `small-caps` → Converts lowercase letters into small uppercase style.

---

### 7. **font (Shorthand)**

* **Purpose**: Shorthand property to define multiple font-related properties in one line.
* **Includes**: `font-style`, `font-variant`, `font-weight`, `font-size`, `line-height`, `font-family`.
* **Example**:

  ```css
  font: italic small-caps bold 16px/1.5 Arial, sans-serif;
  ```

---

### 8. **text-align**

* **Purpose**: Defines horizontal alignment of the text.
* **Values**:

  * `left` → Aligns text to the left (default in LTR languages).
  * `right` → Aligns text to the right.
  * `center` → Centers the text horizontally.
  * `justify` → Stretches text so each line has equal width.

---

### 9. **text-decoration**

* **Purpose**: Adds or removes decorations from text.
* **Values**:

  * `none` → No decoration.
  * `underline` → Adds a line below the text.
  * `overline` → Adds a line above the text.
  * `line-through` → Draws a line through the text (strikethrough).
  * Multiple values like `underline overline` can be combined.

#### Shorthand:

* `text-decoration` combines: `text-decoration-line`, `text-decoration-style`, `text-decoration-color`.
* **Example**:

  ```css
  text-decoration: underline dotted red;
  ```

---

### 10. **text-transform**

* **Purpose**: Changes the case (capitalization) of text.
* **Values**:

  * `none` → Keeps text as written.
  * `uppercase` → Converts all text to capital letters.
  * `lowercase` → Converts all text to lowercase letters.
  * `capitalize` → Capitalizes the first letter of each word.

---

### 11. **letter-spacing**

* **Purpose**: Controls the space between characters.
* **Values**:

  * `normal` → Default spacing.
  * Custom values: `2px`, `0.5em` → Adds extra spacing.

---

### 12. **word-spacing**

* **Purpose**: Controls the space between words.
* **Values**:

  * `normal` → Default word spacing.
  * Custom values: `5px`, `1em` → Increases spacing between words.

---

### 13. **line-height**

* **Purpose**: Defines the vertical space between lines of text.
* **Values**:

  * `normal` → Default spacing.
  * Number (e.g., `1.5`) → Multiplies the font size.
  * Length (e.g., `20px`) → Fixed line height.

---

### 14. **text-shadow**

* **Purpose**: Adds shadow effects to text.
* **Values**: `horizontal-offset vertical-offset blur-radius color`
* Example: `2px 2px 5px gray` → Creates a gray shadow 2px right, 2px down, with 5px blur.

---

### 15. **direction**

* **Purpose**: Defines the direction of text.
* **Values**:

  * `ltr` → Left to right (default, English and most languages).
  * `rtl` → Right to left (Arabic, Urdu, Hebrew).

---

### 16. **white-space**

* **Purpose**: Controls how spaces and line breaks are handled.
* **Values**:

  * `normal` → Collapses spaces, wraps text as needed.
  * `nowrap` → Prevents wrapping, keeps text in one line.
  * `pre` → Preserves spaces and line breaks exactly as written.
  * `pre-line` → Preserves line breaks but collapses multiple spaces.
  * `pre-wrap` → Preserves both spaces and line breaks, allows wrapping.

---

### 17. **overflow-wrap (word-wrap)**

* **Purpose**: Defines how long words should break.
* **Values**:

  * `normal` → Words do not break unless necessary.
  * `break-word` → Breaks words only when they overflow.
  * `anywhere` → Allows breaking at any point inside the word.

---

### 18. **text-overflow**

* **Purpose**: Controls what happens when text overflows its container.
* **Values**:

  * `clip` → Cuts off extra text.
  * `ellipsis` → Shows three dots (`...`) for overflowed text.

---

## 🎯 Conclusion

CSS provides powerful text-related properties that allow developers to design readable and attractive web pages.
**Shorthand properties** like `font` and `text-decoration` make code shorter and cleaner, while detailed values give complete control over text styling.