# Responsive Web Design Notes

## Contents

- Basic HTML
- Basic CSS
- Applied Visual Design
- Applied Accessibility
- Responsive Web Design Principles
- CSS Flexbox & CSS Grid
- Responsive Web Design Projects

### Projects

- [Tribute Page](https://github.com/abhinavg916/tribute-page)
- [Survey Form](https://github.com/abhinavg916/survey-form)
- [Product Landing Page](https://github.com/abhinavg916/product-landing-page)
- [Technical Documentation Page](https://github.com/abhinavg916/technical-documentation-page)
- [Personal Portfolio Webpage](https://github.com/abhinavg916/personal-portfolio-page)

### Certificate

![RWDC](https://github.com/abhinavg916/freeCodeCamp-web-development/blob/master/Responsive%20Web%20Design/Responsive%20Web%20Design.png)

---

## Basic HTML and HTML5 Notes

### Use HTML5 to Require a Field

- You can require specific form fields so that your user will not be able to submit your form until he or she has filled them out.

- For example, if you wanted to make a text input field required, you can just add the attribute required within your input element, like this: `<input type="text" required>`

### Create a Set of Radio Buttons

- You can use radio buttons for questions where you want the user to only give you one answer out of multiple options.

- Radio buttons are a type of input.

- Each of your radio buttons can be nested within its own label element. By wrapping an input element inside of a label element it will automatically associate the radio button input with the label element surrounding it.

- All related radio buttons should have the same name attribute to create a radio button group. By creating a radio group, selecting any single radio button will automatically deselect the other buttons within the same group ensuring only one answer is provided by the user.

- Here's an example of a radio button:

```html
<label> <input type="radio" name="indoor-outdoor" />Indoor </label>
```

- It is considered best practice to set a for attribute on the label element, with a value that matches the value of the id attribute of the input element. This allows assistive technologies to create a linked relationship between the label and the child input element. For example:

```html
<label for="indoor"> <input id="indoor" type="radio" name="indoor-outdoor" />Indoor </label>
```

---

## Basic CSS Notes

### Add Borders Around Your Elements

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

### Add a Negative Margin to an Element

- An element's margin controls the amount of space between an element's border and surrounding elements.
- If you set an element's margin to a negative value, the element will grow larger.

### Override Styles in Subsequent CSS

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

### Override All Other Styles by using Important

- Yay! We just proved that inline styles will override all the CSS declarations in your style element.
- But wait. There's one last way to override CSS. This is the most powerful method of all. But before we do it, let's talk about why you would ever want to override CSS.
- In many situations, you will use CSS libraries. These may accidentally override your own CSS. So when you absolutely need to be sure that an element has specific CSS, you can use !important
- Let's go all the way back to our pink-text class declaration. Remember that our pink-text class was overridden by subsequent class declarations, id declarations, and inline styles.
- Let's add the keyword !important to your pink-text element's color declaration to make 100% sure that your h1 element will be pink.
- An example of how to do this is:

```css
color: red !important;
```

### Attach a Fallback value to a CSS Variable

- When using your variable as a CSS property value, you can attach a fallback value that your browser will revert to if the given variable is invalid.
- Note: This fallback is not used to increase browser compatibility, and it will not work on IE browsers. Rather, it is used so that the browser has a color to display if it cannot find your variable.
- Here's how you do it:

```css
background: var(--penguin-skin, black);
```

- This will set background to black if your variable wasn't set. Note that this can be useful for debugging.

---

## Applied Visual Design Notes

### Use the text-transform Property to Make Text Uppercase

- The text-transform property in CSS is used to change the appearance of text. It's a convenient way to make sure text on a webpage appears consistently, without having to change the text content of the actual HTML elements.

- The following table shows how the different text-transformvalues change the example text "Transform me".

```
Value - Result
lowercase - "transform me"
uppercase - "TRANSFORM ME"
capitalize - "Transform Me"
initial - Use the default value inherit Use the text-transform
value from the parent element
none - Default: Use the original text
```

### Set the font-weight for Multiple Heading Elements

- You set the font-size of each heading tag in the last challenge, here you'll adjust the font-weight.
- The font-weight property sets how thick or thin characters are in a section of text.

```
Set the font-weight of the h1 tag to 800.
Set the font-weight of the h2 tag to 600.
Set the font-weight of the h3 tag to 500.
Set the font-weight of the h4 tag to 400.
Set the font-weight of the h5 tag to 300.
Set the font-weight of the h6 tag to 200.
```

### Set the line-height of Paragraphs

- CSS offers the line-height property to change the height of each line in a block of text. As the name suggests, it changes the amount of vertical space that each line of text gets.
- Add a line-height property to the p tag and set it to 25px.

### Move a Relatively Positioned Element with CSS Offsets

- The CSS offsets of top or bottom, and left or right tell the browser how far to offset an item relative to where it would sit in the normal flow of the document. You're offsetting an element away from a given spot, which moves the element away from the referenced side (effectively, the opposite direction). As you saw in the last challenge, using the top offset moved the h2 downwards. Likewise, using a left offset moves an item to the right.
  ![](gif)
- Use CSS offsets to move the h2 15 pixels to the right and 10 pixels up.

```css
h2 {
  position: relative;
  left: 15px;
  /* right-offset: 15px; */ /* Wrong */
  bottom: 10px;
  /* bottom-offset: 10px; */ /* Wrong */
}
```

### Lock an Element to its Parent with Absolute Positioning

- The next option for the CSS position property is absolute, which locks the element in place relative to its parent container. Unlike the relative position, this removes the element from the normal flow of the document, so surrounding items ignore it. The CSS offset properties (top or bottom and left or right) are used to adjust the position.
- One nuance with absolute positioning is that it will be locked relative to its closest positioned ancestor. If you forget to add a position rule to the parent item, (this is typically done using position: relative;), the browser will keep looking up the chain and ultimately default to the body tag.

### Learn about Complementary Colors

- Color theory and its impact on design is a deep topic and only the basics are covered in the following challenges. On a website, color can draw attention to content, evoke emotions, or create visual harmony. Using different combinations of colors can really change the look of a website, and a lot of thought can go into picking a color palette that works with your content.
- The color wheel is a useful tool to visualize how colors relate to each other - it's a circle where similar hues are neighbors and different hues are farther apart. When two colors are opposite each other on the wheel, they are called complementary colors. They have the characteristic that if they are combined, they "cancel" each other out and create a gray color. However, when placed side-by-side, these colors appear more vibrant and produce a strong visual contrast.
- Some examples of complementary colors with their hex codes are:

```
red (#FF0000) and cyan (#00FFFF)
green (#00FF00) and magenta (#FF00FF)
blue (#0000FF) and yellow (#FFFF00)
```

- This is different than the outdated RYB color model that many of us were taught in school, which has different primary and complementary colors. Modern color theory uses the additive RGB model (like on a computer screen) and the subtractive CMY(K) model (like in printing). Read here for more information on this complex subject.
- There are many color picking tools available online that have an option to find the complement of a color.
- Note: For all color challenges: Using color can be a powerful way to add visual interest to a page. However, color alone should not be used as the only way to convey important information because users with visual impairments may not understand that content. This issue will be covered in more detail in the Applied Accessibility challenges.

### Learn about Tertiary Colors

- Computer monitors and device screens create different colors by combining amounts of red, green, and blue light. This is known as the RGB additive color model in modern color theory. Red (R), green (G), and blue (B) are called primary colors. Mixing two primary colors creates the secondary colors cyan (G + B), magenta (R + B) and yellow (R + G). You saw these colors in the Complementary Colors challenge. These secondary colors happen to be the complement to the primary color not used in their creation, and are opposite to that primary color on the color wheel. For example, magenta is made with red and blue, and is the complement to green.
- Tertiary colors are the result of combining a primary color with one of its secondary color neighbors. For example, within the RGB color model, red (primary) and yellow (secondary) make orange (tertiary). This adds six more colors to a simple color wheel for a total of twelve.
- There are various methods of selecting different colors that result in a harmonious combination in design. One example that can use tertiary colors is called the split-complementary color scheme. This scheme starts with a base color, then pairs it with the two colors that are adjacent to its complement. The three colors provide strong visual contrast in a design, but are more subtle than using two complementary colors.
- Here are three colors created using the split-complement scheme:

```
Color	Hex Code
orange	#FF7F00
cyan	#00FFFF
raspberry	#FF007F
```

### Adjust the Hue of a Color

- Colors have several characteristics including hue, saturation, and lightness. CSS3 introduced the hsl() property as an alternative way to pick a color by directly stating these characteristics.
- Hue is what people generally think of as 'color'. If you picture a spectrum of colors starting with red on the left, moving through green in the middle, and blue on right, the hue is where a color fits along this line. In hsl(), hue uses a color wheel concept instead of the spectrum, where the angle of the color on the circle is given as a value between 0 and 360.
- Saturation is the amount of gray in a color. A fully saturated color has no gray in it, and a minimally saturated color is almost completely gray. This is given as a percentage with 100% being fully saturated.
- Lightness is the amount of white or black in a color. A percentage is given ranging from 0% (black) to 100% (white), where 50% is the normal color.
- Here are a few examples of using hsl() with fully-saturated, normal lightness colors:

```
Color	HSL
red	hsl(0, 100%, 50%)
yellow	hsl(60, 100%, 50%)
green	hsl(120, 100%, 50%)
cyan	hsl(180, 100%, 50%)
blue	hsl(240, 100%, 50%)
magenta	hsl(300, 100%, 50%)
```

### Adjust the Tone of a Color

- The hsl() option in CSS also makes it easy to adjust the tone of a color. Mixing white with a pure hue creates a tint of that color, and adding black will make a shade. Alternatively, a tone is produced by adding gray or by both tinting and shading. Recall that the 's' and 'l' of hsl() stand for saturation and lightness, respectively. The saturation percent changes the amount of gray and the lightness percent determines how much white or black is in the color. This is useful when you have a base hue you like, but need different variations of it.
- All elements have a default background-color of transparent. Our nav element currently appears to have a cyan background, because the element behind it has a background-color set to cyan. Add a background-color to the nav element so it uses the same cyan hue, but has 80% saturation and 25% lightness values to change its tone and shade.

### Create a Gradual CSS Linear Gradient

- Applying a color on HTML elements is not limited to one flat hue. CSS provides the ability to use color transitions, otherwise known as gradients, on elements. This is accessed through the background property's linear-gradient() function. - Here is the general syntax:

```css
background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);
```

- The first argument specifies the direction from which color transition starts - it can be stated as a degree, where 90deg makes a vertical gradient and 45deg is angled like a backslash. The following arguments specify the order of colors used in the gradient.
- Example:

```css
background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));
```

### Use the CSS Transform scale Property to Change the Size of an Element

- To change the scale of an element, CSS has the transform property, along with its scale() function. The following code example doubles the size of all the paragraph elements on the page:

```css
p {
  transform: scale(2);
}
```

- Increase the size of the element with the id of ball2 to 1.5 times its original size.

### Use the CSS Transform Property skewX to Skew an Element Along the X-Axis

- The next function of the transform property is skewX(), which skews the selected element along its X (horizontal) axis by a given degree.
- The following code skews the paragraph element by -32 degrees along the X-axis.

```css
p {
  transform: skewX(-32deg);
}
```

- Skew the element with the id of bottom by 24 degrees along the X-axis by using the transform property.

### Create a Graphic Using CSS

- By manipulating different selectors and properties, you can make interesting shapes. One of the easier ones to try is a crescent moon shape. For this challenge you need to work with the box-shadow property that sets the shadow of an element, along with the border-radius property that controls the roundness of the element's corners.
- You will create a round, transparent object with a crisp shadow that is slightly offset to the side - the shadow is actually going to be the moon shape you see.
- In order to create a round object, the border-radius property should be set to a value of 50%.
- You may recall from an earlier challenge that the box-shadow property takes values for offset-x, offset-y, blur-radius, spread-radius and a color value in that order. The blur-radius and spread-radius values are optional.
- Manipulate the square element in the editor to create the moon shape. First, change the background-color to transparent, then set the border-radius property to 50% to make the circular shape. Finally, change the box-shadow property to set the offset-x to 25px, the offset-y to 10px, blur-radius to 0, spread-radius to 0, and color to blue.

### Learn How the CSS @keyframes and animation Properties Work

- To animate an element, you need to know about the animation properties and the @keyframes rule. The animation properties control how the animation should behave and the @keyframes rule controls what happens during that animation. There are eight animation properties in total. This challenge will keep it simple and cover the two most important ones first:
  animation-name sets the name of the animation, which is later used by @keyframes to tell CSS which rules go with which animations.
- animation-duration sets the length of time for the animation.
- @keyframes is how to specify exactly what happens within the animation over the duration. This is done by giving CSS properties for specific "frames" during the animation, with percentages ranging from 0% to 100%. If you compare this to a movie, the CSS properties for 0% is how the element displays in the opening scene. The CSS properties for 100% is how the element appears at the end, right before the credits roll. Then CSS applies the magic to transition the element over the given duration to act out the scene. Here's an example to illustrate the usage of @keyframes and the animation properties:

```css
#anim {
  animation-name: colorful;
  animation-duration: 3s;
}

@keyframes colorful {
  0% {
    background-color: blue;
  }
  100% {
    background-color: yellow;
  }
}
```

- For the element with the anim id, the code snippet above sets the animation-name to colorful and sets the animation-duration to 3 seconds. Then the @keyframes rule links to the animation properties with the name colorful. It sets the color to blue at the beginning of the animation (0%) which will transition to yellow by the end of the animation (100%). You aren't limited to only beginning-end transitions, you can set properties for the element for any percentage between 0% and 100%.
- Create an animation for the element with the id rect, by setting the animation-name to rainbow and the animation-duration to 4 seconds. Next, declare a @keyframes rule, and set the background-color at the beginning of the animation (0%) to blue, the middle of the animation (50%) to green, and the end of the animation (100%) to yellow.

### Modify Fill Mode of an Animation

- That's great, but it doesn't work right yet. Notice how the animation resets after 500ms has passed, causing the button to revert back to the original color. You want the button to stay highlighted.
- This can be done by setting the animation-fill-mode property to forwards. The animation-fill-mode specifies the style applied to an element when the animation has finished. You can set it like so:

```
animation-fill-mode: forwards;
```

### Animate Elements Continually Using an Infinite Animation Count

- The previous challenges covered how to use some of the animation properties and the @keyframes rule. Another animation property is the animation-iteration-count, which allows you to control how many times you would like to loop through the animation. Here's an example:

```
animation-iteration-count: 3;
```

- In this case the animation will stop after running 3 times, but it's possible to make the animation run continuously by setting that value to infinite.
- To keep the ball bouncing on the right on a continuous loop, change the animation-iteration-count property to infinite.

### Make a CSS Heartbeat using an Infinite Animation Count

- Here's one more continuous animation example with the animation-iteration-count property that uses the heart you designed in a previous challenge.
- The one-second long heartbeat animation consists of two animated pieces. The heart elements (including the :before and :after pieces) are animated to change size using the transform property, and the background div is animated to change its color using the background property.
- Keep the heart beating by adding the animation-iteration-count property for both the back class and the heart class and setting the value to infinite. The heart:before and heart:after selectors do not need any animation properties.

### Learn How Bezier Curves Work

- The last challenge introduced the animation-timing-function property and a few keywords that change the speed of an animation over its duration. CSS offers an option other than keywords that provides even finer control over how the animation plays out, through the use of Bezier curves.
- In CSS animations, Bezier curves are used with the cubic-bezier function. The shape of the curve represents how the animation plays out. The curve lives on a 1 by 1 coordinate system. The X-axis of this coordinate system is the duration of the animation (think of it as a time scale), and the Y-axis is the change in the animation.
- The cubic-bezier function consists of four main points that sit on this 1 by 1 grid: p0, p1, p2, and p3. p0 and p3 are set for you - they are the beginning and end points which are always located respectively at the origin (0, 0) and (1, 1). You set the x and y values for the other two points, and where you place them in the grid dictates the shape of the curve for the animation to follow. This is done in CSS by declaring the x and y values of the p1 and p2 "anchor" points in the form: (x1, y1, x2, y2). Pulling it all together, here's an example of a Bezier curve in CSS code:

```
animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
```

- In the example above, the x and y values are equivalent for each point (x1 = 0.25 = y1 and x2 = 0.75 = y2), which if you remember from geometry class, results in a line that extends from the origin to point (1, 1). This animation is a linear change of an element during the length of an animation, and is the same as using the linear keyword. In other words, it changes at a constant speed.
- For the element with the id of ball1, change the value of the animation-timing-function property from linear to its equivalent cubic-bezier function value. Use the point values given in the example above.

---

## Applied Accessibility Notes

### Improve Accessibility of Audio Content with the audio Element

- HTML5's audio element gives semantic meaning when it wraps sound or audio stream content in your markup. Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing. This can be done with nearby text on the page or a link to a transcript.
- The audio tag supports the controls attribute. This shows the browser default play, pause, and other controls, and supports keyboard functionality. This is a boolean attribute, meaning it doesn't need a value, its presence on the tag turns the setting on.
- Here's an example:

```html
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```

- Note: Multimedia content usually has both visual and auditory components. It needs synchronized captions and a transcript so users with visual and/or auditory impairments can access it. Generally, a web developer is not responsible for creating the captions or transcript, but needs to know to include them.
- Time to take a break from Camper Cat and meet fellow camper Zersiax (@zersiax), a champion of accessibility and a screen reader user. To hear a clip of his screen reader in action, add an audio element after the p. Include the controls attribute. Then place a source tag inside the audio tags with the src attribute set to "https://s3.amazonaws.com/freecodecamp/screen-reader.mp3" and type attribute set to "audio/mpeg".
- Note: The audio clip may sound fast and be difficult to understand, but that is a normal speed for screen reader users.

### Improve Chart Accessibility with the figure Element

- HTML5 introduced the figure element, along with the related figcaption. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. This gives a two-fold accessibility boost by both semantically grouping related content, and providing a text alternative that explains the figure.
- For data visualizations like charts, the caption can be used to briefly note the trends or conclusions for users with visual impairments. Another challenge covers how to move a table version of the chart's data off-screen (using CSS) for screen reader users.
- Here's an example - note that the figcaption goes inside the figure tags and can be combined with other elements:

```html
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick" />
  <br />
  <figcaption>Master Camper Cat demonstrates proper form of a roundhouse kick.</figcaption>
</figure>
```

- Camper Cat is hard at work creating a stacked bar chart showing the amount of time per week to spend training in stealth, combat, and weapons. Help him structure his page better by changing the div tag he used to a figure tag, and the p tag that surrounds the caption to a figcaption tag.

### Improve Form Field Accessibility with the label Element

- Improving accessibility with semantic HTML markup applies to using both appropriate tag names as well as attributes. The next several challenges cover some important scenarios using attributes in forms.
- The label tag wraps the text for a specific form control item, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The for attribute on a label tag explicitly associates that label with the form control and is used by screen readers.
- You learned about radio buttons and their labels in a lesson in the Basic HTML section. In that lesson, we wrapped the radio button input element inside a label element along with the label text in order to make the text clickable. Another way to achieve this is by using the for attribute as explained in this lesson.
- The value of the for attribute must be the same as the value of the id attribute of the form control. Here's an example:

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" />
</form>
```

- Camper Cat expects a lot of interest in his thoughtful blog posts and wants to include an email sign up form. Add a for attribute on the email label that matches the id on its input field.

### Wrap Radio Buttons in a fieldset Element for Better Accessibility

- The next form topic covers accessibility of radio buttons. Each choice is given a label with a for attribute tying to the id of the corresponding item as covered in the last challenge. Since radio buttons often come in a group where the user must choose one, there's a way to semantically show the choices are part of a set.
- The fieldset tag surrounds the entire grouping of radio buttons to achieve this. It often uses a legend tag to provide a description for the grouping, which is read by screen readers for each choice in the fieldset element.
- The fieldset wrapper and legend tag are not necessary when the choices are self-explanatory, like a gender selection. Using a label with the for attribute for each radio button is sufficient.
- Here's an example:

```html
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one" />
    <label for="one">Choice One</label><br />
    <input id="two" type="radio" name="items" value="two" />
    <label for="two">Choice Two</label><br />
    <input id="three" type="radio" name="items" value="three" />
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```

- Camper Cat wants information about the ninja level of his users when they sign up for his email list. He's added a set of radio buttons and learned from our last lesson to use label tags with for attributes for each choice. Go Camper Cat! However, his code still needs some help. Change the div tag surrounding the radio buttons to a fieldset tag, and change the p tag inside it to a legend.

### Standardize Times with the HTML5 datetime Attribute

- Continuing with the date theme, HTML5 also introduced the time element along with a datetime attribute to standardize times. This is an inline element that can wrap a date or time on a page. A valid format of that date is held by the datetime attribute. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.
- Here's an example:

```html
<p>
  Master Camper Cat officiated the cage match between Goro and Scorpion
  <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.
</p>
```

- Camper Cat's Mortal Kombat survey results are in! Wrap a time tag around the text "Thursday, September 15<sup>th</sup>" and add a datetime attribute to it set to "2016-09-15".

### Make Elements Only Visible to a Screen Reader by Using Custom CSS

- Have you noticed that all of the applied accessibility challenges so far haven't used any CSS? This is to show the importance of a logical document outline, and using semantically meaningful tags around your content before introducing the visual design aspect.
- However, CSS's magic can also improve accessibility on your page when you want to visually hide content meant only for screen readers. This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. CSS is used to position the screen reader-only elements off the visual area of the browser window.
- Here's an example of the CSS rules that accomplish this:

```css
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}
```

- Note: The following CSS approaches will NOT do the same thing: `display: none; or visibility: hidden;` hides content for everyone, including screen reader users
- Zero values for pixel sizes, such as width: 0px; height: 0px; removes that element from the flow of your document, meaning screen readers will ignore it

### Improve Readability with High Contrast Text

- Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves the readability of your content, but what exactly does "sufficient" mean?
- The Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. The ratio is calculated by comparing the relative luminance values of two colors. This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. There are many contrast checking tools available online that calculate this ratio for you.
- Camper Cat's choice of light gray text on a white background for his recent blog post has a 1.5:1 contrast ratio, making it hard to read. Change the color of the text from the current gray (#D3D3D3) to a darker gray (#636363) to improve the contrast ratio to 6:1.

### Avoid Colorblindness Issues by Using Sufficient Contrast

- Color is a large part of visual design, but its use introduces two accessibility issues. First, color alone should not be used as the only way to convey important information because screen reader users won't see it. Second, foreground and background colors need sufficient contrast so colorblind users can distinguish them.
- Previous challenges covered having text alternatives to address the first issue. The last challenge introduced contrast checking tools to help with the second. The WCAG-recommended contrast ratio of 4.5:1 applies for color use as well as gray-scale combinations.
- Colorblind users have trouble distinguishing some colors from others - usually in hue but sometimes lightness as well. You may recall the contrast ratio is calculated using the relative luminance (or lightness) values of the foreground and background colors.
- In practice, the 4.5:1 contrast ratio can be reached by shading (adding black to) the darker color and tinting (adding white to) the lighter color. Darker shades on the color wheel are considered to be shades of blues, violets, magentas, and reds, whereas lighter tinted colors are oranges, yellows, greens, and blue-greens.
- Camper Cat is experimenting with using color for his blog text and background, but his current combination of a greenish background-color with maroon text color has a 2.5:1 contrast ratio. You can easily adjust the lightness of the colors since he declared them using the CSS hsl() property (which stands for hue, saturation, lightness) by changing the third argument. Increase the background-color lightness value from 35% to 55%, and decrease the color lightness value from 20% to 15%. This improves the contrast to 5.9:1.

### Avoid Colorblindness Issues by Carefully Choosing Colors that Convey Information

- There are various forms of colorblindness. These can range from a reduced sensitivity to a certain wavelength of light to the inability to see color at all. The most common form is a reduced sensitivity to detect greens.
- For example, if two similar green colors are the foreground and background color of your content, a colorblind user may not be able to distinguish them. Close colors can be thought of as neighbors on the color wheel, and those combinations should be avoided when conveying important information.
- Note: Some online color picking tools include visual simulations of how colors appear for different types of colorblindness. These are great resources in addition to online contrast checking calculators.

### Give Links Meaning by Using Descriptive Link Text

- Screen reader users have different options for what type of content their device reads. This includes skipping to (or over) landmark elements, jumping to the main content, or getting a page summary from the headings. Another option is to only hear the links available on a page.
- Screen readers do this by reading the link text, or what's between the anchor (a) tags. Having a list of "click here" or "read more" links isn't helpful. Instead, you should use brief but descriptive text within the a tags to provide more meaning for these users.
- The link text that Camper Cat is using is not very descriptive without the surrounding context. Move the anchor (a) tags so they wrap around the text "information about batteries" instead of "Click here".

### Make Links Navigable with HTML Access Keys

- HTML offers the accesskey attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.
- HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with interactive ones. This includes links, buttons, and form controls.
- Here's an example:

```html
<button accesskey="b">Important Button</button>
```

- Camper Cat wants the links around the two blog article titles to have keyboard shortcuts so his site's users can quickly navigate to the full story. Add an accesskey attribute to both links and set the first one to "g" (for Garfield) and the second one to "c" (for Chuck Norris).

### Use tabindex to Add Keyboard Focus to an Element

- The HTML tabindex attribute has three distinct functions relating to an element's keyboard focus. When it's on a tag, it indicates that element can be focused on. The value (an integer that's positive, negative, or zero) determines the behavior.
- Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page. It's in the same order as the elements come in the HTML source markup. This same functionality can be given to other elements, such as div, span, and p, by placing a tabindex="0" attribute on them. Here's an example:

```html
<div tabindex="0">I need keyboard focus!</div>
```

- Note: A negative tabindex value (typically -1) indicates that an element is focusable, but is not reachable by the keyboard. This method is generally used to bring focus to content programmatically (like when a div used for a pop-up window is activated), and is beyond the scope of these challenges.
- Camper Cat created a new survey to collect information about his users. He knows input fields automatically get keyboard focus, but he wants to make sure his keyboard users pause at the instructions while tabbing through the items. Add a tabindex attribute to the p tag and set its value to "0". Bonus - using tabindex also enables the CSS pseudo-class :focus to work on the p tag.

### Use tabindex to Specify the Order of Keyboard Focus for Several Elements

- The tabindex attribute also specifies the exact tab order of elements. This is achieved when the value of the attribute is set to a positive number of 1 or higher.
- Setting a tabindex="1" will bring keyboard focus to that element first. Then it cycles through the sequence of specified tabindex values (2, 3, etc.), before moving to default and tabindex="0" items.
- It's important to note that when the tab order is set this way, it overrides the default order (which uses the HTML source). This may confuse users who are expecting to start navigation from the top of the page. This technique may be necessary in some circumstances, but in terms of accessibility, take care before applying it.
- Here's an example:

```html
<div tabindex="1">I get keyboard focus, and I get it first!</div>
<div tabindex="2">I get keyboard focus, and I get it second!</div>
```

- Camper Cat has a search field on his Inspirational Quotes page that he plans to position in the upper right corner with CSS. He wants the search input and submit input form controls to be the first two items in the tab order. Add a tabindex attribute set to "1" to the search input, and a tabindex attribute set to "2" to the submit input.

---

## Responsive Web Design Principles Notes

### Make an Image Responsive

- Making images responsive with CSS is actually very simple. You just need to add these properties to an image:

```css
img {
  max-width: 100%;
  height: auto;
}
```

- The max-width of 100% will make sure the image is never wider than the container it is in, and the height of auto will make the image keep its original aspect ratio.
- Add the style rules to the responsive-img class to make it responsive. It should never be wider than its container (in this case, it's the preview window) and it should keep its original aspect ratio. After you have added your code, resize the preview to see how your images behave.

### Use a Retina Image for Higher Resolution Displays

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

### Make Typography Responsive

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

---

## CSS Grid Notes

### Use CSS Grid units to Change the Size of Columns and Rows

- You can use absolute and relative units like px and em in CSS Grid to define the size of rows and columns. You can use these as well:
- fr: sets the column or row to a fraction of the available space,
- auto: sets the column or row to the width or height of its content automatically,
- %: adjusts the column or row to the percent width of its container.
- Here's the code that generates the output in the preview:

```css
grid-template-columns: auto 50px 10% 2fr 1fr;
```

- This snippet creates five columns. The first column is as wide as its content, the second column is 50px, the third column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, two are allocated for the fourth column, and one for the fifth.

### Add Gaps Faster with grid-gap

- grid-gap is a shorthand property for grid-row-gap and grid-column-gap from the previous two challenges that's more convenient to use. If grid-gap has one value, it will create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.

### Create Flexible Layouts Using auto-fill

-The repeat function comes with an option called auto-fill. This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. You can create flexible layouts when combining auto-fill with minmax, like this:

```css
repeat(auto-fill, minmax(60px, 1fr));
```

- When the container changes size, this setup keeps inserting 60px columns and stretching them until it can insert another one. Note: If your container can't fit all your items on one row, it will move them down to a new one.

### Flexible Layouts Using auto-fit

- auto-fit works almost identically to auto-fill. The only difference is that when the container's size exceeds the size of all the items combined, auto-fill keeps inserting empty rows or columns and pushes your items to the side, while auto-fit collapses those empty rows or columns and stretches your items to fit the size of the container.
- Note: If your container can't fit all your items on one row, it will move them down to a new one.

### Create Grids within Grids

- Turning an element into a grid only affects the behavior of its direct descendants. So by turning a direct descendant into a grid, you have a grid within a grid.
- For example, by setting the display and grid-template-columns properties of the element with the item3 class, you create a grid within your grid.
- Turn the element with the item3 class into a grid with two columns with a width of auto and 1fr using display and grid-template-columns.
