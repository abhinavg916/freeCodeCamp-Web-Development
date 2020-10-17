# CSS Grid Notes

## Use CSS Grid units to Change the Size of Columns and Rows

- You can use absolute and relative units like px and em in CSS Grid to define the size of rows and columns. You can use these as well:
- fr: sets the column or row to a fraction of the available space,
- auto: sets the column or row to the width or height of its content automatically,
- %: adjusts the column or row to the percent width of its container.
- Here's the code that generates the output in the preview:

```css
grid-template-columns: auto 50px 10% 2fr 1fr;
```

- This snippet creates five columns. The first column is as wide as its content, the second column is 50px, the third column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, two are allocated for the fourth column, and one for the fifth.

## Add Gaps Faster with grid-gap

- grid-gap is a shorthand property for grid-row-gap and grid-column-gap from the previous two challenges that's more convenient to use. If grid-gap has one value, it will create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.

## Create Flexible Layouts Using auto-fill

-The repeat function comes with an option called auto-fill. This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. You can create flexible layouts when combining auto-fill with minmax, like this:

```css
repeat(auto-fill, minmax(60px, 1fr));
```

- When the container changes size, this setup keeps inserting 60px columns and stretching them until it can insert another one. Note: If your container can't fit all your items on one row, it will move them down to a new one.

## Flexible Layouts Using auto-fit

- auto-fit works almost identically to auto-fill. The only difference is that when the container's size exceeds the size of all the items combined, auto-fill keeps inserting empty rows or columns and pushes your items to the side, while auto-fit collapses those empty rows or columns and stretches your items to fit the size of the container.
- Note: If your container can't fit all your items on one row, it will move them down to a new one.

## Create Grids within Grids

- Turning an element into a grid only affects the behavior of its direct descendants. So by turning a direct descendant into a grid, you have a grid within a grid.
- For example, by setting the display and grid-template-columns properties of the element with the item3 class, you create a grid within your grid.
- Turn the element with the item3 class into a grid with two columns with a width of auto and 1fr using display and grid-template-columns.
