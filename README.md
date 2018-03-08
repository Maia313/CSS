# CSS

##Box positioning in CSS
   _the three main positioning schemes in CSS: normal flow, floats and absolute positioning
   _normal flow concepts, anonymous box generation, formatting context, line boxes and alignment within line boxes
   _float concepts, such as float order, clearfix and float interactions with parent height
   
 ####Normal flow
   -three formatting contexts: the block, inline and relative formatting contexts
   -floats, which interact with normal flow in their own way and form the basis of most modern CSS grid frameworks
   -absolute positioning, which deals with absolute and fixed elements relative to the normal flow
   
   The positioning scheme has impact on the x and y-axis positioning of elements. All elements belong to the normal flow by default unless they are specifically removed from normal flow - typically by setting the float property or the position property.
   
   | Attribute 	| Default value 	| Purpose                                          |
   |------------|:---------------:|:------------------------------------------------:|
   | display 	  | block or inline | Determines the layout algorithm to use           |
   | position 	| static 	        | Controls the positioning of an element           |
   | float 	    | none 	          | Allows other elements to float around the element|
