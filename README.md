# CSS

## Box positioning in CSS
   >The three main positioning schemes in CSS: **`normal flow`**, **`floats`** and **`absolute positioning`**
   >
   > normal flow concepts, anonymous box generation, formatting context, line boxes and alignment within line boxes
   >
   > float concepts, such as float order, clearfix and float interactions with parent height
   
 #### Normal flow
   > three formatting contexts: **`the block`**, **`inline`** and **`relative`** formatting contexts
   > **`floats`**, which interact with normal flow in their own way and form the basis of most modern CSS grid frameworks
   > **`absolute positioning`**, which deals with absolute and fixed elements relative to the normal flow
   
   The positioning scheme has impact on the `x-` and `y-axis` positioning of elements. All elements belong to the normal flow by default unless they are specifically removed from normal flow - typically by setting the float property or the position property.
   
   | **`Attribute`** 	| **`Default value`** 	| **`Purpose`**                                         |
   |--------------------|:---------------------:|:-----------------------------------------------------:|
   | display 	         | block or inline       | Determines the layout algorithm to use                |
   | position 	         | static 	            | Controls the positioning of an element                |
   | float 	            | none 	               | Allows other elements to float around the element     |

=====

#### Float properties
*
*

#### Flexbox properties
* **For parent**
   `display`
   `flex-direction`
   `flex-wrap`
   `flex-flow`
   `justify-content`
   `align-items`
   `align-content`
   
* **For children**
   `order`
   `flex-grow`
   `flex-shrink`
   `flex-basis`
   `flex`
   `align-self`

#### Grid properties
*
*
