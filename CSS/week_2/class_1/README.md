# 📘 Icons, Links, and Lists in CSS/HTML

## 1. Adding Icons in HTML

### 🔹 Purpose

Icons give visual cues, improve navigation, and enhance UI without needing full images. There are several ways to add icons:

### 🔸 Methods

#### a. **Icon Fonts (e.g., Font Awesome)**

* **How**: Include the font’s CSS, then use `<i>` or `<span>` with classes.

  ```html
  <i class="fa fa-home" aria-hidden="true"></i>
  ```
* **Advantages**: Scalable, styleable via CSS (color, size), lightweight.
* **Accessibility**: Add `aria-hidden="true"` if purely decorative; pair with screen-reader text if meaningful.

#### b. **SVG Icons**

* **Inline SVG**:

  ```html
  <svg width="24" height="24" aria-label="home icon" role="img">
    <path d="..."></path>
  </svg>
  ```
* **External SVG via `<img>`**:

  ```html
  <img src="icon.svg" alt="home icon" width="24" height="24">
  ```
* **Advantages**: Crisp at any resolution, can be animated, styled with CSS (`fill`, `stroke`).

#### c. **Image Icons**

* PNG/JPEG/GIF with `<img>`:

  ```html
  <img src="icon.png" alt="settings icon" width="24" height="24">
  ```

#### d. **Background Icons**

* Using CSS background:

  ```css
  .btn-settings {
    background: url('settings.svg') no-repeat center center;
    padding-left: 30px;
  }
  ```

### 🔹 Common Related CSS Properties

* `font-size` → scales icon fonts.
* `color` / `fill` → sets the color of font icons or inline SVG paths.
* `width` / `height` → for `<img>` or SVG sizing.
* `vertical-align` → aligns icon with text baseline.
* `margin`/`padding` → spacing around icon.

---

## 2. Anchor (`<a>`) Tag Styling and States

### 🔹 Purpose

Links are interactive elements. Styling them and their states gives users feedback and maintains usability.

### 🔸 CSS States (in order of typical user interaction priority):

1. `:link` → Unvisited link
2. `:visited` → Visited link
3. `:hover` → Mouse pointer over link
4. `:focus` → Keyboard/tab focus
5. `:active` → While the link is being clicked

> **Remember the LVHFA order** when writing in CSS to avoid specificity bugs (`:link`, `:visited`, `:hover`, `:focus`, `:active`).

### 🔹 Common Properties for Anchor Styling

#### 1. `color`

* **Purpose**: Link text color.
* **Values**: Named (`blue`), HEX (`#1a0dab`), RGB, HSL, etc.

  * Example: `color: #0066cc;` sets a custom blue.

#### 2. `text-decoration`

* **Purpose**: Underline, overline, etc.
* **Values**:

  * `none` → Remove underline.
  * `underline` → Default underlined link.
  * `overline`, `line-through`, combinations like `underline overline`.
  * Shorthand with style/color: `text-decoration: underline dotted red;`

#### 3. `cursor`

* **Purpose**: Shows pointer (hand) on hover.
* **Values**: `pointer` (typical for links), `default`, etc.

#### 4. `outline`

* **Purpose**: Focus ring for accessibility (keyboard navigation).
* **Values**:

  * `none` → Remove (avoid unless replaced accessibly).
  * `2px solid #005fcc` → Visible focus indicator.

#### 5. `background-color`

* **Purpose**: Highlight on hover/focus.
* **Values**: Any color to give feedback.

#### 6. `transition`

* **Purpose**: Smooth interpolation between state changes.
* **Example**: `transition: color 0.2s ease, background-color 0.2s ease;`

#### 7. `display`

* **Purpose**: Inline vs block behaviors for spacing/padding.
* **Values**:

  * `inline` → Default, cannot set width/height easily.
  * `inline-block` → Allows padding/margin while staying inline.
  * `block` → Full width.

### 🔸 Example of state styling:

```css
a {
  color: #0066cc;
  text-decoration: none;
  transition: color 0.2s ease;
}
a:visited {
  color: #551a8b;
}
a:hover {
  color: #004499;
  text-decoration: underline;
}
a:focus {
  outline: 2px dashed #005fcc;
}
a:active {
  color: #002266;
}
```

---

## 3. List Styling (Ordered & Unordered)

### 🔹 Purpose

Lists (`<ul>`, `<ol>`, `<li>`) are used for grouping items. CSS lets you control markers, spacing, and custom numbering.

### 🔹 Properties

#### 1. `list-style-type`

* **Purpose**: Defines the marker symbol or numbering style.
* **Values**:

  * `disc` → Filled circle (default for `<ul>`).
  * `circle` → Hollow circle.
  * `square` → Square bullet.
  * `decimal` → Numbers (1,2,3...) for `<ol>`.
  * `decimal-leading-zero` → 01, 02...
  * `lower-roman`, `upper-roman` → i, ii,... / I, II...
  * `lower-alpha`, `upper-alpha` → a, b,... / A, B...
  * `none` → No marker.

#### 2. `list-style-position`

* **Purpose**: Determines where the marker appears relative to the content.
* **Values**:

  * `outside` → Marker is outside the content box (default).
  * `inside` → Marker is inside, affecting text wrapping.

#### 3. `list-style-image`

* **Purpose**: Use an image instead of default marker.
* **Values**:

  * `url("bullet.png")` → Custom image.
  * `none` → Fallback to type.

#### 4. `list-style` (Shorthand)

* **Purpose**: Combines type, position, and image.
* **Example**:

  ```css
  list-style: square inside url('checkmark.png');
  ```

#### 5. `counter-reset` / `counter-increment`

* **Purpose**: Manual custom numbering for advanced list designs.
* **Example**:

  ```css
  ol.custom {
    counter-reset: step;
  }
  ol.custom li::before {
    counter-increment: step;
    content: counter(step) ". ";
  }
  ```

#### 6. `padding` / `margin` (on `ul`/`ol`)

* **Purpose**: Default indentation and spacing around lists.
* Browsers typically apply left `padding` or `margin`; can be reset:

  ```css
  ul {
    margin: 0;
    padding: 0;
  }
  ```

---

## ✅ Summary Tips

* To remove default bullets/numbers:

  ```css
  ul, ol {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  ```
* Always keep focus styles (`:focus`) on links for keyboard users unless replaced accessibly.
* Use `aria-label` or screen-reader text when icons carry meaning.
* Combine shorthand (`list-style`, `text-decoration`) for cleaner code when possible.

---

## 🎯 Conclusion

This section gives students full control over:

* Adding and styling icons in HTML (font icons, SVGs, images).
* Styling links in all their interactive states with clear feedback.
* Controlling list appearance with markers, custom numbering, and layout.