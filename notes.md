# HTML and CSS Notes #
## HTML Skeleton ##
```HTML
<!DOCTYPE html>
<html lang='en-US'>
  <head>
    <meta charset="utf-8">
    <title>Insert title here</title>
  </head>
  <body>
    Enter HTML body here
  </body>
</html>
```

- `DOCTYPE` must be the first item in an HTML document, cannot be preceded by anthing, even white space
  - It tells the browser what markup language to expect e.g HTML or XML
- `html` element encloses the entire HTML document
- `head` element encloses document header, which contains **meta** information about the document
  - `meta` is a _self-closing element_, meaning it does not have a closing tag

**Bonus elements**

Styling
- `strong` - Used to bold text
- `em` - Used to italicizse text

Semantic
- `p` - Paragraph
- `ol` - Ordered list
- `ul` - Unordered list
- `li` - list item
- `article` - news article, weblog, forum post, comment on article etc...
- `section` - A section of the page, a chapter of an article etc...
- `blockquote` - A quotation of something else
- `address` - An address for a location
- `pre` - Signifies some sort of pre-formatting
- `aside` - Sidebar comments, pullquote, gloasary, footnote, advertising, tangentially related

Non-semantic
- `div` - Flow content with no additional semantics

Anchor
- `a` - Used with `href` (hyper-link reference)attribute to include a hyperlink e.g `<a href="https://launchschool.com">Hyper-link text goe here</a>`
  - Can add attribute `target="_blank"` to open the link in a new tab
  - e.g `<a href="https://launchschool.com" target="_blank">Hyper-link text goe here</a>`

Image
- `img` - Used with `src` attribute (source) to include an image e.g `<img src="picture.jpg">`

Link
- `link` Used with `rel` (relation) and `href` attribute to link another file to HTML
- Typically used to link a JS or CSS file e.g `<link rel="stylesheet" href="styles.css">`
- `rel` just acts as a descriptor for what the relation of the file is to the html

## Classes, IDs, and Names ##
These are the three ways to identify certain elements in HTML

### Classes ###
Identifies a set of page elements that will be styled conistantly
- Use `class` attributre to assign a class or classes to an element
- Any number of elements may belong to the same class
- Elements can belong to multiple classes, but must list all of them seperated by space within string
  - e.g `class="executive management full-time` --> member of `executive`, `management`, and `full-time` classes
- Can select classes with **CSS selectiors**:
```css
.executive {
  text-decoration: underline;
}
```

### IDs ###
Attribute that can be used to identify a unique element. IDs must be unique, only one per element
- Can be selected using CSS selection syntax `#id-name`
```html
<h1 id="head-line">The beginning of the document</h1>
```
```css
#head-line {
  font-size: 48px;
  text-align: center;
}
```

### Names ###
An attribute that is used to tie **form** elements to data on the server
- It does not play a role in styling, only identifying data
- When a form is submitted, the browser sends the form data to the server using the name/value pairs that are derived from the `name` attribute
- `for` attribute is used to reference an `id` attribute, so it is common practice for `name` to be the same as `id`
```html
<form method="get" action="#">
  <label for="first-name">First name:</label>
  <input type="text" name="first-name" id="first-name">

  <label for="last-name">Last name:</label>
  <input type="text" name="last-name" id="last-name">

  <input type="submit" value="Search">
</form>
```
```
When the form is submitted, the browser constructs this query string:
first-name=Brandon&last-name=Corey
- Note that name `first-name` and `last-name` come from the `name` attribute
- The `Brandon` and `Corey` become the values for these names after they are submitted
```

## CSS notes ##
Cascading style sheets is used to style HTML
- Organized as property-value combinations

**Important properties**
- `color` - text color
- `background-color` - background color
- `text-align` - left, center, right, or justify align
- `font-size` - size of font
- `font-family` - serif, sans serif, monospace etc... --> Can give browser multiple options in case one is not available
- `font-style` - italic
- `font-weight` - bold
- `font` - A shorthand for the above equal to: `font-style font-weight font-size/line-height font-family`
  - `font: italic bold 20px/2.5 Verdana, "Trebuchet MS", Tahoma, sans-serif;`
  - Not all values are required, CSS will know whihc ones are which e.g `font: 16px Arial`

### Ways to include CSS ###
- Inline
```html
<h1 style="color: red; text-decoration: underline;">I want red underlined text!</h1>
```
- Internal
```html
<style>
  h1 {
    color: red;
    text-decoration: underline;
  }
</style>
```
- External
```html
<head> <link rel="stylesheet" href="/filepath"> </head>
```

### Nested selections ###
Select the orange on the fancy plate:
- `#fancy orange`

Select the oranges in the bentos:
- `bento orange`

Select the small oranges:
- `orange.small`

Select the small organes in the bentos:
- `bento orange.small`

Select all of the plates and bentos
- `plate, bento`

Select everything on a plate:
- `plate *`

Select every plate that directly follow a bento
- `plate + bento`

Select all plates that follow a bento
- `plate ~ bento`

```html
<div class="table">
  <apple />
  <apple class="small" />
  <bento>
    <orange class="small" />
  </bento>
  <plate id="fancy">
    <orange />
  </plate>
  <plate>
    <orange class="small" />
  </plate>
</div>
```