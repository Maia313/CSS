## Flexbox

> You start by having a container and child divs
>
```
.container {
  display: flex;
  flex-direction: row; /* by default, more common row-reverse column column-reverse */
  justify-content: flex-start;/* by default  flex-start flex-end center space-around space-between space-evenly */
}
```

```
.child-div {
  margin-left:auto; //will add margin on the left side of the div
}
```

```
.container > div {
  flex: 1;
  /*flex is a shortcut for flex-grow, flex-shrink, flex-basis */
}
```

### Axis
> A flexbox container always has direction
> 

#### Main axis
> By default it is horizontal 
>
> It goes from left to right along the row

#### Cross axis
> Is vertical 
>
> It goes from top to bottom along the column
