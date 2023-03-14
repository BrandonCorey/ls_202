## `img`
A self closing tag that tells the borwser to load and display a foreground image from a seperate resource
### Attributes
- `src`- tells browser where to find image. same link format as anchor tag
- `alt` - describes the content of the image to aid users who use screen readers
  - Also helps search engines index images, useful for SEO
- `width` and `height` - (optional) Provide width and height of image in pixels. CSS `width` and `height` override these attributes

## `figure` and `figcaption`
Designates an item as a representation of information discussed in the content
- `figure` - usually encloses some media (image, video, audio)
- `figcaption` - allows you to specify a short caption for the media

```html
<figure>
  <img src="masthead.jpg" alt="Sunset over the forest">
  <figcaption>The sun sets over the dense forest</figcaption>
</figure>
```

## Images as links
Any non-interactive HTML element can be used as a link, including images
```html
<a href="url-of-link">
  <img src="url-of-image" alt="alt-text">
</a>
```

## Background image
Can apply a background image to a page or element using CSS
- `background-image` - specify an image to use for the element/body
  - e.g `url('http://exampleImage/image.png')`
  - e.g `url('.public/images/image.pgn')`
- `background-size` - Can be used with any unit of measurement to determine size of image for element
  - TBRL for inputs. Can also specify a %