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
- [Bonus: More Examples for Every Topic](#-bonus-more-examples-for-every-topic)
- [Practice Challenges](#️-practice-challenges-try-without-looking)
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


---

# 🧪 Bonus: More Examples for Every Topic

Extra practice examples for **every topic** in the roadmap. Each one is small and complete, so you can paste it into a file and see the result.

---

## Phase 1: More Fundamentals Examples

### What is CSS? (before and after)

```html
<h1>My Website</h1>
<p>Welcome to my page.</p>
```

```css
/* Without CSS, it looks plain. With CSS: */
h1 { color: teal; text-align: center; font-size: 48px; }
p  { color: #555; text-align: center; font-size: 20px; }
```

### Types of CSS: same style, three ways

```html
<!-- 1. Inline -->
<h2 style="color: tomato;">Inline heading</h2>

<!-- 2. Internal -->
<style>
  h3 { color: seagreen; }
</style>
<h3>Internal heading</h3>

<!-- 3. External -->
<link rel="stylesheet" href="style.css">
<h4>External heading</h4>
```

```css
/* style.css */
h4 { color: royalblue; }
```

**Priority when they conflict:** Inline > Internal/External (the one written later wins).

### CSS Syntax: many declarations

```css
button {
  background-color: #4caf50;
  color: white;
  padding: 12px 24px;
  border: none;
  font-size: 16px;
  cursor: pointer;
}
```

### CSS Selectors: a complete practice page

```html
<div class="box">
  <h2 id="title">Selectors</h2>
  <p class="note">Note one</p>
  <p class="note special">Note two</p>
  <a href="#">A link</a>
  <input type="text" placeholder="Type here">
</div>
```

```css
.box        { border: 2px solid #333; padding: 20px; }   /* class */
#title      { color: crimson; }                            /* id */
.note       { color: gray; }                               /* class */
.note.special { font-weight: bold; }                       /* two classes together */
.box > a    { color: green; }                              /* direct child */
a:hover     { color: orange; }                             /* pseudo-class */
input[type="text"] { padding: 8px; border: 1px solid blue; } /* attribute */
h2 + p      { margin-top: 0; }                             /* adjacent sibling */
h2 ~ p      { font-size: 18px; }                           /* all following siblings */
```

### Colors: a color palette

```html
<div class="swatch name">red</div>
<div class="swatch hex">#00a86b</div>
<div class="swatch rgb">rgb(30,144,255)</div>
<div class="swatch rgba">rgba(255,0,0,0.4)</div>
<div class="swatch hsl">hsl(280,70%,50%)</div>
```

```css
.swatch { display: inline-block; width: 120px; padding: 20px; color: white; margin: 5px; text-align: center; }
.name { background: red; }
.hex  { background: #00a86b; }
.rgb  { background: rgb(30, 144, 255); }
.rgba { background: rgba(255, 0, 0, 0.4); }
.hsl  { background: hsl(280, 70%, 50%); }
```

### Backgrounds: hero section with overlay

```html
<section class="hero"><h1>Travel the World</h1></section>
```

```css
.hero {
  height: 60vh;
  background:
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),  /* dark overlay */
    url("travel.jpg") center / cover no-repeat;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

More gradients:

```css
.g1 { background: linear-gradient(45deg, #ff512f, #dd2476); }
.g2 { background: radial-gradient(circle, #fff, #4facfe); }
.g3 { background: linear-gradient(to bottom, #0f2027, #203a43, #2c5364); }
```

### Text properties: styled article

```css
.article h1 {
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 3px;
  text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
}

.article p {
  line-height: 1.8;
  text-align: justify;
  text-indent: 2rem;
}

.article a {
  text-decoration: none;
  border-bottom: 2px dotted blue;
}

.truncate {                       /* cut long text with ... */
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  width: 200px;
}
```

### Fonts: heading and body fonts

```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Roboto&display=swap" rel="stylesheet">
```

```css
h1, h2 { font-family: "Playfair Display", serif; font-weight: 700; }
body   { font-family: "Roboto", sans-serif; font-size: 1rem; }
code   { font-family: "Courier New", monospace; background: #eee; padding: 2px 6px; }
.small-caps { font-variant: small-caps; }
```

### Units: compare them side by side

```css
html { font-size: 16px; }

.px   { font-size: 24px; }          /* 24px */
.rem  { font-size: 1.5rem; }        /* 1.5 x 16 = 24px */
.em-parent { font-size: 20px; }
.em-parent .em-child { font-size: 1.5em; }  /* 1.5 x 20 = 30px */

.half  { width: 50%; }
.full-screen { height: 100vh; width: 100vw; }
.banner { height: 30vh; }           /* 30% of screen height */
```

---

## Phase 2: More Box Model Examples

### Content, width and height

```css
.image-box { width: 250px; height: 150px; background: lightblue; }
.flexible  { width: 100%; max-width: 600px; min-height: 100px; }
```

### Padding: button sizes

```css
.btn-small  { padding: 5px 10px; }
.btn-medium { padding: 10px 20px; }
.btn-large  { padding: 15px 40px; }
.input      { padding: 12px 16px; }
```

### Border: different styles

```css
.b1 { border: 3px solid black; }
.b2 { border: 3px dashed red; }
.b3 { border: 3px dotted blue; }
.b4 { border: 6px double green; }
.b5 { border-left: 5px solid orange; padding-left: 15px; }   /* quote style */
.b6 { border-bottom: 2px solid #ddd; }                       /* divider */
```

### Margin: spacing and centering

```css
.container { width: 80%; margin: 0 auto; }       /* centered */
.section   { margin-bottom: 40px; }              /* space below */
.negative  { margin-top: -10px; }                /* pull upward */
h1 { margin: 0 0 10px 0; }
```

**Margin collapse:** vertical margins of two blocks merge into the larger one.

```css
.a { margin-bottom: 30px; }
.b { margin-top: 20px; }     /* gap between them is 30px, not 50px */
```

### Box-sizing: before and after

```css
.content-box { box-sizing: content-box; width: 200px; padding: 20px; border: 5px solid; }  /* total: 250px */
.border-box  { box-sizing: border-box;  width: 200px; padding: 20px; border: 5px solid; }  /* total: 200px */
```

### Border-radius: shapes

```css
.square  { width: 100px; height: 100px; border-radius: 0; }
.rounded { width: 100px; height: 100px; border-radius: 15px; }
.circle  { width: 100px; height: 100px; border-radius: 50%; }
.leaf    { width: 100px; height: 100px; border-radius: 0 50px; }
.tab     { border-radius: 10px 10px 0 0; }
```

### Box-shadow: many styles

```css
.soft   { box-shadow: 0 2px 8px rgba(0,0,0,0.15); }
.deep   { box-shadow: 0 15px 35px rgba(0,0,0,0.3); }
.glow   { box-shadow: 0 0 20px rgba(0,150,255,0.8); }
.inset  { box-shadow: inset 0 2px 6px rgba(0,0,0,0.3); }
.layered{ box-shadow: 0 1px 2px rgba(0,0,0,0.2), 0 8px 16px rgba(0,0,0,0.2); }
.hard   { box-shadow: 6px 6px 0 #000; }   /* retro style */
```

---

## Phase 3: More Layout Examples

### Display: block vs inline vs inline-block vs none

```html
<span class="a">Span A</span>
<span class="a">Span B</span>
<div class="b">Div 1</div>
<div class="b">Div 2</div>
<span class="c">Box 1</span>
<span class="c">Box 2</span>
<p class="d">I am hidden</p>
```

```css
.a { background: pink; padding: 10px; }                         /* inline: same line, padding sideways only works well */
.b { background: lightgreen; }                                  /* block: new lines, full width */
.c { display: inline-block; width: 100px; height: 60px; background: skyblue; }  /* inline-block: same line + size */
.d { display: none; }                                           /* gone */
```

Use case: horizontal menu from a list.

```css
nav li { display: inline-block; margin-right: 15px; }
```

### Position: all five in one demo

```css
.static   { position: static; }
.relative { position: relative; top: 10px; left: 20px; }

.card { position: relative; width: 250px; }
.card .badge {                       /* absolute badge in the card corner */
  position: absolute;
  top: -10px;
  right: -10px;
  background: red;
  color: white;
  padding: 5px 10px;
  border-radius: 20px;
}

.back-to-top {                       /* fixed button */
  position: fixed;
  bottom: 20px;
  right: 20px;
}

.table-head {                        /* sticky table header */
  position: sticky;
  top: 0;
  background: white;
}
```

Center something using absolute:

```css
.parent { position: relative; height: 300px; }
.child  {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### Overflow: scrollable areas

```css
.chat-box {                       /* vertical scroll */
  height: 200px;
  overflow-y: auto;
  border: 1px solid #ccc;
}

.table-wrap {                     /* horizontal scroll for wide tables */
  overflow-x: auto;
}

.image-frame {                    /* crop an image */
  width: 200px;
  height: 200px;
  overflow: hidden;
  border-radius: 50%;
}
```

### Z-index: dropdown and modal

```css
.dropdown-menu {
  position: absolute;
  z-index: 100;
}

.overlay {
  position: fixed;
  inset: 0;                       /* top, right, bottom, left = 0 */
  background: rgba(0,0,0,0.6);
  z-index: 1000;
}

.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 30px;
  z-index: 1001;                  /* above the overlay */
}
```

### Float and Clear: image with text and a 2-column layout

```css
.left-img  { float: left;  margin: 0 15px 10px 0; }
.right-img { float: right; margin: 0 0 10px 15px; }

.col-left  { float: left;  width: 30%; }
.col-right { float: right; width: 70%; }
.footer    { clear: both; }
```

---

## Phase 4: More Flexbox Examples

### What is Flexbox? Equal boxes

```css
.row { display: flex; }
.row > div { flex: 1; padding: 20px; border: 1px solid #333; }
```

### Flex-direction: vertical menu

```css
.sidebar { display: flex; flex-direction: column; gap: 10px; width: 200px; }

.stack-on-mobile { display: flex; flex-direction: row; }
@media (max-width: 600px) {
  .stack-on-mobile { flex-direction: column; }
}
```

### Justify-content: common patterns

```css
.nav      { display: flex; justify-content: space-between; }   /* logo left, links right */
.buttons  { display: flex; justify-content: flex-end; gap: 10px; }  /* buttons at the right */
.centered { display: flex; justify-content: center; }
.steps    { display: flex; justify-content: space-around; }
.even     { display: flex; justify-content: space-evenly; }
```

### Align-items: vertical alignment

```css
.media { display: flex; align-items: center; gap: 15px; }   /* icon + text */
.top   { display: flex; align-items: flex-start; height: 200px; }
.bottom{ display: flex; align-items: flex-end; height: 200px; }
.equal-height-cards { display: flex; align-items: stretch; }
```

### Flex-wrap: card gallery

```css
.gallery { display: flex; flex-wrap: wrap; gap: 20px; }
.gallery .card { flex: 1 1 250px; }     /* each card is at least 250px, then wraps */
```

### Gap: tags list

```css
.tags { display: flex; flex-wrap: wrap; gap: 8px; }
.tag  { padding: 5px 12px; background: #eee; border-radius: 20px; }
```

### Align-content: multiple lines

```css
.wrap-box {
  display: flex;
  flex-wrap: wrap;
  height: 400px;
  align-content: space-between;   /* lines at the top and bottom edges */
}
.wrap-box > div { width: 45%; height: 50px; }
```

### Flex-grow and Flex-shrink: layouts

```css
/* Sidebar fixed, content fills the rest */
.layout { display: flex; }
.sidebar { flex: 0 0 250px; }        /* do not grow, do not shrink, 250px */
.content { flex: 1; }                /* take all remaining space */

/* Search bar: input grows, button stays */
.search { display: flex; }
.search input  { flex: 1; }
.search button { flex-shrink: 0; }

/* Footer pushed to the bottom */
body { display: flex; flex-direction: column; min-height: 100vh; }
main { flex: 1; }
```

Push one item to the far side:

```css
.navbar .login { margin-left: auto; }
```

---

## Phase 5: More Grid Examples

### Grid container: photo gallery

```css
.photos { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
.photos img { width: 100%; height: 200px; object-fit: cover; }
```

### Grid columns: common layouts

```css
.two-col   { display: grid; grid-template-columns: 1fr 1fr; }
.sidebar   { display: grid; grid-template-columns: 250px 1fr; }
.holy-grail{ display: grid; grid-template-columns: 200px 1fr 200px; }
.auto-fill { display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 15px; }
```

### Grid rows: header, content, footer

```css
.app {
  display: grid;
  grid-template-rows: 60px 1fr 40px;
  min-height: 100vh;
}
```

Featured item spanning rows and columns:

```css
.gallery { display: grid; grid-template-columns: repeat(4, 1fr); grid-auto-rows: 150px; gap: 10px; }
.gallery .big { grid-column: span 2; grid-row: span 2; }
```

### Grid gap: spacing options

```css
.tight  { display: grid; grid-template-columns: repeat(3, 1fr); gap: 5px; }
.loose  { display: grid; grid-template-columns: repeat(3, 1fr); gap: 40px; }
.mixed  { display: grid; grid-template-columns: repeat(3, 1fr); row-gap: 10px; column-gap: 50px; }
```

### Grid-template-areas: responsive page

```css
.page {
  display: grid;
  grid-template-areas:
    "header"
    "main"
    "sidebar"
    "footer";
  gap: 10px;
}

@media (min-width: 768px) {
  .page {
    grid-template-columns: 1fr 250px;
    grid-template-areas:
      "header header"
      "main   sidebar"
      "footer footer";
  }
}

.page header  { grid-area: header; }
.page main    { grid-area: main; }
.page aside   { grid-area: sidebar; }
.page footer  { grid-area: footer; }
```

### Grid alignment: centering

```css
.center-one  { display: grid; place-items: center; height: 100vh; }   /* shortest centering trick */
.corner-item { display: grid; }
.corner-item .x { justify-self: end; align-self: end; }
.spread      { display: grid; grid-template-columns: repeat(3, 100px); justify-content: space-between; }
```

---

## Phase 6: More Responsive Examples

### Media queries: hide, show and resize

```css
.desktop-only { display: block; }
.mobile-only  { display: none; }

@media (max-width: 768px) {
  .desktop-only { display: none; }
  .mobile-only  { display: block; }
  h1 { font-size: 1.8rem; }
  .container { padding: 10px; }
}

@media print {
  nav, footer { display: none; }      /* style for printing */
}
```

### Mobile-first: navbar

```css
/* mobile: stacked */
.nav { display: flex; flex-direction: column; }

/* desktop: in a row */
@media (min-width: 768px) {
  .nav { flex-direction: row; justify-content: space-between; }
}
```

### Responsive units: fluid typography and spacing

```css
h1 { font-size: clamp(1.8rem, 5vw, 3.5rem); }
.section { padding: clamp(20px, 5vw, 80px); }
.wrapper { width: min(90%, 1100px); margin-inline: auto; }
.hero { min-height: 80vh; }
```

### Responsive images: card image and background

```css
.card img { width: 100%; height: auto; display: block; }
.avatar   { width: 80px; height: 80px; object-fit: cover; border-radius: 50%; }
.video-wrap { aspect-ratio: 16 / 9; }
.video-wrap iframe { width: 100%; height: 100%; }
```

```html
<img src="small.jpg"
     srcset="small.jpg 480w, medium.jpg 800w, large.jpg 1200w"
     sizes="(max-width: 600px) 480px, (max-width: 1000px) 800px, 1200px"
     alt="Responsive photo">
```

### Breakpoints: one grid, four layouts

```css
.cards { display: grid; gap: 16px; grid-template-columns: 1fr; }

@media (min-width: 600px)  { .cards { grid-template-columns: repeat(2, 1fr); } }
@media (min-width: 900px)  { .cards { grid-template-columns: repeat(3, 1fr); } }
@media (min-width: 1200px) { .cards { grid-template-columns: repeat(4, 1fr); } }
```

---

## Phase 7: More Advanced Examples

### Pseudo-classes: forms, lists and tables

```css
input:focus  { border-color: dodgerblue; box-shadow: 0 0 5px dodgerblue; outline: none; }
input:valid  { border-color: green; }
input:invalid{ border-color: red; }
input:required { border-left: 4px solid orange; }
input::placeholder { color: #aaa; }

tr:nth-child(even) { background: #f9f9f9; }       /* table stripes */
tr:hover           { background: #eef; }
li:not(:last-child){ border-bottom: 1px solid #eee; }
.menu li:first-child { font-weight: bold; }

/* Custom checkbox toggle */
input[type="checkbox"]:checked + label { text-decoration: line-through; color: gray; }
```

### Pseudo-elements: icons, badges, overlays

```css
.link::after { content: " ↗"; }
.price::before { content: "₹"; }

.title::before, .title::after {
  content: "";
  display: inline-block;
  width: 40px;
  height: 2px;
  background: #333;
  vertical-align: middle;
  margin: 0 10px;
}

.image-card { position: relative; }
.image-card::after {                       /* dark overlay on an image */
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.4);
}

p::first-letter { float: left; font-size: 3rem; margin-right: 8px; }
```

### Transitions: buttons, links and menus

```css
.btn {
  background: #333;
  color: white;
  padding: 10px 20px;
  transition: all 0.3s ease;
}
.btn:hover { background: #ff5722; transform: translateY(-2px); }

.link { position: relative; text-decoration: none; }
.link::after {                              /* animated underline */
  content: "";
  position: absolute;
  left: 0; bottom: -3px;
  width: 0; height: 2px;
  background: blue;
  transition: width 0.3s;
}
.link:hover::after { width: 100%; }

.dropdown { opacity: 0; visibility: hidden; transition: opacity 0.3s; }
.menu-item:hover .dropdown { opacity: 1; visibility: visible; }
```

### Transform: cards, icons and flips

```css
.card:hover { transform: translateY(-10px) scale(1.03); }
.icon:hover { transform: rotate(360deg); transition: transform 0.6s; }
.tilt       { transform: rotate(-5deg); }
.mirror     { transform: scaleX(-1); }           /* flip horizontally */

/* Flip card */
.flip { perspective: 1000px; }
.flip-inner { transition: transform 0.6s; transform-style: preserve-3d; }
.flip:hover .flip-inner { transform: rotateY(180deg); }
```

### Animations: pulse, slide, typing and shake

```css
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50%      { transform: scale(1.1); }
}
.heart { animation: pulse 1s infinite; }

@keyframes slideIn {
  from { transform: translateX(-100%); opacity: 0; }
  to   { transform: translateX(0);     opacity: 1; }
}
.panel { animation: slideIn 0.6s ease-out; }

@keyframes shake {
  0%, 100% { transform: translateX(0); }
  25%      { transform: translateX(-8px); }
  75%      { transform: translateX(8px); }
}
.error { animation: shake 0.4s; }

@keyframes typing { from { width: 0; } to { width: 20ch; } }
.type {
  width: 20ch;
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid;
  animation: typing 3s steps(20) forwards;
}

@keyframes gradientMove {
  0%   { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
.rainbow {
  background: linear-gradient(90deg, red, orange, yellow, green, blue);
  background-size: 200% 100%;
  animation: gradientMove 3s linear infinite alternate;
}
```

### CSS Variables: a theme system

```css
:root {
  --primary: #6366f1;
  --primary-dark: #4338ca;
  --text: #1f2937;
  --bg: #ffffff;
  --radius: 10px;
  --shadow: 0 4px 12px rgba(0,0,0,0.1);
  --space: 1rem;
}

.card   { background: var(--bg); color: var(--text); border-radius: var(--radius); box-shadow: var(--shadow); padding: var(--space); }
.btn    { background: var(--primary); border-radius: var(--radius); }
.btn:hover { background: var(--primary-dark); }

/* Dark theme via system setting */
@media (prefers-color-scheme: dark) {
  :root { --text: #f3f4f6; --bg: #111827; }
}

/* Change a variable locally */
.danger { --primary: #dc2626; --primary-dark: #991b1b; }

/* Variables can be used with calc() */
.box { padding: calc(var(--space) * 2); }
```

### Specificity: who wins?

```html
<button id="save" class="btn primary">Save</button>
```

```css
button          { background: gray; }     /* 0-0-1  = 1   */
.btn            { background: blue; }     /* 0-1-0  = 10  */
.btn.primary    { background: green; }    /* 0-2-0  = 20  */
button.btn      { background: orange; }   /* 0-1-1  = 11  */
#save           { background: red; }      /* 1-0-0  = 100  ← wins: red */
```

How to **avoid** specificity wars:

```css
/* Bad */
div#main .content p.text { color: red; }

/* Good: one simple class */
.text { color: red; }
```

### Inheritance: practical use

```css
body { font-family: Arial, sans-serif; color: #333; line-height: 1.6; }   /* everything inherits */

a { color: inherit; text-decoration: none; }     /* links use the parent's color */
button, input { font-family: inherit; }          /* form elements don't inherit fonts by default */

.card { border: 2px solid red; }
.card .inner { border: inherit; }                /* force inheriting a non-inherited property */

.reset { all: unset; }                           /* reset every property */
```

---

## Phase 8: More Project Ideas

Once you finish the 8 main projects, try these extra mini projects.

| Level | Project | Main skills |
|-------|---------|-------------|
| Beginner | Button collection (10 styles) | hover, transition, border-radius |
| Beginner | Image gallery | Grid, hover zoom |
| Beginner | Blog article page | typography, spacing |
| Beginner | Testimonial card | box model, pseudo-elements |
| Intermediate | Animated loading spinners | keyframes, transform |
| Intermediate | Dark/light mode toggle | CSS variables |
| Intermediate | Accordion / FAQ section | transitions, pseudo-classes |
| Intermediate | Weather card UI | Flexbox, gradients |
| Advanced | Netflix-style movie grid | Grid, hover scale, overflow |
| Advanced | E-commerce product page | Grid, responsive design |
| Advanced | Animated hero with parallax | position, background-attachment, animations |
| Advanced | CSS-only drawing (pure CSS art) | border-radius, position, gradients |

### Quick project example: Button collection

```html
<button class="b b-solid">Solid</button>
<button class="b b-outline">Outline</button>
<button class="b b-pill">Pill</button>
<button class="b b-gradient">Gradient</button>
<button class="b b-shadow">3D</button>
```

```css
.b { padding: 12px 28px; font-size: 16px; cursor: pointer; border: none; margin: 8px; transition: 0.3s; }

.b-solid    { background: #2563eb; color: white; border-radius: 6px; }
.b-solid:hover { background: #1d4ed8; }

.b-outline  { background: transparent; color: #2563eb; border: 2px solid #2563eb; border-radius: 6px; }
.b-outline:hover { background: #2563eb; color: white; }

.b-pill     { background: #10b981; color: white; border-radius: 50px; }

.b-gradient { background: linear-gradient(45deg, #f43f5e, #f59e0b); color: white; border-radius: 6px; }
.b-gradient:hover { transform: scale(1.08); }

.b-shadow   { background: #8b5cf6; color: white; border-radius: 6px; box-shadow: 0 5px 0 #6d28d9; }
.b-shadow:active { transform: translateY(5px); box-shadow: none; }
```

### Quick project example: Accordion (FAQ) without JavaScript

```html
<details class="faq">
  <summary>What is CSS?</summary>
  <p>CSS styles your HTML pages.</p>
</details>
<details class="faq">
  <summary>Is CSS hard?</summary>
  <p>Not if you practice every day!</p>
</details>
```

```css
.faq { border: 1px solid #ddd; border-radius: 8px; margin-bottom: 10px; }
.faq summary { padding: 15px; cursor: pointer; font-weight: bold; }
.faq summary:hover { background: #f5f5f5; }
.faq[open] summary { background: #eef2ff; }
.faq p { padding: 0 15px 15px; }
```

---

# ✍️ Practice Challenges (Try Without Looking!)

1. Make a `<div>` 200×200 with a red background, rounded corners and a shadow.
2. Center a box both horizontally and vertically using Flexbox. Then do it again using Grid.
3. Build a 3-column layout that becomes 1 column on mobile.
4. Make a button that changes color and moves up slightly when hovered.
5. Create a loading spinner with `@keyframes`.
6. Make a card with a badge in its top-right corner using `position`.
7. Build a theme with CSS variables, then change the primary color in one place.
8. Style a list so that odd items have a light background using `:nth-child`.
9. Build a page layout with `grid-template-areas`: header, sidebar, main, footer.
10. Write two competing rules and predict which one wins using specificity.