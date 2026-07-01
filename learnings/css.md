# ---------CSS - What I Learned Today (Day- 4)-----------
 
***This document explains everything I learned in Day-4 class,
It covers the DOM,the three  ways to write CSS,
why certain HTML practices are Avoided, and every CSS selector I practiced***

## Why CSS matters
- HTML gives a page its structure.
- CSS gives that structure its look.
- Without CSS, a page is just plain text in order, no design.

## The DOM
- The DOM is how the browser represents the page as a tree of elements.
- Every tag is a "node," nested tags become "children" of their parent.
- The Elements tab in DevTools shows this live tree, not just my raw HTML file.
- The Styles panel shows which CSS rules are matching which elements.

## Branching in the DOM
- The DOM is a branching/tree structure, not a flat list.
- Example from my own resume:
  - html → body → header → table, nav
  - html → body → main → section#objective, section#education, section#skills, section#contact
  - html → body → footer
- A parent tag can have many children, and those children can have their own children too.
- This branching is exactly why descendant selectors (`nav a`) and child selectors (`header > table`) work the way they do — they're navigating this tree.

## DOM access vs no DOM access
- DOM access = can read/change the live page after it loads (this is JavaScript's job).
- No DOM access = can't read or modify the live page (plain CSS doesn't do this).
- CSS just describes rules the browser applies to whatever matches-it doesn't let you read the page or react   to events. 


## Types of DOM access(conceptually)
- Reading the DOM — just inspecting what's currently on the page (this is what the Elements tab does).
- Modifying the DOM — changing content/attributes/structure after the page has loaded (JavaScript's job, not CSS).
- Styling via the DOM — CSS selectors are really just "find this node in the DOM, apply this style to it".
- Developer Tools is useful because:
   - Elements tab - shows the live DOM tree.
   - Styles panel - shows exactly which css rules are matching which elements.

## Writing CSS live in the browser
- In DevTools, I can click an element in the Elements tab and edit its styles directly in the Styles panel.
- This changes the page instantly, without touching or saving any actual file.
- It's useful for testing a style quickly before writing it permanently into my real .css file.
- Refreshing the page removes these live changes since they were never saved to a file.

## The three ways to add CSS
- Inline: written directly on the tag. Quick but messy, hard to maintain.
- Internal: a `<style>` block inside the HTML file's `<head>`. Better, but stuck in one file.
- External: a separate .css file linked with `<link>`. Best — reusable, clean, easiest to maintain.

## The painter analogy
- CSS in the `<head>` = painter paints the house while it's being built — visitor only sees the finished house.
- CSS at the bottom = painter shows up after — visitor sees a plain house first, then it suddenly gets painted.
- This is why CSS goes in the `<head>`, to avoid that flash of unstyled content.

## File paths
- `href="./style.css"` means "look in the current folder."
- This is why my CSS file loads correctly when it's sitting next to my index.html.
- ./ means "start looking in the current folder"

## Why HTML never gives an error
- HTML has no strict syntax checker like JavaScript does.
- Wrong/missing tags don't stop the page — the browser just guesses and renders something anyway.
- This means small mistakes can break a section silently, with no warning.

## Why we avoid the `<table>` tag for layout
- Tables are meant for real data (like my Education section), not for arranging a page.
- Tables don't resize well on different screens.
- Screen readers get confused when tables are used for layout instead of data.
- Table layouts are harder to edit and restyle later.

## Selectors I learned

- Element selector — targets every element of a tag.
  `body { font-family: Arial, sans-serif; }`

- Class selector — targets elements with a specific class.
  `.highlight-box { background-color: #fdf2ec; }`

- Id selector — targets the one element with a specific id.
  `#contact form { color: #222; }`

- Grouping selector — applies one rule to multiple selectors at once.
  `h1, h2, h3 { font-family: Georgia, serif; }`

- Descendant selector — targets an element nested anywhere inside another.
  `nav a { color: #5a1a1a; }`

- Child selector — targets an element only if it's a direct child.
  `header > table { background-color: #ffffff; }`

- Attribute selector — targets an element based on an attribute's value.
  `input[type="email"] { color: #5a1a1a; }`

- Compound selector — targets an element matching two conditions at once (tag + class).
  `h3.featured { color: #c0522d; }`

- Universal selector — targets every element on the page.
  `* { font-family: Arial, sans-serif; }`

- `:hover` pseudo-class — targets an element while the mouse is over it.
  `nav a:hover { text-decoration: underline; }`

## What I did for the task
- Linked style.css externally in my index.html `<head>`.
- Used all the selectors above on my real resume elements.
- Wrote this file to explain my understanding.
- Built profile-card, navbar, and buttons as separate practice projects.




# ----------Improve Resume using better semantic tags, better version(Day-5)------------

***A breakdown of every HTML tag and CSS selector used in index.html and style.css, grouped by purpose with  explanation each***

---------------------------------------
###HTML TAGS
---------------------------------------

--- Document structure ---
- `<html lang="en">` - Root of the page, declares language
- `<head>` - Metadata container (not visible on page)
- `<meta charset>` - Sets character encoding
- `<meta viewport>` - Makes the page responsive on mobile
- `<title> `- Text shown in the browser tab
- `<link rel="stylesheet"> `- Connects the CSS file
- `<body>` - Everything visible on the page


--- Semantic layout tags ---
- `<article>` - A self-contained block of content (whole resume, each project card)
- `<header> `- Intro area — name, title, nav
- `<hgroup> `- Groups a heading with its subheading (h1 + h3)
- `<nav> ` - Navigation links
- `<aside> `- Content related to but separate from main flow (sidebar, highlight box)
- `<section>` - A distinct thematic chunk (Skills, Education, Projects, etc.)
- `<main>` - The primary content of the page
- `<footer>` - Closing area — place & signature


--- Headings & text ---
- `<h1> to <h3>` - Headings, in order of importance
- `<span> `- Inline wrapper with no meaning of its own — used only for the gold "Bora" accent
- `<p>` - Paragrap

-- Media & figures ---
- `<figure>` - Wraps an image with an optional caption
- `<img> `- The profile photo
- `<figcaption>` - Caption for the figure (visually hidden here, kept for accessibility)

--- Lists ---
- `<ul> / <li>` - Unordered list (skills, hobbies, contact links)
- `<ol> `- Ordered list (project steps, since order matters)
- `<dl> / <dt> / <dd>` - Description list — pairs a term (school) with its detail (dates), used for Education

--- Contact info ---
- `<address>` - Marks up contact information specifically
- `<a href> `- Hyperlink

--- Interactive / disclosure ---
- `<details> / <summary>` - Native expand/collapse widget — "More about this project"

--- Form ---
- `<form> `- Wraps form controls
- `<input type="text">` - Single-line text input
- `<input type="email">` - Email input (adds basic browser validation)
- `<textarea>` - Multi-line text input
- `<button type="submit">` - Submits the form


----------------------------------------
##CSS SELECTORS
----------------------------------------

--- Custom properties ---
- `:root { --dark: #1c1c1c; }`
- Defines reusable variables (colors) at the top level, referenced later via var(--dark).

--- Universal selector ---
- `* { box-sizing: border-box; }`
- Targets every element — used here to reset box-sizing and font globally.

--- Type (element) selectors ---
- `body { ... }   h1 { ... }   p { ... }   hr { ... }`
- Targets all elements of that tag name, no matter where they are.

--- Class selectors ---
- `.resume { ... }   .sidebar { ... }   .highlight-box { ... }`
- Targets any element with that class="..." attribute — the most-used selector type here.

--- ID selectors ---
- `#objective { ... }   #contact form { ... }   #skills { ... }`
- Targets one specific element by its id. Note #contact form combines an ID with a descendant tag.

--- Grouping selector ---
- `h1, h2, h3 { font-family: Arial; }`
- Comma-separates multiple selectors so they share one rule block, instead of repeating it three times

--- Descendant combinator ---
- `.sidebar h2 { ... }   #projects article:hover { ... }`
- Space between selectors = "the second one, anywhere inside the first." .sidebar h2 only styles h2s inside .sidebar, not every h2 on the page.

--- Compound selector ---
- `.sidebar h3.featured { ... }`
- No space = same element must match both, Here: an h3 that is also inside .sidebar and also carries the featured class.

--- Pseudo-classes ---
- `nav a:hover { ... }`
- `.sidebar-section:last-child { ... }`
Style an element based on a state or position — :hover fires on mouse-over, :last-child targets the final sibling.

--- Pseudo-elements ---
- `h2::after { content: ""; }`
- `.sidebar li::before { content: "\25C6"; }`
- Generate a virtual "extra" element attached to the real one — draws the gold line after headings and the diamond bullet before list items. Pure decoration, not real content.

--- Attribute selectors ---
- `input[type="email"] { border-color: var(--gold); }`
-` input[type="text"] { border-color: var(--dark); }`
- Targets elements based on an attribute's value — lets the two input types have different border colors without extra classes.

--- Media query ---
- `@media (max-width: 750px) { ... }`
-Not a selector on its own, but a conditional wrapper — rules inside only apply when the screen is narrower than 750px (stacks the grid into one column for mobile).


-----------------------------------
##QUICK REVISION
------------------------------------
- Tag = what kind of thing is this (semantic meaning: article, nav, dl)
- Class = reusable style hook (.sidebar-section)
- ID = one unique target (#objective)
- Pseudo-class = state-based (:hover, :last-child)
- Pseudo-element =  extra element for decoration (::before, ::after)


-------------------------------------
##WHY WE AVOID USING TABLE TAGS
-------------------------------------


# Even though tables can display data neatly, this resume avoids` <table> `for layout — here's why:

-` <table>` means "this is a grid with rows AND columns that relate to each other across both axes" — like a price comparison chart or a multiplication table, where you'd genuinely have column headers.

- The Education section here is just pairs — one term, one detail (school → dates). There's no second axis, no column headers, nothing that needs row/column relationships.

- `<dl>/<dt>/<dd> `(description list) was built exactly for this shape: "term → detail" pairs, not a full grid.

-Using` <table> `for non-tabular content is a semantic and accessibility problem (it confuses screen readers, which announce "table" and try to navigate it row by row.


--------------------------------
##WHAT I LEARNED
--------------------------------

- Went deep into the HTML tags and CSS selectors used in my resume project 
today. Key takeaway: semantic HTML isn't about which tag "looks right" — 
it's about picking the tag whose MEANING matches the content's actual 
shape.

- Learned the difference between `<table> `(grid data, two axes) and 
  `<dl>/<dt>/<dd> `(term → detail pairs) — and corrected my own assumption 
  that we avoid tables for file size. It's actually about semantic 
  correctness and accessibility (screen readers), not weight.

- Went through every tag in my resume — structural (header, main, footer), 
  semantic (article, section, aside), and form elements — and understood 
  WHY each one was chosen over a generic div/span.

- Broke down every CSS selector type used: type selectors, class/ID 
  selectors, grouping, descendant combinators, compound selectors, 
  pseudo-classes (:hover, :last-child), pseudo-elements (::before, 
  ::after), attribute selectors, and media queries.

- Biggest mindset shift: writing "no div, no span" HTML forces you to 
  actually think about what each piece of content IS, not just how to 
  make it look styled,That's the real value of semantic markup — for 
  accessibility, SEO, and for the next person (or future me) reading 
  the code.


