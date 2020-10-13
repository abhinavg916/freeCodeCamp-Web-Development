# Basic CSS Notes

## Add Borders Around Your Elements

- CSS borders have properties like style, color and width.
- For example, if we wanted to create a red, 5 pixel border around an HTML element, we could use this class:

```html
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
  }
</style>
```

- Create a class called thick-green-border. This class should add a 10px, solid, green border around an HTML element. Apply the class to your cat photo.

## Add a Negative Margin to an Element

- An element's margin controls the amount of space between an element's border and surrounding elements.
- If you set an element's margin to a negative value, the element will grow larger.

## Override Styles in Subsequent CSS

- Our "pink-text" class overrode our body element's CSS declaration!
- We just proved that our classes will override the body element's CSS. So the next logical question is, what can we do to override our pink-text class?
- Create an additional CSS class called blue-text that gives an element the color blue. Make sure it's below your pink-text class declaration.
- Apply the blue-text class to your h1 element in addition to your pink-text class, and let's see which one wins.
- Applying multiple class attributes to a HTML element is done with a space between them like this:

```html
class="class1 class2"
```

- Note: It doesn't matter which order the classes are listed in the HTML element.
- However, the order of the class declarations in the <style> section is what is important. The second declaration will always take precedence over the first. Because .blue-text is declared second, it overrides the attributes of .pink-text

## Override All Other Styles by using Important

- Yay! We just proved that inline styles will override all the CSS declarations in your style element.
- But wait. There's one last way to override CSS. This is the most powerful method of all. But before we do it, let's talk about why you would ever want to override CSS.
- In many situations, you will use CSS libraries. These may accidentally override your own CSS. So when you absolutely need to be sure that an element has specific CSS, you can use !important
- Let's go all the way back to our pink-text class declaration. Remember that our pink-text class was overridden by subsequent class declarations, id declarations, and inline styles.
- Let's add the keyword !important to your pink-text element's color declaration to make 100% sure that your h1 element will be pink.
- An example of how to do this is:

```css
color: red !important;
```

## Attach a Fallback value to a CSS Variable

- When using your variable as a CSS property value, you can attach a fallback value that your browser will revert to if the given variable is invalid.
- Note: This fallback is not used to increase browser compatibility, and it will not work on IE browsers. Rather, it is used so that the browser has a color to display if it cannot find your variable.
- Here's how you do it:

```css
background: var(--penguin-skin, black);
```

- This will set background to black if your variable wasn't set. Note that this can be useful for debugging.
