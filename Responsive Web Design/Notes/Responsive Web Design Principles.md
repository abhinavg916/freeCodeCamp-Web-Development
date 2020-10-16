# Responsive Web Design Principles Notes

## Make an Image Responsive

- Making images responsive with CSS is actually very simple. You just need to add these properties to an image:

```css
img {
  max-width: 100%;
  height: auto;
}
```

- The max-width of 100% will make sure the image is never wider than the container it is in, and the height of auto will make the image keep its original aspect ratio.
- Add the style rules to the responsive-img class to make it responsive. It should never be wider than its container (in this case, it's the preview window) and it should keep its original aspect ratio. After you have added your code, resize the preview to see how your images behave.

## Use a Retina Image for Higher Resolution Displays

- With the increase of internet connected devices, their sizes and specifications vary, and the displays they use could be different externally and internally. Pixel density is an aspect that could be different on one device from others and this density is known as Pixel Per Inch(PPI) or Dots Per Inch(DPI). The most famous such display is the one known as a "Retina Display" on the latest Apple MacBook Pro notebooks, and recently iMac computers. Due to the difference in pixel density between a "Retina" and "Non-Retina" displays, some images that have not been made with a High-Resolution Display in mind could look "pixelated" when rendered on a High-Resolution display.
- The simplest way to make your images properly appear on High-Resolution Displays, such as the MacBook Pros "retina display" is to define their width and height values as only half of what the original file is. Here is an example of an image that is only using half of the original height and width:

```html
<style>
  img {
    height: 250px;
    width: 250px;
  }
</style>
<img src="coolPic500x500" alt="A most excellent picture" />
```

- Set the width and height of the img tag to half of their original values. In this case, both the original height and the original width are 200px.

## Make Typography Responsive

- Instead of using em or px to size text, you can use viewport units for responsive typography. Viewport units, like percentages, are relative units, but they are based off different items. Viewport units are relative to the viewport dimensions (width or height) of a device, and percentages are relative to the size of the parent container element.
- The four different viewport units are:

```
vw (viewport width): 10vw would be 10% of the viewport's width.
vh (viewport height): 3vh would be 3% of the viewport's height.
vmin (viewport minimum): 70vmin would be 70% of the viewport's smaller dimension (height or width).
vmax (viewport maximum): 100vmax would be 100% of the viewport's bigger dimension (height or width).
```

- Here is an example that sets a body tag to 30% of the viewport's width.

```css
body {
  width: 30vw;
}
```

- Set the width of the h2 tag to 80% of the viewport's width and the width of the paragraph as 75% of the viewport's smaller dimension.
