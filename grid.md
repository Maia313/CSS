## Grid 

> Container and child divs
>

```css
.container {
    display: grid;
    grid-template-columns: 100px auto 100px;
    grid-template-rows: 50px 50px;
    grid-gap: 3px;
}
```
or
```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 50px 50px;
    grid-gap: 3px;
}
```
or
```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 50px);
    grid-gap: 3px;
}
```
or
```css
.container {
    display: grid;
    grid-template: repeat(2, 50px) / repeat(3, 1fr);
    grid-gap: 3px;
}
```
#### For the child div we can specify where it should start and where it should end
------
```css
.header {
    grid-column-start: 1;
    grid-column-end: 3;
}
//or
.header {
    grid-column: 1 / 3;
}
```

### Template areas

> The areas have to be rectangles otherwise they brake the entire layout

```css
.container {
    height: 100%;
    display: grid;
    grid-gap: 3px;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: 40px auto 40px;
    grid-template-areas: 
        ". h h h h h h h h h h ."
        "m c c c c c c c c c c c"
        ". f f f f f f f f f f .";
}
```
You can group cells of your grid together into an area and give the area a custom name. Do this by using `grid-template-areas` on the container like this:
```css
    grid-template-areas:
    "header header header"
    "advert content content"
    "footer footer footer";
```
The code above merges the top three cells together into an area named header, the bottom three cells into a footer area, and it makes two areas in the middle row; `advert` and `content`.

**Note**
Every word in the code represents a cell and every pair of quotation marks represent a row.

In addition to custom labels, you can use a `period (.)` to designate an empty cell in the grid.

### Grid areas

After creating an areas template for your grid container, as shown in the previous challenge, you can place an item in your custom area by referencing the name you gave it. To do this, you use the `grid-area` property on an item like this:
```css
    .item1 { grid-area: header; }
```
This lets the grid know that you want the item1 class to go in the area named header. In this case, the item will use the entire top row because that whole row is named as the header area.

The `grid-area` property can be used in another way. If your grid doesn't have an `areas template` to reference, you can create an area on the fly for an item to be placed like this:
```css
    item1 { grid-area: 1/1/2/4; }
```
This is using the line numbers you learned about earlier to define where the area for this item will be. The numbers in the example above represent these values:
```css
    grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;
```

### Using minmax

```css
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    grid-template-rows: 100px 100px;
}
```
There's another built-in function to use with `grid-template-columns` and `grid-template-rows` called `minmax`. It's used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for your item. Here is an example:
```css
    grid-template-columns: 100px minmax(50px, 200px);
```
In the code above, `grid-template-columns` is set to create `two columns; the first is 100px wide, and the second has the minimum width of 50px and the maximum width of 200px`.

### Implicit rows

```css
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    grid-auto-rows: 100px;
}
```

### Named lines

```css
.container {
    height: 100%; 
    display: grid;
    grid-gap: 3px;
    grid-template-columns: [main-start] 1fr [content-start] 5fr [content-end main-end];
    grid-template-rows: [main-start] 40px [content-start] auto [content-end] 40px [main-end]; 
}
```

### Grid gap

`grid-gap` is a shorthand property for `grid-row-gap` and `grid-column-gap` from the previous two challenges that's more convenient to use. If `grid-gap` has one value, it will a create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.

### Repeat function

When you used grid-template-columns and grid-template-rows to define the structure of a grid, you entered a value for each row or column you created.

Lets say you want a grid with 100 rows of the same height. It isn't very practical to insert 100 values individually. Fortunately, there's a better way - by using the `repeat function` to specify the number of times you want your column or row to be repeated, followed by a comma and the value you want to repeat.

Here's an example that would create the `100 row grid, each row at 50px tall`.
```css
    grid-template-rows: repeat(100, 50px);
```
You can also repeat multiple values with the `repeat function`, and insert the function amongst other values when defining a grid structure.
```css
    grid-template-columns: repeat(2, 1fr 50px) 20px;
```
This translates to:
```css
    grid-template-columns: 1fr 50px 1fr 50px 20px;
```
--**Note**
1fr 50px is repeated twice followed by 20px.

### Auto-fill

The `repeat function` comes with a option called `auto-fill`. This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. You can create flexible layouts when combining `auto-fill` with `minmax`.

In the preview, grid-template-columns is set to
```css
    repeat(auto-fill, minmax(60px, 1fr));
```
When the container changes size, this setup keeps inserting 60px columns and stretching them until it can insert another one.

--**Note**
If your container can't fit all your items on one row, it will move them down to a new one.

### Auto-fit

`auto-fit` works almost identical to `auto-fill`. The only **difference** is that when the container's size exceeds the size of all the items combined, `auto-fill` keeps inserting empty rows or columns and pushes your items to the side, while `auto-fit` collapses those empty rows or columns and stretches your items to fit the size of the container.

--**Note**
If your container can't fit all your items on one row, it will move them down to a new one.

### Justify-content & align-content
### Justify-items & align-items

In CSS Grid, the content of each item is located in a box which is referred to as a cell. You can align the content's position within its cell horizontally using the `justify-self` property on a grid item. By default, this property has a value of `stretch`, which will make the content fill the whole width of the cell. This CSS Grid property accepts other values as well:

* `start`: aligns the content at the left of the cell,
* `center`: aligns the content in the center of the cell,
* `end`: aligns the content at the right of the cell.

### Auto-fit & auto-fill
### Grid & flexbox can be used together
