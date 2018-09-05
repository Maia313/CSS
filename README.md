

## Box positioning in CSS
   > The 3 main positioning schemes in CSS: **`normal flow`**, **`floats`** and **`absolute positioning`**
     normal flow concepts, anonymous box generation, formatting context, line boxes and alignment within line boxes
     float concepts, such as float order, clearfix and float interactions with parent height
   
 #### Normal flow
   > 3 formatting contexts: **`the block`**, **`inline`** and **`relative`** formatting contexts
   > **`floats`**, which interact with normal flow in their own way and form the basis of most modern CSS grid frameworks
   > **`absolute positioning`**, which deals with absolute and fixed elements relative to the normal flow
   
   The positioning scheme has impact on the `x-` and `y-axis` positioning of elements. All elements belong to the normal flow by default unless they are specifically removed from normal flow - typically by setting the `float` or the `position` property.
   
   | **`Attribute`** 	| **`Default value`** 	| **`Purpose`**                                         |
   |--------------------|:---------------------:|:-----------------------------------------------------:|
   | display 	         | block or inline       | Determines the layout algorithm to use                |
   | position 	         | static 	            | Controls the positioning of an element                |
   | float 	            | none 	               | Allows other elements to float around the element     |

----

#### Float properties
* + `float`
  + `clear`
* Techniques for Clearing Floats
  + The `Empty Div Method` is, quite literally, an empty div. `<div style="clear: both;"></div>`.
  + The `Overflow Method` relies on setting the overflow CSS property on a parent element. If this property is set to `auto` or `hidden` on the parent element, the parent will expand to contain the `floats`, effectively clearing it for succeeding elements.
  + The `Easy Clearing Method` uses a clever CSS pseudo selector (`:after`) to clear floats. Rather than setting the `overflow` on the parent, you apply an additional class like "`clearfix`" to it.
 

#### Flexbox properties
* **For parent elements**
   + `display`
   + `flex-direction`
   + `flex-wrap`
   + `flex-flow` - shorthand for `flex-direction` and `flex-wrap`, which define the flex container's main and cross axes.               Default is row nowrap
   + `justify-content` - For `main axis`, aligns individual items
   + `align-items` - For `cross axis`
   + `align-content` - aligns a flex container's lines within when there is extra space in the cross-axis
   
* **For child elements**
   + `order`
   + `flex-grow`
   + `flex-shrink`
   + `flex-basis`
   + `flex` - This is the shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined. The second and third parameters (`flex-shrink` and `flex-basis`) are `optional`. Default is `0 1 auto`.
   + `align-self` - This allows the default alignment (or the one specified by `align-items`) to be overridden for individual `flex items`.

#### Grid properties
* **For parent elements**
   + `display`
   + `grid-template-columns`, `grid-template-rows`
   + `grid-template-areas`
   + `grid-template` - A shorthand for setting `grid-template-rows`, `grid-template-columns`, and `grid-template-areas` in a single declaration.
   + `grid-column-gap`, `grid-row-gap` - Specifies the size of the grid lines. 
   + `grid-gap` - A shorthand for `grid-row-gap` and `grid-column-gap`
   + `justify-items` - Aligns grid items along the `inline (row) axis` (as opposed to `align-items` which aligns along the `block (column) axis`). This value applies to all grid items inside the container
   + `align-items`
   + `place-items` - sets both the `align-items` and `justify-items` properties in a single declaration
   + `justify-content` - aligns the grid along the `inline (row) axis` (as opposed to `align-content` which aligns the grid along the block (column) axis).
   + `align-content`
   + `place-content` - sets both the `align-content` and `justify-content` properties in a single declaration.
   + `grid-auto-columns`, `grid-auto-rows`-Specifies the size of any `auto-generated grid tracks` (aka `implicit grid tracks`). `Implicit tracks` get created when there are more grid items than cells in the grid or when a grid item is placed outside of the `explicit grid`.
   + `grid-auto-flow` - If you have grid items that you don't explicitly place on the grid, the auto-placement algorithm kicks in to automatically place the items. This property controls how the auto-placement algorithm works.
   + `grid` - A shorthand for setting all of the following properties in a single declaration: `grid-template-rows`, `grid-template-columns`, `grid-template-areas`, `grid-auto-rows`, `grid-auto-columns`, and `grid-auto-flow` (Note: You can only specify the `explicit` or the `implicit grid` properties in a single grid declaration).
   
* **For child elements**
   + `grid-column-start`, `grid-column-end`, `grid-row-start`, `grid-row-end`
   + `grid-column`, `grid-row` - Shorthand for `grid-column-start + grid-column-end`, and `grid-row-start + grid-row-end`, respectively.
   + `grid-area` - Gives an item a name so that it can be referenced by a template created with the grid-template-areas property. Alternatively, this property can be used as an even shorter shorthand for `grid-row-start + grid-column-start + grid-row-end + grid-column-end`.
   + `justify-self` - Aligns a grid item inside a cell along the `inline (row) axis` (as opposed to `align-self` which aligns along the `block (column) axis`). This value applies to a grid item inside a single cell.
   + `align-self` - Aligns a grid item inside a cell along the `block (column) axis`. This value applies to the content inside a single grid item.
   + `place-self` - sets both the `align-self` and `justify-self` properties in a single declaration. 
 
