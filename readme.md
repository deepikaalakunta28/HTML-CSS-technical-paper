# Box Model
### Introduction:
The CSS Box Model is a basic and important idea in web design. It explains how web browsers calculate the size and spacing of HTML elements. When developers understand the Box Model, they can create cleaner layouts and avoid common layout problems.
### Structure of the Box Model
```
+-----------------------+
|        Margin         |
|  +-----------------+  |
|  |     Border      |  |
|  |  +-----------+  |  |
|  |  |  Padding  |  |  |
|  |  | +-------+ |  |  |
|  |  | |Content| |  |  |
|  |  | +-------+ |  |  |
|  |  +-----------+  |  |
|  +-----------------+  |
+-----------------------+
```
### Parts of the Box Model
#### Content
- The main area where text, images, or other elements appear
- Its size is controlled by width and height

#### Padding
- The space between the content and the border
- Adds space inside the element

#### Border
- A line surrounding the padding and content
- Has thickness, style, and color

#### Margin
- The space outside the element
- Creates space between elements
- Does not have background color
#### How Size Is Calculated
- total width = content + padding + border + margin
- total height = content + padding + border + margin
# Inline vs Block Elements in HTML
## Block Elements
### What they do:
- Always start on a new line
- Take up the full width available (stretch across the page)
- Can contain inline or other block elements
- Allow width, height, margin, and padding to affect layout normally

### Common block elements:
```
- <div>
- <p>
- <h1> to <h6>
- <ul> and <ol>
- <li>
- <section>
- <header>, <footer>, <nav>
```
### Example:
```
<p>This is a block element.</p>
<div>This is another block element.</div>
```
## Inline Elements
### What they do:
- Do not start a new line
- Only take up as much width as needed
- Cannot contain block elements (normally)
- width and height do not apply the same way
- Only horizontal padding and margin affect layout clearly

### Common inline elements:
```
<span>
<a>
<strong>
<em>
<img>
```
### Example:
```
<span>This is inline</span>
<a>and this is also inline</a>
```
# CSS Positioning: Relative vs Absolute
### Position: Relative
- The element stays in the normal document flow
- You can move it using top, left, right, bottom
- Movement is relative to its original position
#### Example:
```
relative-box {
  position: relative;
  top: 10px;
  left: 20px;
}
```
### Position: Absolute
- The element is removed from the normal flow
- It positions itself based on the nearest positioned ancestor
(an element with position: relative, absolute, or fixed)
- If no positioned parent exists, it positions relative to the page
#### Example:
```
absolute-box {
  position: absolute;
  top: 10px;
  left: 20px;
}
```
# Common CSS Structural Classes
```
.container
.header
.nav
.main / .content
.sidebar
.footer
.wrapper
.row / .column
```
### .container
```
.container {
  max-width: 1200px;
  margin: 0 auto;
}
```
### .header
```
<div class="header"></div>
```
### .nav
```
<nav class="nav"></nav>
```
### .main / .content
```
<div class="main"></div>
```
# Common CSS Styling Classes
These classes are used to style elements quickly and consistently across a webpage.
```
.text-center
.bold
.italic
.primary
.bg-light
.btn
.btn-primary
.padding
.margin
.border
```
### .text-center
```
.text-center {
  text-align: center;
}
```
### .bold
```
.bold {
  font-weight: bold;
}
```
### .italic
```
.italic {
  font-style: italic;
}
```
### Color Styling
#### .primary
```
.primary {
  color: #007bff;
}
```
#### .bg-light
```
.bg-light {
  background-color: #f5f5f5;
}
```
### Button Styling
#### .btn
```
.btn {
  padding: 10px 20px;
  border-radius: 5px;
  display: inline-block;
}
```
# CSS Specificity

CSS **specificity** determines which CSS rule is applied when multiple rules target the same element. The browser chooses the rule with the highest specificity.
---
### Specificity Ranking (Highest → Lowest)
#### Inline styles
   ```html
   <p style="color: red;">
```
#### IDs
```
#title { }
```
#### Classes, attributes, pseudo-classes
```
.box { }
[type="text"] { }
:hover { }
```
#### Elements and pseudo-elements
```
p { }
h1 { }
::before { }
```
#### Example
```
p { color: blue; }          /* 1 */
p.highlight { color: red; } /* 11 */
#main p { color: green; }   /* 101 */
```
# CSS Responsive Queries

CSS **responsive (media) queries** allow web pages to change layout and styling based on screen size, device type, or orientation. They help make websites look good on phones, tablets, and desktops.

## Basic Media Query

```css
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```
#### Common Breakpoints
| Device        | Width      |
| ------------- | ---------- |
| Mobile        | 0–600px    |
| Tablet        | 600–900px  |
| Small Desktop | 900–1200px |
| Large Desktop | 1200px+    |

### Examples
#### Mobile Style
```
@media (max-width: 600px) {
  .container {
    padding: 10px;
  }
}
```
#### Tablet Style
```
@media (min-width: 600px) and (max-width: 900px) {
  .container {
    width: 80%;
  }
}
```
#### Desktop Style
```
@media (min-width: 900px) {
  .container {
    width: 70%;
  }
}
```
# CSS Flexbox & Grid
CSS **Flexbox** and **Grid** are modern layout systems that help create responsive and organized web layouts.
### Common Flexbox Properties
| Property          | Description                      |
| ----------------- | -------------------------------- |
| `display: flex`   | Enables flexbox                  |
| `flex-direction`  | Row or column layout             |
| `justify-content` | Controls spacing on main axis    |
| `align-items`     | Controls alignment on cross axis |
| `flex-wrap`       | Wraps items to next line         |
| `gap`             | Space between items              |

#### Flexbox Example
```
.container {
  display: flex;
  justify-content: space-between;
}
```
#### When to Use Flexbox
- Navigation bars
- Centering elements
- Buttons or icons in a row
- Simple layouts
## CSS Grid
Grid is used for two-dimensional layouts (rows and columns). It is ideal for full page or section structures.
#### Common Grid Properties
| Property                | Description           |
| ----------------------- | --------------------- |
| `display: grid`         | Enables grid          |
| `grid-template-columns` | Defines column layout |
| `grid-template-rows`    | Defines row layout    |
| `gap`                   | Space between items   |
| `grid-column`           | Item column span      |
| `grid-row`              | Item row span         |
### Flexbox vs Grid
| Feature   | Flexbox       | Grid             |
| --------- | ------------- | ---------------- |
| Layout    | 1D            | 2D               |
| Direction | Row OR Column | Rows AND Columns |
| Best for  | Components    | Full layouts     |

# Common Header Meta Tags
Meta tags are placed inside the `<head>` section of an HTML document. They provide information to browsers, search engines, and devices.
### Common Meta Tags
#### Charset (Character Encoding)
```
<meta charset="UTF-8">
```
#### Viewport (Responsive Design)
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
#### Description (SEO)
```
<meta name="description" content="This is a sample website.">
```
#### Keywords (SEO)
```
<meta name="keywords" content="HTML, CSS, Web Design">
```
### Example Full Header
```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Learning HTML and CSS.">
  <meta name="keywords" content="HTML, CSS, Web Development">
  <meta name="author" content="John Doe">
  <meta name="robots" content="index, follow">
</head>
```
## References
- Link: https://developer.mozilla.org/en-US/docs/Web/HTML/Element
- Link: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
- Link: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout








































