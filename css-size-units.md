## Size units

#### `The four different viewport units are:`

   * `vw`: 10vw would be 10% of the viewport's width.
   * `vh`: 3vh would be 3% of the viewport's height.
   * `vmin`: 70vmin would be 70% of the viewport's smaller dimension (height vs. width).
   * `vmax`: 100vmax would be 100% of the viewport's bigger dimension (height vs. width).

----

#### `Grid units`

You can use `absolute` and `relative units` like `px` and `em` in CSS Grid to define the size of rows and columns. You can use these as well:

* `fr`: sets the column or row to a fraction of the available space,

* `auto`: sets the column or row to the width or height of its content automatically,

* `%`: adjusts the column or row to the percent width of its container.

Here's the code that generates the output in the preview:
```css
    grid-template-columns: auto 50px 10% 2fr 1fr;
```
This snippet creates 5 columns. The 1st column is as wide as its content, the 2nd column is 50px, the 3rd column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, 2 are allocated for the 4th column, and one for the 5th.
