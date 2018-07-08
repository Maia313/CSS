
> To make an image responsive to the container it is in, you will set the width to 100%. The following is a basic CSS example to make your images responsive:
```css
img {
    max-width: 100%;
    height: auto;
}
```

```css
/* Change all elements to use border-box */
html {
    box-sizing: border-box;
}
*, *:before, *:after {
    box-sizing: inherit;
}

```

The `max-width` property of 100% scales the image to fit the width of its container, but the image won't stretch wider than its original width. Setting the `display` property to block changes the image from an inline element (its default), to a block element on its own line. The `height` property of auto keeps the original aspect ratio of the image.
```css
img {
  max-width: 100%;
  display: block;
  height: auto;
}
```
