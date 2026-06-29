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