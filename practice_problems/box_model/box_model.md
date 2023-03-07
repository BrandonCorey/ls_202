How large does the div need to be below? Height and width
```html
<div>
  <img src="#" alt="test">
</div>
```
```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

img {
  border: 4px solid red;
  box-sizing: content-box;
  display: inline-block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}
```
img height = 300 +  (10 * 2) + (4 * 2) + (20 + 10) --> 358
-------------height---padding-----border-----margin---
img width = 500 + (20 * 2) + (4 * 2) + (11 + 19) --> 578
-----------width---padding-----border----margin---
div border = 2
div box-sizing = border box

div min height: 360
div min width: 580

- Note that because `div` is `border-box`, border is part of its total hieght
- That means we need to add it to the height of 578 (img height)

How large must minimum width and height be for div to fit em?
```html
<div>
  <em>content</em>
</div>
```
```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

em {
  border: 4px solid red;
  box-sizing: content-box;
  display: inline; /* This one is inline, not inline-block or block */
  height: 300px; /* Ignored */
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px; /* Ignored */
}
```

- em is inline, so width, height, top and bottom margins will be ignored
- We need to know actual width of content to know how large the div needs to be

div min widtht = (20 * 2) + (4 * 2) + (11 + 19) + 2 --> 80 + whatever content width of em ends up being
div min height = (10 * 2) + (4 * 2) + (20 + 10) + 2 --> 50 + whatever content length ends up being
padding----border------margin--div border


Minmum height of div to contain article?
```html
<div>
  <article>content</article>
</div>
```
```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

article {
  border: 4px solid red;
  box-sizing: border-box; /* this one is border box, not content box */
  display: inline-block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px; /* Includes padding and border */
}
```

div min width = 500 + (19 + 11) + 2 --> 532
div min height = 300 = (20 + 10) + 2 --> 332
--------height/width---margin--div border

Given the code
```html
<div>
  <tag1>content</tag1><tag2>content</tag2>
</div>
```
```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: content-box;
  display: inline-block;
  margin: 0;
  padding: 0;
  width: 720px;
}

tag1, tag2 {
  box-sizing: border-box;
  height: 240px;
  margin: 0;
  padding: 0;
  width: 360px;
}

tag1 {
  background-color: yellow;
}

tag2 {
  background-color: lime;
}
```

Which element pairs would display side by side properly. Assume the content with of `inline` elements is 360
div content width --> 720px (it is a content box)
- both inline (360 * 2) --> 720
- inline-block, inline (360 * 2) --> 720
- inline-block, inline, block (360 * 2) --> 720