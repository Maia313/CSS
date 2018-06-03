## Flexbox

> You start by having a container and child divs
>
```css
.container {
  display: flex;
  flex-direction: row; // by default, more common /* row-reverse|column|column-reverse */
  justify-content: flex-start;// by default /* flex-start|flex-end center|space-around|space-between|space-evenly */
  align-items: stretch; // by default /* center|flex-start|flex-end|baseline|initial|inherit */
  flex-wrap: nowrap; // by default /* wrap */
}
```

```css
.child-div {
  margin-left:auto; // will add margin on the left side of the div
  align-self:auto; // by default /* stretch|center|flex-start|flex-end|baseline|initial|inherit */
}
```

```css
.container > div {
  flex: 1; // shorthand, same as flex: 1 1 0; or
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 0;
  /*flex is a shortcut for flex-grow, flex-shrink, flex-basis */
}
```
------

### Axis
> A flexbox container always has **`direction`**
> 

#### Main axis
> By default it is horizontal 
>
> It goes from left to right along the row

#### Cross axis
> Is vertical 
>
> It goes from top to bottom along the column


### Wrapping

> **`nowrap`** means that the containers child divs will be placed on one row or column, 
> they will not extend the nr of rows/columns.

### Order

> Set on child divs to change the order in which they appear in the layout
>


* Adding `display: flex` to an element turns it into a `flex container`. This makes it possible to align any children of that element into rows or columns. You do this by adding the `flex-direction` property to the parent item and setting it to `row` or `column`. Creating a row will align the children horizontally, and creating a column will align the children vertically.

Sometimes the flex items within a flex container do not fill all the space in the container. It is common to want to tell CSS how to align and space out the flex items a certain way. Fortunately, the `justify-content` property has several options to do this. But first, there is some important terminology to understand before reviewing those options.

Here is a useful image showing a row to illustrate the concepts below.

Recall that setting a flex container as a row places the flex items side-by-side from left-to-right. A flex container set as a column places the flex items in a vertical stack from top-to-bottom. For each, the direction the flex items are arranged is called the `main axis`. For a `row, this is a horizontal line that cuts through each item`. And for a `column, the main axis is a vertical line through the items`.

There are `several options for how to space the flex items along the line that is the main axis`. One of the most commonly used is `justify-content`: `center`;, which aligns all the flex items to the center inside the flex container. Others options include:

   * `flex-start`: aligns items to the start of the flex container. For a row, this pushes the items to the left of the container. For a column, this pushes the items to the top of the container.
   * `flex-end`: aligns items to the end of the flex container. For a row, this pushes the items to the right of the container. For a column, this pushes the items to the bottom of the container.
   * `space-between`: aligns items to the center of the main axis, with extra space placed between the items. The first and last items are pushed to the very edge of the flex container. For example, in a row the first item is against the left side of the container, the last item is against the right side of the container, then the other items between them are spaced evenly.
   * `space-around`: similar to space-between but the first and last items are not locked to the edges of the container, the space is distributed around all the items
