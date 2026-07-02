# Web Development Learning Journey

This repository contains everything I've learned while starting my full stack journey. Instead of just writing definitions, I've explained each topic in my own words so anyone new to web development can understand it easily.

---

#  Topics Covered

- HTML Overview
- Semantic HTML Tags
- DOM (Document Object Model)
- Why CSS is Different from HTML
- CSS Selectors
- What Happens When You Open a Website?
  - DNS
  - TCP
  - TLS
  - HTTP
  - Browser Rendering

---

# 1. HTML Overview

- HTML stands for **HyperText Markup Language**.

- It is the language used to create the structure of a webpage.

- Think of HTML as the skeleton of the human body.

- Without HTML, a webpage has no headings, paragraphs, images, buttons, or forms.

Example:

```html
<h1>Hello World</h1>
<p>This is my first webpage.</p>
```

HTML only tells the browser **what each piece of content is**.

It does **not** decide:

- Colors
- Fonts
- Animations
- Layout

That is the job of CSS.

---

# 2. Semantic HTML Tags

Semantic tags describe the meaning of the content.

Instead of telling only how something looks, they explain what the content actually is.

Examples:

| Tag | Meaning |
|------|----------|
| `<header>` | Top section |
| `<nav>` | Navigation links |
| `<main>` | Main content |
| `<section>` | A section of content |
| `<article>` | Independent content |
| `<aside>` | Side content |
| `<footer>` | Bottom section |

Example structure:

```
Page
│
├── Header
│
├── Navigation
│
├── Main
│     ├── Section
│     ├── Article
│     └── Aside
│
└── Footer
```

Benefits:

- Easier to read
- Better for SEO
- Helps screen readers
- Easier for developers

---

# 3. DOM (Document Object Model)

When the browser reads HTML, it converts it into a tree-like structure called the DOM.

The browser doesn't directly work with HTML text.

Instead, it creates objects for every element.

Example HTML:

```html
<body>
    <h1>Hello</h1>
    <p>Learning DOM</p>
</body>
```

DOM Tree:

```
Document
│
└── html
     │
     ├── head
     │
     └── body
           │
           ├── h1
           │    └── "Hello"
           │
           └── p
                └── "Learning DOM"
```

JavaScript changes the DOM to make websites interactive.

Examples:

- Change text
- Hide elements
- Add buttons
- Create new sections
- Remove elements

---

# 4. Why CSS is Different from HTML

HTML and CSS have different jobs.

HTML creates the content.

CSS controls how that content looks.

Imagine building a house.

HTML:

- Walls
- Doors
- Windows
- Rooms

CSS:

- Paint
- Furniture
- Lighting
- Decorations

Without CSS:

```
Heading
Paragraph
Button
Image
```

With CSS:

```
Large Blue Heading

Beautiful paragraph

Rounded button

Centered image
```

Keeping structure and design separate makes websites easier to maintain.

---

# 5. CSS Selectors

Selectors tell CSS **which HTML element should receive the styling**.

Example:

```css
h1{
    color:blue;
}
```

Here,

Every `<h1>` becomes blue.

Common selectors:

### Element Selector

```css
p{
    color:red;
}
```

Targets every paragraph.

---

### Class Selector

```css
.card{
    border:1px solid black;
}
```

Used for multiple elements.

---

### ID Selector

```css
#header{
    background:black;
}
```

Used for one unique element.

---

### Universal Selector

```css
*{
    margin:0;
    padding:0;
}
```

Selects every element.

---

---

# 6. Flexbox

Flexbox is a one-dimensional layout system in CSS.

It helps arrange elements in a single direction—either in a row or a column.

Instead of manually using margins or positions, Flexbox automatically aligns and spaces items.

Example:

```css
.container{
    display: flex;
}
```

By default, items are placed in a row.

```
+-----------------------------+
| Item 1  Item 2  Item 3      |
+-----------------------------+
```

Some commonly used Flexbox properties:

| Property | Purpose |
|----------|---------|
| `display: flex` | Turns an element into a flex container |
| `flex-direction` | Changes the direction (row or column) |
| `justify-content` | Aligns items along the main axis |
| `align-items` | Aligns items along the cross axis |
| `gap` | Adds space between items |
| `flex-wrap` | Allows items to move to the next line if needed |

Flexbox is best used for:

- Navigation bars
- Buttons
- Cards
- Centering elements
- Small layouts

---

# 7. CSS Grid

CSS Grid is a two-dimensional layout system.

Unlike Flexbox, Grid can control both rows and columns at the same time.

Example:

```css
.container{
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

Diagram:

```
+---------------------------+
| Sidebar | Main Content    |
|         |                 |
|         |                 |
+---------------------------+
```

Common Grid properties:

| Property | Purpose |
|----------|---------|
| `display: grid` | Creates a grid container |
| `grid-template-columns` | Defines the number and size of columns |
| `grid-template-rows` | Defines rows |
| `gap` | Adds spacing between grid items |
| `grid-column` | Controls how many columns an item spans |
| `grid-row` | Controls how many rows an item spans |

Grid is best used for:

- Full webpage layouts
- Dashboards
- Galleries
- Complex page structures

---

# Flexbox vs Grid

| Flexbox | Grid |
|----------|------|
| One-dimensional | Two-dimensional |
| Works with rows **or** columns | Works with rows **and** columns |
| Best for small layouts | Best for complete page layouts |
| Great for alignment | Great for structured layouts |

A simple way to remember the difference:

```
Flexbox

Item → Item → Item
(One direction)


Grid

+---------+---------+
| Item 1  | Item 2  |
+---------+---------+
| Item 3  | Item 4  |
+---------+---------+

(Rows and Columns)
```

# 8. What Happens When You Open a Website?

When we type:

```
www.example.com
```

Many things happen before the webpage appears.

The process looks like this:

```
You
 │
 ▼
Browser
 │
 ▼
DNS
 │
 ▼
TCP
 │
 ▼
TLS
 │
 ▼
HTTP
 │
 ▼
Browser Rendering
 │
 ▼
Website Appears
```

Let's understand each step.

---

## Step 1 — DNS

DNS stands for Domain Name System.

Humans remember names.

Computers remember IP addresses.

DNS translates:

```
google.com
```

into

```
142.250.xx.xx
```

Think of DNS as the internet's phonebook.

---

## Step 2 — TCP

TCP stands for Transmission Control Protocol.

It creates a reliable connection between your browser and the server.

Before sending data, both sides agree that they're ready.

This is called the Three-Way Handshake.

```
Browser ---- SYN ---->

Server <--- SYN-ACK ---

Browser ---- ACK ---->

Connection Established
```

Now both devices can communicate safely.

---

## Step 3 — TLS

TLS stands for Transport Layer Security.

It encrypts the data.

Without TLS:

```
Password
↓

Anyone could read it.
```

With TLS:

```
Password
↓

Encrypted

↓

Only the server can understand it.
```

This is why websites show:

```
https://
```

instead of

```
http://
```

The lock icon in the browser means TLS is protecting your connection.

---

## Step 4 — HTTP Request & Response

Now the browser requests the webpage.

Example request:

```
GET /
Host: example.com
```

The server replies:

```
200 OK

HTML
CSS
JavaScript
Images
Fonts
```

The browser downloads these files.

---

## Step 5 — Browser Rendering

Now the browser starts building the page.

It:

1. Reads HTML
2. Creates the DOM
3. Reads CSS
4. Applies styles
5. Calculates layout
6. Paints pixels on the screen

Simplified diagram:

```
HTML
 │
 ▼
DOM
 │
 ▼
CSS
 │
 ▼
Styled DOM
 │
 ▼
Layout
 │
 ▼
Paint
 │
 ▼
Website
```

This entire process usually takes only a fraction of a second.

---

# Summary

```
HTML
↓

Creates Structure

↓

CSS
↓

Adds Design

↓

Browser

↓

Reads HTML

↓

Creates DOM

↓

Finds Server using DNS

↓

Connects using TCP

↓

Encrypts using TLS

↓

Downloads page using HTTP

↓

Renders Website
```

---

# What I Learned

- HTML provides structure.
- Semantic tags make webpages meaningful.
- The browser converts HTML into the DOM.
- CSS controls presentation while HTML defines content.
- CSS selectors determine which elements receive styles.
- Opening a webpage involves DNS, TCP, TLS, HTTP, and browser rendering before anything appears on the screen.

---

