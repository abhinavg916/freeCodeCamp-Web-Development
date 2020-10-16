# Applied Accessibility Notes

## Improve Accessibility of Audio Content with the audio Element

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

## Improve Chart Accessibility with the figure Element

- HTML5 introduced the figure element, along with the related figcaption. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. This gives a two-fold accessibility boost by both semantically grouping related content, and providing a text alternative that explains the figure.
- For data visualizations like charts, the caption can be used to briefly note the trends or conclusions for users with visual impairments. Another challenge covers how to move a table version of the chart's data off-screen (using CSS) for screen reader users.
- Here's an example - note that the figcaption goes inside the figure tags and can be combined with other elements:

```html
<figure>
  <img
    src="roundhouseDestruction.jpeg"
    alt="Photo of Camper Cat executing a roundhouse kick"
  />
  <br />
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

- Camper Cat is hard at work creating a stacked bar chart showing the amount of time per week to spend training in stealth, combat, and weapons. Help him structure his page better by changing the div tag he used to a figure tag, and the p tag that surrounds the caption to a figcaption tag.

## Improve Form Field Accessibility with the label Element

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

## Wrap Radio Buttons in a fieldset Element for Better Accessibility

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

## Standardize Times with the HTML5 datetime Attribute

- Continuing with the date theme, HTML5 also introduced the time element along with a datetime attribute to standardize times. This is an inline element that can wrap a date or time on a page. A valid format of that date is held by the datetime attribute. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.
- Here's an example:

```html
<p>
  Master Camper Cat officiated the cage match between Goro and Scorpion
  <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.
</p>
```

- Camper Cat's Mortal Kombat survey results are in! Wrap a time tag around the text "Thursday, September 15<sup>th</sup>" and add a datetime attribute to it set to "2016-09-15".

## Make Elements Only Visible to a Screen Reader by Using Custom CSS

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

## Improve Readability with High Contrast Text

- Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves the readability of your content, but what exactly does "sufficient" mean?
- The Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. The ratio is calculated by comparing the relative luminance values of two colors. This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. There are many contrast checking tools available online that calculate this ratio for you.
- Camper Cat's choice of light gray text on a white background for his recent blog post has a 1.5:1 contrast ratio, making it hard to read. Change the color of the text from the current gray (#D3D3D3) to a darker gray (#636363) to improve the contrast ratio to 6:1.

## Avoid Colorblindness Issues by Using Sufficient Contrast

- Color is a large part of visual design, but its use introduces two accessibility issues. First, color alone should not be used as the only way to convey important information because screen reader users won't see it. Second, foreground and background colors need sufficient contrast so colorblind users can distinguish them.
- Previous challenges covered having text alternatives to address the first issue. The last challenge introduced contrast checking tools to help with the second. The WCAG-recommended contrast ratio of 4.5:1 applies for color use as well as gray-scale combinations.
- Colorblind users have trouble distinguishing some colors from others - usually in hue but sometimes lightness as well. You may recall the contrast ratio is calculated using the relative luminance (or lightness) values of the foreground and background colors.
- In practice, the 4.5:1 contrast ratio can be reached by shading (adding black to) the darker color and tinting (adding white to) the lighter color. Darker shades on the color wheel are considered to be shades of blues, violets, magentas, and reds, whereas lighter tinted colors are oranges, yellows, greens, and blue-greens.
- Camper Cat is experimenting with using color for his blog text and background, but his current combination of a greenish background-color with maroon text color has a 2.5:1 contrast ratio. You can easily adjust the lightness of the colors since he declared them using the CSS hsl() property (which stands for hue, saturation, lightness) by changing the third argument. Increase the background-color lightness value from 35% to 55%, and decrease the color lightness value from 20% to 15%. This improves the contrast to 5.9:1.

## Avoid Colorblindness Issues by Carefully Choosing Colors that Convey Information

- There are various forms of colorblindness. These can range from a reduced sensitivity to a certain wavelength of light to the inability to see color at all. The most common form is a reduced sensitivity to detect greens.
- For example, if two similar green colors are the foreground and background color of your content, a colorblind user may not be able to distinguish them. Close colors can be thought of as neighbors on the color wheel, and those combinations should be avoided when conveying important information.
- Note: Some online color picking tools include visual simulations of how colors appear for different types of colorblindness. These are great resources in addition to online contrast checking calculators.

## Give Links Meaning by Using Descriptive Link Text

- Screen reader users have different options for what type of content their device reads. This includes skipping to (or over) landmark elements, jumping to the main content, or getting a page summary from the headings. Another option is to only hear the links available on a page.
- Screen readers do this by reading the link text, or what's between the anchor (a) tags. Having a list of "click here" or "read more" links isn't helpful. Instead, you should use brief but descriptive text within the a tags to provide more meaning for these users.
- The link text that Camper Cat is using is not very descriptive without the surrounding context. Move the anchor (a) tags so they wrap around the text "information about batteries" instead of "Click here".

## Make Links Navigable with HTML Access Keys

- HTML offers the accesskey attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.
- HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with interactive ones. This includes links, buttons, and form controls.
- Here's an example:

```html
<button accesskey="b">Important Button</button>
```

- Camper Cat wants the links around the two blog article titles to have keyboard shortcuts so his site's users can quickly navigate to the full story. Add an accesskey attribute to both links and set the first one to "g" (for Garfield) and the second one to "c" (for Chuck Norris).

## Use tabindex to Add Keyboard Focus to an Element

- The HTML tabindex attribute has three distinct functions relating to an element's keyboard focus. When it's on a tag, it indicates that element can be focused on. The value (an integer that's positive, negative, or zero) determines the behavior.
- Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page. It's in the same order as the elements come in the HTML source markup. This same functionality can be given to other elements, such as div, span, and p, by placing a tabindex="0" attribute on them. Here's an example:

```html
<div tabindex="0">I need keyboard focus!</div>
```

- Note: A negative tabindex value (typically -1) indicates that an element is focusable, but is not reachable by the keyboard. This method is generally used to bring focus to content programmatically (like when a div used for a pop-up window is activated), and is beyond the scope of these challenges.
- Camper Cat created a new survey to collect information about his users. He knows input fields automatically get keyboard focus, but he wants to make sure his keyboard users pause at the instructions while tabbing through the items. Add a tabindex attribute to the p tag and set its value to "0". Bonus - using tabindex also enables the CSS pseudo-class :focus to work on the p tag.

## Use tabindex to Specify the Order of Keyboard Focus for Several Elements

- The tabindex attribute also specifies the exact tab order of elements. This is achieved when the value of the attribute is set to a positive number of 1 or higher.
- Setting a tabindex="1" will bring keyboard focus to that element first. Then it cycles through the sequence of specified tabindex values (2, 3, etc.), before moving to default and tabindex="0" items.
- It's important to note that when the tab order is set this way, it overrides the default order (which uses the HTML source). This may confuse users who are expecting to start navigation from the top of the page. This technique may be necessary in some circumstances, but in terms of accessibility, take care before applying it.
- Here's an example:

```html
<div tabindex="1">I get keyboard focus, and I get it first!</div>
<div tabindex="2">I get keyboard focus, and I get it second!</div>
```

- Camper Cat has a search field on his Inspirational Quotes page that he plans to position in the upper right corner with CSS. He wants the search input and submit input form controls to be the first two items in the tab order. Add a tabindex attribute set to "1" to the search input, and a tabindex attribute set to "2" to the submit input.
