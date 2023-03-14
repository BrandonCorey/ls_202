## Margins ##
Margins are transparent
- Margins lie outside of the border of the element, not clickable
- Magins are not considered part of the element
- Things like background color of a container will appear in the margin of an element
- Top and bottom margins **collapse** on the larger mrgin
  - So if two paragapah elements are on top of each other, the space between them wouldn't be top + bottom. It would be top OR bottom (whichever margin is larger)

## Padding ##
Padding is usually opaque
- Part of the visible and clickable bounds of an element
- Things like background color for an element will be visible within the padding, not margin

### How to choose ###
A technique is to use margins everywhere except when you need padding. You probably need to use padding when:
- You want to change the height or width of a border.
- You want to adjust how much background is visible around an element.
- You want to alter the amount of clickable area.
- You want to avoid margin collapse.
- You want some horizontal spacing to the left or right of an inline element.
- As before, use padding to separate the left and right sides of a container from its content. Use margins for the vertical gap.