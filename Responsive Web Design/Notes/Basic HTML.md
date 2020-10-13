# Basic HTML and HTML5 Notes

## Use HTML5 to Require a Field

- You can require specific form fields so that your user will not be able to submit your form until he or she has filled them out.

- For example, if you wanted to make a text input field required, you can just add the attribute required within your input element, like this: `<input type="text" required>`

## Create a Set of Radio Buttons

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
<label for="indoor">
  <input id="indoor" type="radio" name="indoor-outdoor" />Indoor
</label>
```
