# 📘 HTML Links, Images, and Extra Markup

## 1. 🔗 HTML Links (`<a>`)

### 🔹 Purpose

Links (anchors) connect one page to another, allow navigation, and can also link to sections, email addresses, or files.

### 🔹 Syntax

```html
<a href="URL">Link Text</a>
```

### 🔹 Types of Link Paths

#### a. **Absolute Links**

* **Purpose**: Point to a full web address including protocol; used to link to other websites or full paths.
* **Example**:

  ```html
  <a href="https://www.google.com">Visit Google</a>
  <a href="https://example.com/page.html">External Page</a>
  ```
* **Explanation**: Always works regardless of the current page location because it includes the complete URL (e.g., `https://domain.com/folder/file.html`).

#### b. **Relative Links**

* **Purpose**: Point to files/pages relative to the current document’s location; used for internal navigation within the same website.
* **Examples**:

  ```html
  <!-- Same folder -->
  <a href="about.html">About Us</a>

  <!-- Subfolder -->
  <a href="blog/post1.html">First Blog Post</a>

  <!-- Parent folder -->
  <a href="../contact.html">Contact</a>
  ```
* **Explanation**: Shorter and depends on directory structure. Easier to move site as long as relative structure is preserved.

---

### 🔹 Attributes

* `href` → Destination URL (absolute or relative).
* `target` → Defines where to open the link.

  * `_self` → Default, opens in same tab.
  * `_blank` → Opens in new tab.
  * `_parent` → Opens in parent frame.
  * `_top` → Opens in full body of window.
* `title` → Tooltip text shown on hover.
* `download` → Prompts file download instead of navigation.
* `rel` → Defines relationship (important for SEO/security).

  * `nofollow`, `noopener`, `noreferrer`.

### 🔹 Examples

```html
<!-- Absolute link to external site -->
<a href="https://www.google.com">Visit Google</a>

<!-- Relative link to an internal page -->
<a href="about.html">About Us</a>

<!-- Open in new tab -->
<a href="services.html" target="_blank">Our Services</a>

<!-- Email link -->
<a href="mailto:info@example.com">Send Email</a>

<!-- Phone link -->
<a href="tel:+923001234567">Call Us</a>

<!-- Download link -->
<a href="files/report.pdf" download>Download Report</a>

<!-- Link with relationship and tooltip -->
<a href="https://example.com" rel="noopener" title="Go to example">Example Site</a>
```

---

## 2. 🖼️ HTML Images (`<img>`)

### 🔹 Purpose

The `<img>` tag is used to embed images into a web page.

### 🔹 Syntax

```html
<img src="image.jpg" alt="Description" width="400" height="300">
```

### 🔹 Attributes

* `src` → Image source (URL or relative path).
* `alt` → Alternative text (shown if image fails to load, important for accessibility/SEO).
* `title` → Tooltip text.
* `width` / `height` → Define size (can be in px or %).
* `loading` → Controls image loading.

  * `lazy` → Loads only when needed (performance).
  * `eager` → Loads immediately.
* `srcset` / `sizes` → Provide multiple image versions for responsive images.

### 🔹 Examples

```html
<!-- Basic image -->
<img src="logo.png" alt="Company Logo">

<!-- Image with fixed size -->
<img src="banner.jpg" alt="Banner" width="600" height="200">

<!-- Lazy loading -->
<img src="large-image.jpg" alt="Lazy Example" loading="lazy">
```

---

## 3. 📑 Extra Markup

### 🔹 Semantic Elements (HTML5)

Semantic tags provide **meaning** to the content, helping SEO and accessibility.

* `<header>` → Top section (logo, nav).
* `<nav>` → Navigation links.
* `<main>` → Main content.
* `<section>` → Section of a document.
* `<article>` → Independent piece of content.
* `<aside>` → Sidebar content.
* `<footer>` → Bottom section (credits, contact info).
* `<figure>` → Groups media (images, diagrams).
* `<figcaption>` → Caption for `<figure>`.
* `<time>` → Represents date/time.

Example:

```html
<header>
  <h1>My Blog</h1>
  <nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
  </nav>
</header>
<main>
  <article>
    <h2>Article Title</h2>
    <p>Article content...</p>
  </article>
</main>
<footer>
  <p>&copy; 2025 My Blog</p>
</footer>
```

---

### 🔹 Multimedia Elements

* `<audio>` → Embeds audio.
* `<video>` → Embeds video.
* `<source>` → Defines multiple file formats.
* `<track>` → Subtitles/captions for video.
* `<iframe>` → Embeds another HTML page or external resource into the current web page.

Example:

```html
<!-- Audio -->
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
  Your browser does not support audio.
</audio>

<!-- Video -->
<video width="400" controls>
  <source src="movie.mp4" type="video/mp4">
  Your browser does not support video.
</video>

<!-- Iframe -->
### 🔹 Attributes

* `src` → The URL of the page/resource to display.
* `width`, `height` → Dimensions of the frame.
* `title` → Accessibility (describe content inside iframe).
* `frameborder` → (Deprecated, use CSS `border`).
* `allowfullscreen` → Allows full-screen display (videos).
* `loading="lazy"` → Delays loading until needed (performance).
* `allow` → Defines permissions (like autoplay for videos, geolocation).

### 🔹 Common Uses of `<iframe>`

#### 1. **Embed External Platforms / Websites**

* Used to display another website, login widget, or form inside your page.

Example:

```html
<iframe src="https://www.wikipedia.org" width="800" height="400" title="Wikipedia"></iframe>
```

#### 2. **Embed Google Maps**

* Helps users find business locations directly on your site.

Example:

```html
<iframe 
  src="https://www.google.com/maps/embed?pb=!1m18!..." 
  width="600" height="450" style="border:0;" 
  allowfullscreen="" loading="lazy" 
  referrerpolicy="no-referrer-when-downgrade"
  title="Google Maps Location">
</iframe>
```

#### 3. **Embed YouTube / Vimeo Videos**

* Used for adding tutorials, ads, or media content.

Example:

```html
<iframe 
  width="560" height="315" 
  src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
  title="YouTube video player" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>
```

---

### 🔹 Other Use Cases

* **Embed Forms** (e.g., Google Forms, Typeform):

  ```html
  <iframe src="https://docs.google.com/forms/d/e/example/viewform" width="640" height="800"></iframe>
  ```

* **Embed Social Media Posts** (Twitter/X, Facebook):
  Many platforms give an iframe embed code to show posts.

* **Embed Dashboards / Reports** (Power BI, Data Studio, Tableau):
  Great for analytics or reports.

* **Interactive Widgets** (Calendars, Chatbots, Payment Widgets).

---

## ⚠️ Security Note

* **XSS Risks**: If you embed unknown sources, they may inject scripts.
* Use `sandbox` attribute for security (restricts iframe capabilities).

Example:

```html
<iframe src="page.html" sandbox></iframe>
```

---

✅ Now `<iframe>` is fully documented in your HTML guide with **3 main uses (platform, map, video)** + extra real-world cases.

```

---

### 🔹 Character Entities

HTML uses **entities** for special characters that can’t be typed directly.

* `&lt;` → `<` (less than)
* `&gt;` → `>` (greater than)
* `&amp;` → `&`
* `&quot;` → `"`
* `&copy;` → ©
* `&nbsp;` → Non-breaking space

Example:

```html
<p>5 &lt; 10 and 10 &gt; 5</p>
<p>&copy; 2025 My Company</p>
```

---

### 🔹 Block vs Inline Elements

* **Block Elements** → Take full width, start on a new line. (e.g., `<div>`, `<p>`, `<h1>`).
* **Inline Elements** → Only take space of content, no line break. (e.g., `<span>`, `<a>`, `<strong>`).

Example:

```html
<p>This is a <span style="color:red;">red word</span> inside a paragraph.</p>
```

---

## 🎯 Conclusion

* **Links (`<a>`)** connect pages, emails, files, and can be styled with attributes.
* **Images (`<img>`)** embed visuals with accessibility (`alt`) and performance (`loading`, `srcset`).
* **Extra Markup** (semantic tags, multimedia, entities) makes HTML more meaningful, structured, and user-friendly.