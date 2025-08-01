# 📘 HTML Forms

## 🟢 Introduction

An **HTML form** collects user input and sends it to a server for processing. Forms are used in **login pages, registrations, search bars, payments, and feedback**.

* **Tag**: `<form>`
* **Elements**: `<input>`, `<textarea>`, `<select>`, `<button>`, etc.
* **Attributes**: Define how data is sent.

---

## 🏗️ Basic Structure

```html
<form action="/submit" method="post">
  <label for="username">Username:</label>
  <input type="text" id="username" name="username">

  <label for="password">Password:</label>
  <input type="password" id="password" name="password">

  <button type="submit">Login</button>
</form>
```

### 🔹 Important Attributes of `<form>`

* `action` → URL where form data is sent.
* `method` → How data is sent:

  * `get` → Data in URL (used for search forms).
  * `post` → Data in request body (used for login, sensitive info).
* `target` → Where to open the response (`_self`, `_blank`).
* `enctype` → How form data is encoded (used for file upload):

  * `application/x-www-form-urlencoded` → Default.
  * `multipart/form-data` → Required for file uploads.
  * `text/plain` → Sends plain text.

---

## ✍️ Input Types (`<input>`)

The `<input>` element is the most important form control. It has many types:

### 🔹 Text Fields

```html
<input type="text" name="fullname" placeholder="Enter your name">
```

* `type="text"` → Single-line text input.
* `placeholder` → Shows hint text.

### 🔹 Password

```html
<input type="password" name="pass" placeholder="Enter password">
```

* Characters hidden (dots/stars).

### 🔹 Email

```html
<input type="email" name="email" required>
```

* Validates email format.

### 🔹 Number

```html
<input type="number" name="age" min="1" max="100" step="1">
```

* Accepts only numbers with optional range/step.

### 🔹 Checkbox

```html
<input type="checkbox" name="subscribe" value="yes"> Subscribe
```

* Allows multiple selections.

### 🔹 Radio

```html
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female
```

* Select one option from a group (same `name`).

### 🔹 File Upload

```html
<input type="file" name="resume" accept=".pdf,.docx">
```

* Allows file selection; `accept` restricts formats.

### 🔹 Hidden

```html
<input type="hidden" name="userId" value="12345">
```

* Invisible field for storing extra info.

---

## 📋 Other Form Controls

### 1. **Textarea**

```html
<textarea name="message" rows="5" cols="30" placeholder="Write here..."></textarea>
```

* Multi-line text input.

---

### 2. **Select Dropdown**

```html
<select name="country">
  <option value="pk">Pakistan</option>
  <option value="us">USA</option>
  <option value="uk">UK</option>
</select>
```

* `<select>` creates a dropdown menu.
* `<option>` defines choices.
* Attributes:

  * `multiple` → Allows multiple selections.
  * `selected` → Pre-selected option.

---

### 3. **Datalist (Autocomplete)**

```html
<input list="browsers" name="browser">
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Edge">
</datalist>
```

* Provides suggestions while typing.

---

### 4. **Buttons**

```html
<button type="submit">Submit</button>
<button type="reset">Reset</button>
<button type="button">Click Me</button>
```

* `submit` → Sends form.
* `reset` → Clears form fields.
* `button` → General button (needs JavaScript).

---

## 📦 Grouping & Labels

### 1. **Label**

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email">
```

* Connects text with input (using `for` and `id`).
* Improves accessibility.

### 2. **Fieldset & Legend**

```html
<fieldset>
  <legend>Personal Information</legend>
  <input type="text" placeholder="Name">
  <input type="email" placeholder="Email">
</fieldset>
```

* `<fieldset>` groups inputs.
* `<legend>` gives group title.

---

## ⚙️ Useful Input Attributes

* `required` → Field must be filled.
* `readonly` → Field cannot be edited.
* `disabled` → Field is disabled.
* `pattern` → Regex pattern validation.
* `maxlength` / `minlength` → Restrict text length.
* `value` → Pre-filled value.
* `autocomplete` → Controls browser auto-fill.

Example:

```html
<input type="text" name="username" required minlength="3" maxlength="12" autocomplete="off">
```

---

## 🆕 HTML5 Input Types

* `date` → Calendar picker.
* `time` → Time picker.
* `datetime-local` → Date + time picker.
* `month` → Month/year picker.
* `week` → Week picker.
* `color` → Color picker.
* `range` → Slider input.
* `search` → Search field (styled differently).
* `tel` → Telephone number.
* `url` → Website URL.

Example:

```html
<input type="date" name="dob">
<input type="color" name="favColor">
<input type="range" name="volume" min="0" max="100">
```

---

## 🔒 Form Validation

* **Built-in validation**: `required`, `email`, `number`, `pattern`.
* **Custom validation**: JavaScript.

Example:

```html
<input type="email" name="email" required pattern=".+@gmail\.com">
```

---

## 🎯 Conclusion

* Forms allow collecting **user input**.
* Use correct **input types** for better validation and user experience.
* Group inputs with **labels, fieldsets**.
* Modern HTML5 adds new types like `date`, `color`, `range` for rich UI.
* Always use **validation and accessibility** features.

---

# 📝 Extra Form Attributes & Elements

## 🔹 Form Attributes (on `<form>`)

1. **accept-charset** → Defines character encoding of submitted data (default = UTF-8).

   ```html
   <form action="" accept-charset="UTF-8">
   ```
2. **autocomplete** → Suggests previously entered values.

   * Values: `on`, `off`

   ```html
   <form action="" autocomplete="on">
   ```
3. **name** → Gives the form a name (useful with JS).

   ```html
   <form name="loginForm">
   ```
5. **enctype** → Already covered (used with file uploads).
6. **method** → Already covered (`get`, `post`).
7. **target** → Already covered (`_self`, `_blank`).

---

## 🔹 Input Attributes (on `<input>`)

1. **size** → Defines visible width of input in characters.

   ```html
   <input type="text" size="30">
   ```
2. **step** → Defines valid intervals for number/range.

   ```html
   <input type="number" min="0" max="100" step="5">
   ```
3. **list** → Connects input with `<datalist>`.

   ```html
   <input list="browsers">
   ```
4. **spellcheck** (global attribute) → Checks spelling/grammar in text fields.

   ```html
   <textarea spellcheck="true"></textarea>
   ```
5. **multiple** → Allows selecting multiple files or emails.

   ```html
   <input type="file" multiple>
   <input type="email" multiple>
   ```
6. **pattern** → Already covered, but reminder it only works with `text`, `email`, `tel`, `url`.
7. **inputmode** → Hints at virtual keyboard type (mobile).

   * Values: `text`, `numeric`, `decimal`, `email`, `tel`, `url`.

   ```html
   <input type="text" inputmode="numeric">
   ```
8. **min** / **max** → Define numeric/date boundaries.

   ```html
   <input type="date" min="2025-01-01" max="2025-12-31">
   ```
9. **form** → Connects input to another form (even if not inside `<form>`).

   ```html
   <input type="text" name="extra" form="myForm">
   ```
10. **formaction** (on submit button) → Overrides `action` of the form.

    ```html
    <button type="submit" formaction="save.php">Save</button>
    ```

---

## 🔹 Extra Form Fields

1. **Search Field**

   ```html
   <input type="search" name="query" placeholder="Search...">
   ```
2. **Progress & Meter**

   * `<progress>` → Shows progress (e.g., upload).
   * `<meter>` → Shows a known measurement.

   ```html
   <progress value="70" max="100"></progress>
   <meter value="0.7">70%</meter>
   ```
3. **Color Picker** → Already covered (`<input type="color">`).
4. **Range Slider** → Already covered (`<input type="range">`).

---

# ✅ Final Check (Complete List)

* **Form-level attributes**: `action`, `method`, `target`, `enctype`, `novalidate`, `autocomplete`, `accept-charset`, `name`.
* **Input-level attributes**: `type`, `name`, `id`, `value`, `placeholder`, `required`, `readonly`, `disabled`, `pattern`, `maxlength`, `minlength`, `size`, `min`, `max`, `step`, `multiple`, `list`, `spellcheck`, `inputmode`, `autocomplete`, `autofocus`, `checked`, `selected`.
* **Button overrides**: `formaction`, `formenctype`, `formmethod`, `formnovalidate`, `formtarget`.
* **Elements**: `<input>`, `<textarea>`, `<select>`, `<option>`, `<datalist>`, `<button>`, `<label>`, `<fieldset>`, `<legend>`, `<output>`, `<progress>`, `<meter>`.