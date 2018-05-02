
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
 
 ### Positioning schemes
 
 CSS 2.1 defines three positioning schemes, which are:

* **normal** flow, which consists of three formatting contexts: the block, inline and relative formatting contexts
* **floats**, which interact with normal flow in their own way and form the basis of most modern CSS grid frameworks
* **absolute positioning**, which deals with absolute and fixed elements relative to the normal flow

**All elements belong to the normal flow by default unless they are specifically removed from normal flow - typically by setting the float property or the position property.**

### There are actually two aspects of layout that are at play:

 * how the box of an element is sized and aligned, which is primarily controlled by the display property (and width, height and margin).
 * how elements within a particular parent element are positioned relative to each other
 
 > Boxes in the normal flow belong to a formatting context, which may be block or inline, but not both simultaneously. 
 > Block-level boxes participate in a block formatting context. Inline-level boxes participate in an inline formatting context. 

### Block-level
> Block-level elements are those elements of the source document that are formatted visually as blocks (e.g., paragraphs). 
> The following values of the 'display' property make an element block-level: 'block', 'list-item', and 'table'.
> Block-level boxes are boxes that participate in a block formatting context. Each block-level element generates a principal >block-level box that contains descendant boxes and generated content and is also the box involved in any positioning scheme. 
> Some block-level elements may generate additional boxes in addition to the principal box [for example,]: 'list-item' elements. These additional boxes are placed with respect to the principal box.

### Inline-level
>Inline-level elements are those elements of the source document that do not form new blocks of content; the content is >distributed in lines (e.g., emphasized pieces of text within a paragraph, inline images, etc.). The following values of the >'display' property make an element inline-level: 'inline', 'inline-table', and 'inline-block'. Inline-level elements generate >inline-level boxes, which are boxes that participate in an inline formatting context.

>An inline box is one that is both inline-level and whose contents participate in its containing inline formatting context. A >non-replaced element with a 'display' value of 'inline' generates an inline box. Inline-level boxes that are not inline boxes >(such as replaced inline-level elements, inline-block elements, and inline-table elements) are called atomic inline-level >boxes because they participate in their inline formatting context as a single opaque box. Source

## Normal flow: block formatting

**In a box formatting context, boxes are laid out vertically, and that every box's left outer edge will touch the left outer edge of the containing block (even in the presence of floats).**

## Normal flow: inline formatting

In an inline formatting context, boxes are laid out horizontally, one after the other, beginning at the top of a containing block. Horizontal margins, borders, and padding are respected between these boxes.

The boxes may be aligned vertically in different ways: their bottoms or tops may be aligned, or the baselines of text within them may be aligned. The rectangular area that contains the boxes that form a line is called a **line box.**

**Horizontal alignment within line boxes: text-align**

**Vertical alignment within line boxes: vertical-align**

### Inline boxes have:

+ a font size, which determines the size of the text glyphs
+ a line height, which determines the height of the inline box (in absolute terms or relative to the font size)
+ a baseline, which is a position defined by the font, and on which the bottom edges of most glyphs / characters are aligned (excluding characters such as q and g, which have descenders/ascenders - parts that extend below/above the baseline alignment)

### Each line box has:

+ a font size, which is inherited from the parent
+ a height defined by the heights and alignments of inline boxes in the line box
+ a baseline, which is defined by a "strut" (except in rare cases involving vertical-align: top / bottom): an invisible, zero-width inline box with the element's font and line height properties
