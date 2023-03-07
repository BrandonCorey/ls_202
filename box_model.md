# Everything is a box #
The browser puts every HTML element inside of a box
- Every element requires a box-shaped segment of the page
- Every character of text content also needs a boxed portion of the page
- The browser calculates the dimensions of that box by using the browser defaults and CSS
- **Boxes are placed left to right**, unless there is not enough room, then they are placed on the next line

## Box properties ##
- `width` - How much horizontal space is needed for _content area_ of the box
- `height` - How much vertical space is needed for _content area_ of the box
- `padding` - Area that surrounds the content area of the box, seperates it from the border
  - Typically opaque (not transparent) and hides anything it overlays
- `border` - A boundary that surrounds the padding
- `margin` - A transparent area that lies outside of the border and acts as seperation between elements
- `display` - A property that determines how the browser lays out an element relative to its neighbors
  - `block`
  - `inline`
  - `inline-block`

Looks something like this for each element:

![image](https://user-images.githubusercontent.com/93304067/223458608-b38b8ab4-4f07-4aac-9247-0b2482fafa79.png)

## Visual formatting model ##

### Block elements ###
Block elements occupy all horizontal space available within their container
- They do this regardless of what their `width` is
- There container may also be a block element, most block elements group one or more elements
- Block properties
  - `width`
  - `height`
  - `padding`
  - `border`
  - `margin`

**Most elements are block elements, including:**
- `section`, `article`, `aside`, `header`, `footer`
- `p`
- `h1` through `h6`
- `blockquote`
- `ul`, `ol`, `dl`
- `figure` and `figcaption`
- `form` and `fieldset`

**Note** that any element can be conveted to a block element with `display: block`
 - Its common to render `a` and `img` as blocks

 ### Inline elements ###
 Provide a small bit of semantic meaning to content, used to alter how sections of text are displayed
 - Meant to be part of a line of text
 - e.g if you wanted to use bolded text for definitions, use the `strong` element
 - Flow onto the next line if `width` is wider than available `width`
 - Browsers handle left and right _margins_ and _padding_ same as block elements
   - Handle many other properties differently
 
 **Differences from block**
 Browsers:
 - ignore `width` and `height` properties (except with `img`)
 - ignore top and bottom margins
 - **don't** ignore borders, but results may look odd
 - **don't** ignore top and bottom padding
 - **don't** ingore left and right padding and margins

**The following elements are `inline` by default**
- `span`
- `b`, `i`, `strong`, `em`
- `a`
- `sub` and `sup`
- `img`

### Inline-block elements ###
Act like block elements, except they do _**not**_ take up an entire row when `width` is less than available width
- Instead, they flow in the same way that `inline` elements flow from one line to the next
- This lets you place inline block elements side by side (unlike block)
- Inline block elements can be aligned vertically with `vertical-align` (top, bottom, middle)
- **Don't** ignore the `width` and `height` properties (unlike inline)
- Can convert _any_ element to inline block using `display`

## Nesting elements ##
HTML allows for nesting elements, but there are rules
- `block` can nest `block`, `inline-block` and `inline`
- `inline-block` can nest `inline-block` and `inline`
- `inline` can only nest `inline`

## `box-siziding` ##
A versatile CSS property that affects how an HTML element is sized
- `content-box` --> sizing (**Browser Default**): Size of actual `content` area
  - `width` --> visible width of rendered box (`border` and `padding` are moved inside `width`)
  - `height` --> visible height of rendered box (`border` and `padding` are moved inside `height`)
- `border-box` --> sizing: Considred the **optimal** option to use
  - `width` + `padding` + `border` --> visible width of rendered box
  - `height` + `padding` + `border` --> visibile height of rendered box

To apply `border-bodx` to all HTML elements
```css
html {
  box-sizing: border-box;
}

*, *::before, *::after {
  box-sizing: inherit;
}
```