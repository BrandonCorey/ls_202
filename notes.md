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
first-name=Joe&last-name=Jones
```