### Layout rules
-----

>There are *inline* and *block* elements in CSS normal flow.
>The relative positioning of *block* and *inline* elements is not actually determined by the element's display property! It's actually determined by the formatting context, which is influenced by the siblings of the element.

>*z-index* is not absolute across the document, but rather relative to a stacking context

>There are in fact at least 5 different box models, with subtle differences in how content dimensions and **margin: auto** are treated

>**Box positioning** in CSS covers how the boxes that HTML elements generate are positioned relative to each other:

The three main positioning schemes in CSS: **normal flow**, **floats** and **absolute positioning**
normal flow concepts, such as anonymous box generation, formatting context, line boxes and alignment within line boxes
float concepts, such as float order, clearfix and float interactions with parent height

>**Box sizing** in CSS discusses the box model, but more importantly how the box model varies across the different >positioning schemes in CSS. Concretely, height, width and margins are calculated using completely different mechanisms, and >you can only understand these calculations by knowing the positioning scheme and calculation mechanism in use.

>**Additional properties that influence positioning** covers additional mechanisms that influence box positioning, such >as:

 + margin collapsing
 + negative margins
 + overflow
 + max-width, max-height, min-width, min-height
 + stacking contexts and the z-index property
 + how pseudo elements impact layout
 + the CSS3 box-sizing property

>**Flexbox** discusses the CSS 3 flexbox layout mode.

>**CSS layout** - tricks and layout techniques takes what we have learned and applies it to several practical problems. 
>It also contains small quiz-like questions to test you understanding of layout in contexts such as:

 + horizontal and vertical centering
 + how CSS grid frameworks work
 + multicolumn layout
 + common gotchas and layout tricks.
 
 
 ----
 
 >the highest level abstraction for CSS layout is the positioning scheme. Once a positioning scheme has been determined, 
 >it can be further modified by specific layout modes, such as display: table or display: inline-table.
