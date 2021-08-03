# HTML/CSS book, Ch. 15, “Layout”

- Going to recap some of these elements now that I have a bit better understanding of them.

## Block Level Elements

Automatically move to a new line when created
> h1, p, ul, li

## Inline Elements

Flow in between surrounding text.
> img, b, i

## Containing Elements

A block level element within a block level element creates a parent-child relationship.

Div elements are often used as a ***container*** to store related elements.

## Positioning Elements

### Relative Positioning

Moves something in relation to where it would be in normal flow, ie. shifting something up/down/left/right of where it would normally be if left alone.

### Absolute Positioning

- Takes an element out of normal flow and places it realtive to its container.
- Move as someone scrolls up and down.
  - Works well for headings or chatboxes, etc.
- Doesn't affect other elements

### Fixed Positioning

- Type of Absolute positioning
- Positions in relation to browser window rather than containing element (364)
- I don't see this one as useful since this does not stay in position when scrolling.

### Float

- Newspaper styling - elements wrap around when using float.
- Z-index is the bring to front/send to back functionality

### Page Sizes

- Developers used to have standardized sizing when creating their screen sizes, but now are just trying to keep the most important content within the top 570-600 pixels of the page (379).
