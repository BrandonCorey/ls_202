## Absolute vs relative units ##
These are the units of measurements providfed to CSS properties like:
- `width`, `height`, `margin`, `padding`, `border` and `font-size`

### Absolute Units ###
The only absolute unit we usually concern ourself with ix pixels (px)
- This isn't as straightforward as it seems
  - Not all displays have the same amount of pixels
  - Not all displays' pixel sizes are the same

### Relative Units ###
The most common relative units are `rem`, `em`, and `%`
- `rem` is are calculated from the **root font size** of the document
  - **root font size** should be specified in pixels for the `html`  element
- `em` is calculated from the **calculated** font size of the element
  - This is less conistant and can cause compounding issues if elements are nested
-  **Percentages** define dimensions as a faction of the containers width or height
  - e.g if you set `block` or `inline-block` elements to `width: 50%`, they fill half the continer

### Auto ###
Can use it to let browser determine a few different things
- Determine a `width` or `height` for you
  - Browsers default to setting these to `auto` when they are not specified
  - Fits entire element, including margins, inside of its container
- Left or right `margin` with `auto` push the element all the way to the opposite side of container
  - If you specify `auto` for both left and right, it will center a **block** element
- For top and bottom margin, `auto` is equal to 0
- Padding does not except `auto` values

**Notes**
`width: 100%` and `width: auto` are not the same thing because:
- `width: auto`
  - browser will put content + padding + border + margins in container
- `width: 100% border-sizing: border-box`
  - browser will put content + padding + border in container, margin is outside though, so won't be part of browser calulction for how big the element can be at %100
    - Can lead to overflow
- if you add in `width: 100% border-sizing: content-box`
  - browser will put content in container, so padding, border, and margin outside will not be part of the calculatioon for how big the element can be at %100
      - Can lead to overflow

  ![measurement-units-02](https://user-images.githubusercontent.com/93304067/224379639-b0cd37d0-bfea-40e2-bea0-ca13bf4f6ddf.png)

## when to use ##
- Use absolute units sparingly, and stick with pixels. Pixels work well for:
  - the root font size
  - image widths and heights
  - top and bottom margins and padding, sometimes useful with left and right margins and padding
  - width or height of fixed-width/fixed-height containers such as navigation sidebars
  - border widths

- Use relative units liberally:
  - Use rems for fonts, possibly with a fallback to ems or pixels. The root font should use pixels.
  - If you must use ems instead of rems, try to avoid compounding font sizes.
  - Use rems, ems, or pixels for left and right margins and padding.
  - Use % for measurements that are proportional to the container element's width or height. Percentages work best for container dimensions and come in handy when you want certain - - areas of the page to grow and shrink as the width of the browser window changes.
  - Use auto with width and height to let the browser calculate an appropriate value.
  - Use auto with left and right margins to left, center, or right justify a block element within its container.