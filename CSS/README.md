# 🎨 CSS Learning Roadmap: Beginner to Advanced

A step-by-step guide to learning CSS after HTML. Every topic has a **simple explanation** and a **clear example** you can copy and try.

## 📚 Table of Contents

- [Phase 1: CSS Fundamentals](#phase-1-css-fundamentals)
- [Phase 2: CSS Box Model](#phase-2-css-box-model)
- [Phase 3: CSS Layout](#phase-3-css-layout)
- [Phase 4: Flexbox](#phase-4-flexbox)
- [Phase 5: CSS Grid](#phase-5-css-grid)
- [Phase 6: Responsive Web Design](#phase-6-responsive-web-design)
- [Phase 7: Advanced CSS](#phase-7-advanced-css)
- [Phase 8: CSS Projects](#phase-8-css-projects)
- [Study Tips](#study-tips)

---

# Phase 1: CSS Fundamentals

## 1. What is CSS?

**CSS** stands for **Cascading Style Sheets**. HTML builds the *structure* of a page (headings, paragraphs, images). CSS controls the *look* (colors, spacing, fonts, layout).

Think of a house: HTML is the walls and rooms, CSS is the paint, furniture and decoration.

**Without CSS:** plain black text on a white page.
**With CSS:** colors, layouts, animations, responsive design.

```html
<h1>Hello World</h1>
```

```css
h1 {
  color: blue;
  font-size: 40px;
}
```

---

## 2. Types of CSS

There are three ways to add CSS to an HTML page.

### a) Inline CSS

Written directly inside an HTML tag using the `style` attribute. It affects only that one element.

```html
<p style="color: red; font-size: 20px;">This is red text.</p>
```

✅ Quick for tests
❌ Hard to maintain, messy for big projects

### b) Internal CSS

Written inside a `<style>` tag in the `<head>` of the HTML file. It affects only that page.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    p {
      color: green;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <p>This is green text.</p>
</body>
</html>
```

✅ Good for single-page demos
❌ Cannot be reused on other pages

### c) External CSS (Best Practice ⭐)

Written in a separate `.css` file and linked to the HTML file. One file can style many pages.

**index.html**
```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <p>This is styled by an external file.</p>
</body>
</html>
```

**style.css**
```css
p {
  color: purple;
  font-size: 18px;
}
```

✅ Clean, reusable, professional
Always use this in real projects.

---

## 3. CSS Syntax

A CSS rule has a **selector** and a **declaration block**. Each declaration is a **property: value;** pair.

```css
selector {
  property: value;
}
```

Example:

```css
h1 {
  color: red;        /* property: color, value: red */
  text-align: center;
}
```

- `h1` is the **selector** (what to style)
- `color` is the **property** (what to change)
- `red` is the **value** (how to change it)
- `/* ... */` is a **comment**

---

## 4. CSS Selectors

Selectors choose which HTML elements to style.

### Element selector
Selects all elements of a given tag.

```css
p {
  color: gray;
}
```

### Class selector (`.`)
Selects elements with a `class`. Can be reused on many elements.

```html
<p class="highlight">Important</p>
<p class="highlight">Also important</p>
```

```css
.highlight {
  background-color: yellow;
}
```

### ID selector (`#`)
Selects one unique element. An id should be used only once per page.

```html
<h1 id="main-title">Welcome</h1>
```

```css
#main-title {
  color: darkblue;
}
```

### Universal selector (`*`)
Selects everything.

```css
* {
  margin: 0;
  padding: 0;
}
```

### Group selector (`,`)
Applies the same style to several selectors.

```css
h1, h2, h3 {
  font-family: Arial, sans-serif;
}
```

### Descendant selector (space)
Selects elements inside another element.

```css
div p {
  color: blue;   /* every <p> inside a <div> */
}
```

### Child selector (`>`)
Selects only direct children.

```css
ul > li {
  list-style: square;
}
```

### Attribute selector
Selects by attribute.

```css
input[type="text"] {
  border: 2px solid green;
}
```

---

## 5. Colors

CSS gives many ways to write colors.

```css
/* 1. Color names */
h1 { color: red; }

/* 2. HEX codes */
h1 { color: #ff0000; }

/* 3. RGB */
h1 { color: rgb(255, 0, 0); }

/* 4. RGBA (with transparency, 0 to 1) */
h1 { color: rgba(255, 0, 0, 0.5); }

/* 5. HSL (hue, saturation, lightness) */
h1 { color: hsl(0, 100%, 50%); }
```

Two main properties:

- `color` changes the **text** color
- `background-color` changes the **background** color

```css
p {
  color: white;
  background-color: #333;
}
```

---

## 6. Backgrounds

```css
.hero {
  background-color: #f0f0f0;                 /* solid color */
  background-image: url("banner.jpg");       /* image */
  background-repeat: no-repeat;              /* repeat, repeat-x, repeat-y */
  background-size: cover;                    /* cover, contain, 100px */
  background-position: center;               /* where the image sits */
  background-attachment: fixed;              /* parallax effect */
}
```

**Gradient background:**

```css
.gradient {
  background: linear-gradient(to right, #ff7e5f, #feb47b);
}
```

**Shorthand:**

```css
.hero {
  background: #222 url("banner.jpg") no-repeat center / cover;
}
```

---

## 7. Text Properties

```css
p {
  color: #333;
  text-align: center;          /* left, right, center, justify */
  text-decoration: underline;  /* none, underline, line-through */
  text-transform: uppercase;   /* lowercase, capitalize */
  letter-spacing: 2px;         /* space between letters */
  word-spacing: 5px;           /* space between words */
  line-height: 1.6;            /* space between lines */
  text-indent: 30px;           /* indent first line */
  text-shadow: 2px 2px 4px gray;
}
```

Remove the underline from links:

```css
a {
  text-decoration: none;
}
```

---

## 8. Fonts

```css
body {
  font-family: "Poppins", Arial, sans-serif;  /* first choice, then fallbacks */
  font-size: 16px;
  font-weight: bold;         /* normal, bold, or 100 to 900 */
  font-style: italic;        /* normal, italic */
}
```

**Using Google Fonts:**

```html
<link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet">
```

```css
body {
  font-family: "Poppins", sans-serif;
}
```

**Shorthand:** `font: style weight size/line-height family;`

```css
p {
  font: italic bold 16px/1.5 Arial, sans-serif;
}
```

---

## 9. Units (px, %, em, rem, vh, vw)

| Unit | Meaning | Type |
|------|---------|------|
| `px` | Pixels, a fixed size | Absolute |
| `%` | Percentage of the parent element | Relative |
| `em` | Relative to the **parent's** font size | Relative |
| `rem` | Relative to the **root (html)** font size | Relative |
| `vh` | 1% of the viewport **height** | Relative |
| `vw` | 1% of the viewport **width** | Relative |

```css
html { font-size: 16px; }

.box1 { width: 300px; }        /* always 300 pixels */
.box2 { width: 50%; }          /* half of the parent's width */
.box3 { font-size: 2em; }      /* 2 x parent font size */
.box4 { font-size: 2rem; }     /* 2 x 16px = 32px */
.box5 { height: 100vh; }       /* full screen height */
.box6 { width: 100vw; }        /* full screen width */
```

💡 **Tip:** Use `rem` for font sizes and spacing, `%` / `vw` / `vh` for flexible layouts.

---

# Phase 2: CSS Box Model

Every HTML element is a rectangular **box**. From inside to outside:

```
┌──────────────────────────────┐
│           MARGIN             │
│   ┌──────────────────────┐   │
│   │        BORDER        │   │
│   │   ┌──────────────┐   │   │
│   │   │   PADDING    │   │   │
│   │   │  ┌────────┐  │   │   │
│   │   │  │CONTENT │  │   │   │
│   │   │  └────────┘  │   │   │
│   │   └──────────────┘   │   │
│   └──────────────────────┘   │
└──────────────────────────────┘
```

## 1. Content

The actual text, image or element inside the box. Its size is set with `width` and `height`.

## 2. Padding

Space **inside** the border, between the content and the border.

```css
.box {
  padding: 20px;                  /* all 4 sides */
  padding: 10px 20px;             /* top-bottom, left-right */
  padding: 10px 20px 30px 40px;   /* top, right, bottom, left (clockwise) */
  padding-left: 15px;             /* one side only */
}
```

## 3. Border

A line around the padding and content.

```css
.box {
  border: 2px solid black;        /* width style color */
  border-style: dashed;           /* solid, dashed, dotted, double */
  border-bottom: 3px solid red;   /* one side only */
}
```

## 4. Margin

Space **outside** the border, between this box and other boxes.

```css
.box {
  margin: 20px;
  margin: 10px 20px;
  margin-top: 30px;
  margin: 0 auto;     /* centers a block element horizontally (needs a width) */
}
```

## 5. Width and Height

```css
.box {
  width: 300px;
  height: 200px;
  max-width: 100%;     /* never wider than this */
  min-height: 100px;   /* never shorter than this */
}
```

## 6. Box-sizing

By default (`content-box`), padding and border are **added** to the width, so a `300px` box with `20px` padding becomes `340px` wide. This is confusing.

`border-box` includes padding and border **inside** the width, so the box stays `300px`.

```css
/* Recommended: put this at the top of every project */
* {
  box-sizing: border-box;
}

.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  /* total width is still 300px */
}
```

## 7. Border-radius

Rounds corners.

```css
.card   { border-radius: 10px; }        /* soft corners */
.circle { border-radius: 50%; width: 100px; height: 100px; }  /* circle */
.pill   { border-radius: 50px; }        /* pill-shaped button */
.custom { border-radius: 10px 20px 30px 40px; }  /* each corner */
```

## 8. Box-shadow

Adds a shadow around a box.

Syntax: `box-shadow: x-offset y-offset blur spread color;`

```css
.card {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.inner-shadow {
  box-shadow: inset 0 0 10px gray;
}
```

### ✅ Full Box Model Example

```html
<div class="card">Hello Box Model</div>
```

```css
* { box-sizing: border-box; }

.card {
  width: 300px;
  padding: 20px;
  border: 2px solid #333;
  margin: 30px auto;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  background-color: #fff;
}
```

---

# Phase 3: CSS Layout

## 1. Display Properties

`display` controls how an element behaves in the page flow.

### Block
Starts on a **new line** and takes the **full width**. Width and height work. (Examples: `div`, `p`, `h1`)

```css
span { display: block; }
```

### Inline
Stays **in the same line**. Width, height and top/bottom margin **do not** work. (Examples: `span`, `a`)

```css
div { display: inline; }
```

### Inline-block
Stays in the same line **but** also allows width, height and margin.

```css
.box {
  display: inline-block;
  width: 100px;
  height: 100px;
  background: coral;
}
```

### None
Hides the element completely (it takes no space).

```css
.hidden { display: none; }
```

> `visibility: hidden;` also hides the element but it **still takes space**.

---

## 2. Position

Controls where an element is placed. Use `top`, `right`, `bottom`, `left` to move positioned elements.

### Static (default)
Normal flow. `top/left` have no effect.

```css
.box { position: static; }
```

### Relative
Positioned relative to **its own original place**. It still keeps its original space.

```css
.box {
  position: relative;
  top: 20px;
  left: 30px;
}
```

### Absolute
Positioned relative to the **nearest positioned parent** (one that is not `static`). It is removed from the normal flow.

```html
<div class="parent">
  <div class="child">I am inside the corner</div>
</div>
```

```css
.parent {
  position: relative;    /* the reference point */
  width: 300px;
  height: 200px;
  background: lightgray;
}

.child {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

### Fixed
Positioned relative to the **browser window**. It stays in place while scrolling (for example a sticky chat button).

```css
.chat-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

### Sticky
Behaves like `relative` until you scroll to a point, then **sticks** like `fixed`.

```css
.navbar {
  position: sticky;
  top: 0;
  background: white;
}
```

---

## 3. Overflow

Controls what happens when content is **bigger than its box**.

```css
.box {
  width: 200px;
  height: 100px;
  overflow: visible;   /* default: content spills outside */
  overflow: hidden;    /* extra content is cut off */
  overflow: scroll;    /* always show scrollbars */
  overflow: auto;      /* scrollbar only if needed (most useful) */
  overflow-x: auto;    /* horizontal only */
}
```

---

## 4. Z-index

Controls which element appears **on top** when elements overlap. A higher number is on top. It works only on positioned elements (not `static`).

```css
.box1 {
  position: absolute;
  z-index: 1;
  background: red;
}

.box2 {
  position: absolute;
  z-index: 2;       /* box2 is above box1 */
  background: blue;
}
```

---

## 5. Float and Clear

`float` pushes an element to the left or right so text wraps around it. It was used for layouts in the past; today **Flexbox and Grid** are used instead, but float is still good for wrapping text around images.

```html
<img src="photo.jpg" class="photo">
<p>This text wraps around the image...</p>
```

```css
.photo {
  float: left;
  margin-right: 15px;
  width: 150px;
}
```

`clear` stops an element from sitting next to a floated element.

```css
.footer {
  clear: both;     /* left, right, both */
}
```

**Clearfix** (fixes a parent collapsing when all children are floated):

```css
.container::after {
  content: "";
  display: block;
  clear: both;
}
```

---

# Phase 4: Flexbox

## 1. What is Flexbox?

Flexbox is a **one-dimensional** layout system (a row **or** a column). It makes aligning, spacing and centering items very easy.

- The parent is the **flex container**.
- The children are **flex items**.

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;      /* this turns on Flexbox */
}

.item {
  background: skyblue;
  padding: 20px;
  margin: 5px;
}
```

The items now sit side by side in a row.

**Two axes:**
- **Main axis**: the direction of the items (row by default)
- **Cross axis**: perpendicular to the main axis

---

## 2. Flex-direction

Sets the main axis direction.

```css
.container {
  display: flex;
  flex-direction: row;              /* default: left to right */
  flex-direction: row-reverse;      /* right to left */
  flex-direction: column;           /* top to bottom */
  flex-direction: column-reverse;   /* bottom to top */
}
```

---

## 3. Justify-content

Aligns items along the **main axis**.

```css
.container {
  display: flex;
  justify-content: flex-start;     /* default: at the start */
  justify-content: center;         /* in the middle */
  justify-content: flex-end;       /* at the end */
  justify-content: space-between;  /* equal space between, none at edges */
  justify-content: space-around;   /* equal space around each item */
  justify-content: space-evenly;   /* perfectly equal spaces */
}
```

---

## 4. Align-items

Aligns items along the **cross axis**.

```css
.container {
  display: flex;
  height: 300px;
  align-items: stretch;      /* default: fill the height */
  align-items: flex-start;   /* top */
  align-items: center;       /* middle */
  align-items: flex-end;     /* bottom */
  align-items: baseline;     /* align text baselines */
}
```

### 🎯 Perfect centering (most famous Flexbox trick)

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

---

## 5. Flex-wrap

By default, all items try to fit in **one line**. `flex-wrap` lets them move to the next line.

```css
.container {
  display: flex;
  flex-wrap: nowrap;        /* default: one line */
  flex-wrap: wrap;          /* wrap to the next line */
  flex-wrap: wrap-reverse;
}

.item {
  width: 200px;
}
```

---

## 6. Gap

Adds space **between** flex items (no more margin hacks).

```css
.container {
  display: flex;
  gap: 20px;               /* row and column gap */
  gap: 10px 30px;          /* row-gap column-gap */
}
```

---

## 7. Align-content

Aligns **multiple lines** of items along the cross axis. It works only when `flex-wrap: wrap` is used and there is more than one line.

```css
.container {
  display: flex;
  flex-wrap: wrap;
  height: 500px;
  align-content: flex-start;     /* center, flex-end, space-between, space-around */
}
```

> **Difference:** `align-items` aligns items inside each line. `align-content` aligns the lines themselves.

---

## 8. Flex-grow and Flex-shrink

### flex-grow
How much an item **grows** to fill extra space. Default is `0` (does not grow).

```css
.item1 { flex-grow: 1; }
.item2 { flex-grow: 2; }   /* takes twice as much extra space as item1 */
```

### flex-shrink
How much an item **shrinks** when there is not enough space. Default is `1`. Use `0` to stop shrinking.

```css
.item { flex-shrink: 0; }
```

### flex-basis
The starting size of an item before growing or shrinking.

### Shorthand: `flex: grow shrink basis;`

```css
.item {
  flex: 1;              /* equal width for all items */
  flex: 1 1 200px;      /* grow, shrink, start at 200px */
}
```

### ✅ Flexbox Navbar Example

```html
<nav class="navbar">
  <div class="logo">MySite</div>
  <ul class="menu">
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
  </ul>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background: #222;
  color: white;
}

.menu {
  display: flex;
  gap: 20px;
  list-style: none;
}
```

---

# Phase 5: CSS Grid

Flexbox is **one-dimensional**. Grid is **two-dimensional** (rows **and** columns at the same time). It is perfect for full page layouts and galleries.

## 1. Grid Container

Turn on Grid with `display: grid`. The parent is the **grid container** and the children are **grid items**.

```html
<div class="grid">
  <div>1</div><div>2</div><div>3</div>
  <div>4</div><div>5</div><div>6</div>
</div>
```

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.grid div {
  background: lightgreen;
  padding: 20px;
  text-align: center;
}
```

---

## 2. Grid Columns

`grid-template-columns` defines the columns.

```css
.grid {
  display: grid;
  grid-template-columns: 200px 200px 200px;   /* 3 fixed columns */
  grid-template-columns: 1fr 2fr 1fr;         /* flexible: middle is twice as wide */
  grid-template-columns: repeat(3, 1fr);      /* same as 1fr 1fr 1fr */
  grid-template-columns: 250px 1fr;           /* sidebar + main content */
}
```

`fr` means a **fraction** of the available space.

**Auto-responsive columns (no media query needed):**

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

---

## 3. Grid Rows

`grid-template-rows` defines the row heights.

```css
.grid {
  display: grid;
  grid-template-rows: 100px 200px 100px;
  grid-auto-rows: 150px;     /* height of any extra rows */
}
```

**Spanning cells:**

```css
.item1 {
  grid-column: 1 / 3;   /* from line 1 to line 3 (spans 2 columns) */
  grid-row: 1 / 3;      /* spans 2 rows */
}

.item2 {
  grid-column: span 2;  /* span 2 columns */
}
```

---

## 4. Grid Gap

Space between rows and columns.

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;               /* both */
  row-gap: 10px;           /* rows only */
  column-gap: 30px;        /* columns only */
}
```

---

## 5. Grid-template-areas

Name parts of your layout and place them visually. It reads like a drawing of your page.

```html
<div class="page">
  <header>Header</header>
  <aside>Sidebar</aside>
  <main>Main</main>
  <footer>Footer</footer>
</div>
```

```css
.page {
  display: grid;
  grid-template-columns: 200px 1fr;
  grid-template-rows: 80px 1fr 60px;
  grid-template-areas:
    "header  header"
    "sidebar main"
    "footer  footer";
  height: 100vh;
  gap: 10px;
}

header { grid-area: header; background: #ffb3b3; }
aside  { grid-area: sidebar; background: #b3d9ff; }
main   { grid-area: main;   background: #c6f5c6; }
footer { grid-area: footer; background: #ffe6b3; }
```

---

## 6. Grid Alignment

### Aligning all items inside their cells

```css
.grid {
  justify-items: center;    /* horizontal: start, end, center, stretch */
  align-items: center;      /* vertical:   start, end, center, stretch */
  place-items: center;      /* shorthand for both */
}
```

### Aligning the whole grid inside the container

```css
.grid {
  justify-content: center;         /* start, end, center, space-between, space-around */
  align-content: center;
}
```

### Aligning one single item

```css
.item {
  justify-self: end;
  align-self: center;
}
```

> **When to use which?** Use **Flexbox** for components (navbars, buttons, cards in a row). Use **Grid** for page layouts and galleries. They also work great together.

---

# Phase 6: Responsive Web Design

Responsive design makes your website look good on **all screen sizes**: phone, tablet and desktop.

**First, always add this in your HTML `<head>`:**

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## 1. Media Queries

Apply CSS only when a condition is true (usually screen width).

```css
/* Default style */
.container {
  background: lightblue;
}

/* When the screen is 768px wide or smaller */
@media (max-width: 768px) {
  .container {
    background: lightcoral;
  }
}
```

Other useful conditions:

```css
@media (min-width: 1024px) { ... }                       /* large screens */
@media (min-width: 600px) and (max-width: 900px) { ... } /* a range */
@media (orientation: landscape) { ... }
@media (prefers-color-scheme: dark) { ... }              /* dark mode */
```

---

## 2. Mobile-first Design

Design for **small screens first**, then add styles for larger screens using `min-width`. This is the modern best practice.

```css
/* Mobile (default): 1 column */
.cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}

/* Tablet: 2 columns */
@media (min-width: 768px) {
  .cards {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Desktop: 4 columns */
@media (min-width: 1024px) {
  .cards {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

---

## 3. Responsive Units

Use flexible units instead of fixed pixels.

```css
.container {
  width: 90%;                          /* flexible width */
  max-width: 1200px;                   /* but never too wide */
  margin: 0 auto;
}

h1 {
  font-size: 5vw;                      /* scales with screen width */
  font-size: clamp(1.5rem, 4vw, 3rem); /* min, preferred, max */
}

.hero {
  height: 100vh;
}
```

---

## 4. Responsive Images

Make images shrink to fit their container.

```css
img {
  max-width: 100%;
  height: auto;
}
```

**Cover a box without stretching:**

```css
.thumb {
  width: 100%;
  height: 250px;
  object-fit: cover;    /* cover, contain, fill */
}
```

**Different images for different screens:**

```html
<picture>
  <source media="(min-width: 800px)" srcset="large.jpg">
  <source media="(min-width: 400px)" srcset="medium.jpg">
  <img src="small.jpg" alt="Responsive image">
</picture>
```

---

## 5. Breakpoints

Breakpoints are the screen widths where your layout changes. Common choices:

| Device | Width |
|--------|-------|
| Mobile | up to 480px (default styles) |
| Large phone / small tablet | 600px |
| Tablet | 768px |
| Laptop | 1024px |
| Desktop | 1200px and above |

```css
/* mobile-first breakpoints */
@media (min-width: 600px)  { /* large phones */ }
@media (min-width: 768px)  { /* tablets */ }
@media (min-width: 1024px) { /* laptops */ }
@media (min-width: 1200px) { /* desktops */ }
```

💡 **Tip:** Pick breakpoints where *your design breaks*, not just by device names.

---

# Phase 7: Advanced CSS

## 1. Pseudo-classes

A pseudo-class styles an element in a **special state**. It uses a single colon `:`.

```css
a:hover        { color: red; }              /* mouse is over */
button:active  { transform: scale(0.95); }  /* being clicked */
input:focus    { border-color: blue; outline: none; }
a:visited      { color: purple; }

li:first-child { font-weight: bold; }
li:last-child  { border-bottom: none; }
li:nth-child(2) { color: red; }             /* second item */
li:nth-child(odd)  { background: #f2f2f2; } /* striped list */
li:nth-child(even) { background: white; }

input:disabled { background: #ddd; }
input:checked + label { color: green; }
p:not(.special) { color: gray; }
```

Example: a button with hover.

```css
.btn {
  background: royalblue;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}

.btn:hover {
  background: darkblue;
}
```

---

## 2. Pseudo-elements

A pseudo-element styles a **part** of an element, or adds extra content. It uses a double colon `::`.

```css
p::first-letter {
  font-size: 2.5rem;       /* drop cap */
  color: crimson;
}

p::first-line {
  font-weight: bold;
}

::selection {
  background: yellow;      /* highlighted text color */
}

/* ::before and ::after add content (needs the content property) */
.required::after {
  content: " *";
  color: red;
}

.quote::before {
  content: "“";
  font-size: 2rem;
}
```

Decorative underline example:

```css
h2::after {
  content: "";
  display: block;
  width: 60px;
  height: 4px;
  background: orange;
  margin-top: 8px;
}
```

---

## 3. CSS Transitions

Make changes happen **smoothly** instead of instantly.

Syntax: `transition: property duration timing-function delay;`

```css
.btn {
  background: tomato;
  transition: background 0.3s ease;
}

.btn:hover {
  background: darkred;
}
```

Transition several properties:

```css
.card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.25);
}
```

Timing functions: `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`.

---

## 4. CSS Transform

Move, rotate, scale or skew an element without affecting the layout.

```css
.box {
  transform: translate(50px, 20px);   /* move right 50px, down 20px */
  transform: translateX(100px);
  transform: rotate(45deg);
  transform: scale(1.5);              /* 1.5 times bigger */
  transform: skew(20deg);
  transform: rotate(10deg) scale(1.2);  /* combine them */
}

.box {
  transform-origin: top left;         /* the point of rotation/scaling */
}
```

Hover zoom on an image:

```css
.gallery img {
  transition: transform 0.4s;
}

.gallery img:hover {
  transform: scale(1.1);
}
```

---

## 5. CSS Animations

Animations run automatically and can have many steps, using `@keyframes`.

```css
/* Step 1: define the animation */
@keyframes bounce {
  0%   { transform: translateY(0); }
  50%  { transform: translateY(-30px); }
  100% { transform: translateY(0); }
}

/* Step 2: apply it */
.ball {
  width: 50px;
  height: 50px;
  background: orange;
  border-radius: 50%;
  animation: bounce 1s ease-in-out infinite;
}
```

Animation properties:

```css
.box {
  animation-name: bounce;
  animation-duration: 2s;
  animation-timing-function: ease;
  animation-delay: 0.5s;
  animation-iteration-count: infinite;   /* or a number like 3 */
  animation-direction: alternate;        /* normal, reverse, alternate */
  animation-fill-mode: forwards;         /* keep the final state */
}
```

Fade-in example:

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

.hero {
  animation: fadeIn 1.5s ease;
}
```

Loading spinner:

```css
@keyframes spin {
  to { transform: rotate(360deg); }
}

.spinner {
  width: 40px;
  height: 40px;
  border: 5px solid #ddd;
  border-top-color: royalblue;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}
```

---

## 6. CSS Variables

Also called **custom properties**. Store a value once and reuse it everywhere. Change it in one place and the whole site updates.

```css
:root {
  --primary-color: #4f46e5;
  --secondary-color: #f59e0b;
  --radius: 8px;
  --spacing: 16px;
}

.btn {
  background: var(--primary-color);
  border-radius: var(--radius);
  padding: var(--spacing);
}

h1 {
  color: var(--primary-color);
}

/* fallback value if the variable is missing */
p {
  color: var(--text-color, black);
}
```

**Easy dark mode with variables:**

```css
:root {
  --bg: white;
  --text: black;
}

body.dark {
  --bg: #121212;
  --text: white;
}

body {
  background: var(--bg);
  color: var(--text);
}
```

---

## 7. Specificity

When two rules target the same element, **specificity** decides which one wins. Think of it as a score:

| Selector type | Score |
|---------------|-------|
| Inline style | 1000 |
| ID (`#id`) | 100 |
| Class, attribute, pseudo-class (`.class`, `[type]`, `:hover`) | 10 |
| Element, pseudo-element (`p`, `::before`) | 1 |

```html
<p id="intro" class="text">Hello</p>
```

```css
p        { color: blue; }    /* score: 1   */
.text    { color: green; }   /* score: 10  */
#intro   { color: red; }     /* score: 100 ← wins, the text is red */
```

**Rules to remember:**
- Higher specificity wins.
- If the score is equal, the **later** rule in the file wins.
- `!important` beats everything, but **avoid it** because it makes code hard to fix.

```css
p { color: orange !important; }  /* avoid this if possible */
```

💡 **Best practice:** use classes for styling, avoid IDs and `!important`.

---

## 8. Inheritance

Some CSS properties are passed down from a parent to its children automatically.

**Inherited by default:** `color`, `font-family`, `font-size`, `line-height`, `text-align`
**Not inherited:** `margin`, `padding`, `border`, `background`, `width`

```html
<div class="parent">
  <p>I get the parent's color and font.</p>
</div>
```

```css
.parent {
  color: darkgreen;
  font-family: Arial;
  border: 2px solid black;   /* NOT inherited by the p */
}
```

Control inheritance manually:

```css
.child {
  border: inherit;      /* force inheriting from the parent */
  color: initial;       /* reset to the browser default */
  color: unset;         /* inherit if naturally inherited, else initial */
}
```

💡 Setting `font-family` and `color` once on `body` styles the whole page.

---

# Phase 8: CSS Projects

Projects are where real learning happens. Build each one yourself, then improve it.

## 🟢 Beginner

### 1. Personal Profile Card
**Goal:** A centered card with a photo, name, job title, short bio and social links.
**Skills used:** box model, border-radius, box-shadow, text properties, Flexbox centering.
**Challenges:** add a hover lift effect with `transition` and `transform`.

**Starter:**
```html
<div class="card">
  <img src="me.jpg" alt="Profile" class="avatar">
  <h2>Your Name</h2>
  <p class="job">Web Developer</p>
  <p>I love building websites.</p>
  <a href="#" class="btn">Contact Me</a>
</div>
```

```css
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #eef2f7;
  font-family: Arial, sans-serif;
}

.card {
  width: 300px;
  padding: 30px;
  text-align: center;
  background: white;
  border-radius: 16px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s;
}

.card:hover { transform: translateY(-8px); }

.avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
}

.job { color: gray; }

.btn {
  display: inline-block;
  margin-top: 15px;
  padding: 10px 24px;
  background: royalblue;
  color: white;
  text-decoration: none;
  border-radius: 25px;
}
```

### 2. Simple Login Page
**Goal:** A centered login form with email, password and a button.
**Skills used:** forms, padding, focus states, Flexbox.
**Challenges:** style `input:focus`, add a "Forgot password?" link, add a gradient background.

**Starter idea:**
```html
<form class="login">
  <h2>Login</h2>
  <input type="email" placeholder="Email">
  <input type="password" placeholder="Password">
  <button type="submit">Login</button>
</form>
```

```css
.login {
  width: 320px;
  margin: 100px auto;
  padding: 30px;
  display: flex;
  flex-direction: column;
  gap: 15px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.login input {
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
}

.login input:focus {
  outline: none;
  border-color: royalblue;
}

.login button {
  padding: 12px;
  background: royalblue;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}
```

### 3. Registration Form
**Goal:** A form with name, email, password, confirm password, gender (radio), country (select), terms (checkbox) and a submit button.
**Skills used:** form styling, Grid for two-column fields, pseudo-classes.
**Challenges:** style `:required`, `:valid` and `:invalid` states; use Grid to put first name and last name side by side.

---

## 🟡 Intermediate

### 4. Responsive Navbar
**Goal:** A navbar with logo and links that turns into a **hamburger menu** on mobile.
**Skills used:** Flexbox, media queries, `position`, transitions.
**Steps:**
1. Build the desktop navbar with `display: flex; justify-content: space-between;`.
2. Hide the links on small screens with a media query.
3. Show a hamburger icon (☰) on mobile.
4. Toggle the menu (with a small bit of JavaScript or the checkbox hack).

```css
.menu { display: flex; gap: 20px; }
.hamburger { display: none; }

@media (max-width: 768px) {
  .menu {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 60px;
    left: 0;
    width: 100%;
    background: #222;
  }
  .menu.open { display: flex; }
  .hamburger { display: block; }
}
```

### 5. Pricing Table
**Goal:** Three pricing cards (Basic, Pro, Premium) with the middle one highlighted.
**Skills used:** Flexbox or Grid, box-shadow, hover effects, `transform: scale()`.
**Challenges:** add a "Most Popular" badge using `position: absolute`; stack the cards on mobile.

```css
.pricing {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  padding: 40px;
}

.plan {
  padding: 30px;
  text-align: center;
  border: 1px solid #ddd;
  border-radius: 12px;
  transition: transform 0.3s;
}

.plan:hover { transform: scale(1.05); }
.plan.featured { border-color: royalblue; box-shadow: 0 8px 20px rgba(0,0,0,0.2); }
```

### 6. Product Landing Page
**Goal:** A full page with Hero section, Features, Testimonials, Call-to-action and Footer.
**Skills used:** Grid, Flexbox, backgrounds, gradients, responsive design, animations.
**Sections to build:**
1. Navbar
2. Hero (big heading, subtitle, button, image)
3. Features (3 icon cards)
4. Testimonials
5. Call-to-action
6. Footer

---

## 🔴 Advanced

### 7. Portfolio Website
**Goal:** A complete personal website to show to employers.
**Pages / sections:** Home, About, Skills, Projects, Contact.
**Skills used:** everything: CSS variables, Grid, Flexbox, animations, responsive design, hover effects, dark mode.
**Challenges:**
- Add a dark/light theme toggle using CSS variables.
- Add scroll animations.
- Make it fully responsive.
- Deploy it free on **GitHub Pages** or **Netlify**.

### 8. Responsive Dashboard
**Goal:** An admin dashboard with a sidebar, top bar, stat cards, charts area and a table.
**Skills used:** Grid layout with `grid-template-areas`, Flexbox, sticky sidebar, media queries.
**Layout idea:**

```css
.dashboard {
  display: grid;
  grid-template-columns: 240px 1fr;
  grid-template-areas:
    "sidebar header"
    "sidebar main";
  min-height: 100vh;
}

.sidebar { grid-area: sidebar; background: #1e293b; color: white; }
.header  { grid-area: header; padding: 15px; background: white; }
.main    { grid-area: main; padding: 20px; background: #f1f5f9; }

.stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

@media (max-width: 768px) {
  .dashboard {
    grid-template-columns: 1fr;
    grid-template-areas:
      "header"
      "main";
  }
  .sidebar { display: none; }
}
```

---

# Study Tips

1. **Code every example yourself.** Do not just read. Type it and change values to see what happens.
2. **Use DevTools.** Right-click a page, choose **Inspect**, and edit CSS live in the browser.
3. **Practice daily**, even 30 to 60 minutes.
4. **Rebuild real websites.** Pick a simple page and try to copy its design.
5. **Learn in order.** Do not skip the Box Model; Flexbox and Grid depend on it.
6. **Play games to learn layouts:**
   - [Flexbox Froggy](https://flexboxfroggy.com)
   - [Grid Garden](https://cssgridgarden.com)
7. **Reference documentation:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS)

## ✅ Progress Checklist

- [ ] Phase 1: CSS Fundamentals
- [ ] Phase 2: Box Model
- [ ] Phase 3: Layout
- [ ] Phase 4: Flexbox
- [ ] Phase 5: Grid
- [ ] Phase 6: Responsive Design
- [ ] Phase 7: Advanced CSS
- [ ] Phase 8: Projects (all 8 built)

## 🚀 What to Learn After CSS

1. **JavaScript** (make pages interactive)
2. **Git and GitHub** (save and share your code)
3. **CSS frameworks** (Tailwind CSS, Bootstrap)
4. **Sass / SCSS** (CSS with superpowers)
5. **React** (build modern web apps)

---

**Happy Coding! 🎉** Keep practicing, and build something every week.
