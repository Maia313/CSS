### Nesting

```css
nav {
  background-color: red;
}

nav ul {
  list-style: none;
}

nav ul li {
  display: inline-block;
}
```
becomes instead

```scss
nav {
  background-color: red;

  ul {
    list-style: none;

    li {
      display: inline-block;
    }
  }
}
```

### Mixin
 As features are added to browsers, CSS rules using them may need vendor prefixes. Consider "box-shadow":

```css
div {
  -webkit-box-shadow: 0px 0px 4px #fff;
  -moz-box-shadow: 0px 0px 4px #fff;
  -ms-box-shadow: 0px 0px 4px #fff;
  box-shadow: 0px 0px 4px #fff;
}
```

It's a lot of typing to re-write this rule for all the elements that have a box-shadow, or to change each value to test 
different effects.

Mixins are like functions for CSS. Here is how to write one:

```scss
@mixin box-shadow($x, $y, $blur, $c){
  -webkit-box-shadow: $x, $y, $blur, $c;
  -moz-box-shadow: $x, $y, $blur, $c;
  -ms-box-shadow: $x, $y, $blur, $c;
  box-shadow: $x, $y, $blur, $c;
}
```

The definition starts with @mixin followed by a custom name. The parameters (the $x, $y, $blur, and $c in the example above) 
are optional.

Now any time a box-shadow rule is needed, only a single line calling the mixin replaces having to type all the vendor prefixes. 
A mixin is called with the @include directive:

```scss
div {
  @include box-shadow(0px, 0px, 4px, #fff);
}
```

```scss
//Clearfix Mixin
@mixin clearfix() { 
   &:before,
   &:after {
      content: "";
      display: table;
   }
   &:after {
      clear: both;
   }
}

//Add Clearfix to row
.row {
   @include clearfix();
}
```

### @If directive

The @if directive in Sass is useful to test for a specific case - it works just like the if statement in JavaScript.

```scss
@mixin make-bold($bool) {
  @if $bool == true {
    font-weight: bold;
  }
}
```

```scss
@mixin text-effect($val) {
  @if $val == danger {
    color: red;
  }
  @else if $val == alert {
    color: yellow;
  }
  @else if $val == success {
    color: green;
  }
  @else {
    color: black;
  }
}
```

### @For directive

The @for directive adds styles in a loop, very similar to a for loop in JavaScript.

@for is used in two ways: "start through end" or "start to end". The main difference is that "start to end" excludes the 
end number, and "start through end" includes the end number.

Here's a start through end example:

```scss
@for $i from 1 through 12 {
  .col-#{$i} { width: 100%/12 * $i; }
}
```

The #{$i} part is the syntax to combine a variable (i) with text to make a string. When the Sass file is converted to CSS, 
it looks like this:

```css
.col-1 {
  width: 8.33333%;
}

.col-2 {
  width: 16.66667%;
}

...

.col-12 {
  width: 100%;
}
```
This is a powerful way to create a grid layout. Now you have twelve options for column widths available as CSS classes.

### @Each directive

Sass also offers the @each directive which loops over each item in a list or map.

On each iteration, the variable gets assigned to the current value from the list or map.

```scss
@each $color in blue, red, green {
  .#{$color}-text {color: $color;}
}
```

```scss
$colors: (color1: blue, color2: red, color3: green);

@each $key, $color in $colors {
  .#{$color}-text {color: $color;}
}
```

**Note** that the `$key` variable is needed to reference the keys in the map. Otherwise, the compiled CSS would have color1, color2... in it.


### Partials

**Note** that the underscore is not needed in the import statement - Sass understands it is a partial. Once a partial is imported into a file, all variables, mixins, and other code are available to use.

### Extend

Sass has a feature called extend that makes it easy to borrow the CSS rules from one element and build upon them in another.

For example, the below block of CSS rules style a .panel class. It has a background-color, height and border.

```scss
.panel{
  background-color: red;
  height: 70px;
  border: 2px solid green;
}
```

Now you want another panel called .big-panel. It has the same base properties as .panel, but also needs a width and font-size.

It's possible to copy and paste the initial CSS rules from .panel, but the code becomes repetitive as you add more types of panels.

The extend directive is a simple way to reuse the rules written for one element, then add more for another:
```scss
.big-panel{
  @extend .panel;
  width: 150px;
  font-size: 2em;
}
```
The `.big-panel` will have the same properties as `.panel` in addition to the new styles.
