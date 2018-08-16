```css
#element1{
  color:white;
  background-color:red; 
  position:absolute; 
  top:30; 
  left:40;
}

#element2 {
  color:white;
  background-color:blue; 
  position:relative; 
  top:20; 
  left:50; 
  z-index:1;
}
```
4 properties will determine placement on the page — `position`, `top`, `left`, and `z-index`. 
The **position** property can have one of 3 values—`static`, `relative`, or `absolute`. The **default position is static**.
`position:static` means that the blocked-off area will stay inline as normal HTML and **cannot be changed by the top and left properties**. 

### _In order to change the position, we must declare the position to be either relative or absolute._

`position:absolute` means that the top and left coordinates are defined absolutely. That is, the coordinate values are relative to the top left corner of the webpage. In the above example, top:100 would be 100 pixels from the top of the webpage and left:100 would be 100 pixels from the left of the web page. 

However, if the element is nested inside another positioned element, then the absolutely positioned element will treat the top left corner of its parent element as the starting point instead of the top left corner of the web page.
