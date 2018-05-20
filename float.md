## Float positioning scheme

### Floats exhibit several special behaviors:

* Floats are taken out of the normal flow during layout, and hence they do not affect the vertical positioning of block-level elements.
* Floats are aligned to either the left or right outer edge of their container.
* Floats are stacked starting from either the left or right edge, and are stacked in the order they appear in markup. In other words, for right-floated boxes, the first right-floated box is positioned on the right edge of the box that contains it and the second right-floated box is positioned immediately left of the first box. source
* Floats can, however, affect the current and subsequent elements' inline-level content's line boxes. Specifically, any current and subsequent line boxes are shortened to make space for the float.
* Because floats are not in the normal flow, they do not normally affect parent height. This is one reason why the "clearfix" technique was developed.
* Floats can be cleared using the clear property.

## Float clearing

### The clear property can take one of the following values:

* left: Requires that the top border edge of the box be below the bottom outer edge of any left-floating boxes that resulted from elements earlier in the source document.
* right: Requires that the top border edge of the box be below the bottom outer edge of any right-floating boxes that resulted from elements earlier in the source document.
* both: Both float: left and float: right must be cleared as above
* none: No constraint on the box's position with respect to floats.

## The clearfix

### A clearfix combines several desirable properties into one class:

* it prevents the floats within the clearfixed parent element from affecting line boxes in other elements that follow the clearfixed element
* it causes the floats within the clearfixed parent element to be taken into account when calculating that element's height

### There are three ways to accomplish this:

* explicitly adding an element with clear: both at the end of the parent
* adding an element with clear: both using pseudo-elements at the end of the parent
* making the parent element establish a new formatting context using a property such as overflow: hidden or overflow: auto
