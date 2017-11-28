# It's Not Dark Magic
### Pulling Back the Curtains from Your Stylesheets
[Slides](https://github.com/AimeeKnight/Dark-Magic)

> A language that doesn't affect the way you think about programming is not worth knowing – Alan J. Perlis

- Software devs spend more time reading than writing
- Knowledge of internals can be useful for advanced debugging and performance tuning
- **In the future, we'll be able to modify the browsers' rendering engine ourselves!**

## Houdini
- Normalize cross-browser differences
- Invent or polyfill new features

> Low-level programming is good for the developer's soul – John D. Carmack

## Can't I just use component based styling?
- No longer able to change one variable and update all colors
- Unable to affect children by parent classes

## Browser Internals

### How do browsers actually work?

- UI
- Browser Engine -> Data persistence
- Rendering Engine
 - Networking
 - Javascript Engine
 - UI Backend

### Flow:
#### HTML Parser:
Bytes -> characters -> tokens -> nodes -> DOM
- Browser sends HTTP req
- Webserver responds
- Browser converts buffer into tokens
- Tokens -> nodes
- nodes get placed in the tree
- pause for CSSOM

#### CSSOM
- By default, CSS is treated as a render blocking resource
- Browers will hold rendering of any process until the CSSMOM is constructed
- CSS files are parsed into Stylesheet Objects
- Broken down into rules Objects
- Each rule contains selector and declaration objects.
- Not 1:1 with the DOM
- Display none, script tags, meta tags, head element, etc. are ommitted since they're not reflected in the rendered output.

#### Render tree
- Visual representation of the document
- Enables painting the contents in their correct order
- CSSOM can have drastic effects on the render tree but not the DOM
- Knows how to paint and layout itself and its children
- Knows geometry and properties

#### Layout
- Calculating the position and size of the tree's render Objects- The output of the layout process is a box model that contains the position and size of every element within the viewport

#### Paint
- Converts each node in the render tree to the actual pixels on the screen.
- Multiple rounds of painting can be by JS being loaded that changes the DOM
- Includes: test, colors, shadows, etc.
- Changing any properties besides transform or opacity with trigger a repaint
- Painting time varies based on render tree construction
- Adding different effects increases time
- **Paint is usually the most expensive phase**
- Painting Order
 1. Follows order that elements are placed in the render tree

#### Composite
- Render different elements of a webpage in different layers
- Action of flattening all layers into the final image that is visible on the screen.

### Rendering performance
- Changes to the elements position will cause relayout and repaint of that element, children and siblings
- Adding a DOM node will cause a relayout and repaint of the parent node
- Major changes like font size changes will relayout and repaint the entire tree
- Color changes will only trigger a repaint
- Opacity and transform will only recomposite

## Common Issues

> The amatuer software engineer is always in search of magic – Grady Booch

### Specificity
- Many ways to target a specific tag using CSS selectors
- Applying rules in the correct cascade order
- The selector with the highest specificity value winds

### Positioning
- **Normal**: object is placed according to its place in the doc, box type and the geometry
- **Relative**: normal then delta applied
- **Absolute**: object is placed in a completely separate part of the render tree

### `z-index`
- Every element in an HTML doc can be either in front or behind every other element in the document

#### Stacking Context
- A 3d representation of HTML elements along an imaginary z-axis relative to the user facing the viewport
- An elemnt contains a set of layers
- A group of elements moves together
- Children are confined to that stacking context. Everything is relative to that root HTML element
- Compositing properties create new stacking contexts

#### Stacking order
- Every stacking context has a single HTML element as its root element
- When z-index and position properties aren't involved, the rules are simple: DOM order

4$$
