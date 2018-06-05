
# Keyframes

Each animation needs to be defined with the `@keyframes` at-rule which is then called with the `animation` property, like so:
```css
.element {
  animation: pulse 5s infinite;
}

@keyframes pulse {
  0% {
    background-color: #001F3F;
  }
  100% {
    background-color: #FF4136;
  }
}
```
* Sub-properties
  + `animation-name`: declares the name of the @keyframes at-rule to manipulate.
  + `animation-duration`: the length of time it takes for an animation to complete one cycle.
  + `animation-timing-function`: establishes preset acceleration curves such as ease or linear.
  + `animation-delay`: the time between the element being loaded and the start of the animation sequence.
  + `animation-direction`: sets the direction of the animation after the cycle. Its default resets on each cycle.
  + `animation-iteration-count`: the number of times the animation should be performed.
  + `animation-fill-mode`: sets which values are applied before/after the animation.
    For example, you can set the last state of the animation to remain on screen, or you can set it to switch back to before when the animation began.
  + `animation-play-state`: pause/play the animation.
  
  ```css
  @keyframes stretch {
  /* declare animation actions here */
  }

  .element {
    animation-name: stretch;
    animation-duration: 1.5s; 
    animation-timing-function: ease-out; 
    animation-delay: 0s;
    animation-direction: alternate;
    animation-iteration-count: infinite;
    animation-fill-mode: none;
    animation-play-state: running; 
  }

  /*
    is the same as:
  */

  .element {
    animation:  stretch 1.5s ease-out 0s alternate infinite none running;
  }
  ```
