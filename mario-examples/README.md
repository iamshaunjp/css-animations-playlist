File created by Kai Lin Cheng - edited by myself for spelling typos to test GitHub
##################################################################
## CSS Animation Tutorial #4 - KEYFRAMES
##################################################################

  -   define animations, tell css how we want animation to work,
      which properties to change, how and when to do it
  -   use diff keyframe block for diff elements
  -   similar to functions for animations

  Example: Mario Cart
  ```css
  /*// ELEMENTS TO ANIMATE //*/
  .mario {
    position: absolute;
    top: -40px;
    left: 0px;
    /*This is tying the animation to the element*/
    animation-name: drive;
    animation-duration: 3s;
  }

  /*
  this is how you define an animation the name of the animation is drive
  from{}  goes from this state to{}  ends up at this state
  */
  @keyframes drive{
    from{ transform: translateX(0) }
    to{ transform: translateX(700px) }
  }
  ```

Source: [CSS Animation Tutorial #4 - KEYFRAMES](https://www.youtube.com/watch?v=PjR97QzOrJM)

##################################################################
## CSS Animation Tutorial #5 - Animation Fill Mode
##################################################################

  Animation Fill Modes Values:
  1. none
     -   do nothing outside the animation window
     -   goes back to where it is

  2. forwards
     -   at the end of the animation it will set the element to be
         at to{}
     -   the element will just stay at where the animation ended

  3. backwards
     -   this is the default
     -   at the end of the animation, it will be at where it started

  4. both
     -   this will follow the rules of forward and backwards

  5. initial
  6. inherit

  -   animation-delay: 2s;  will run the animation after the specified time delated

Source: [CSS Animation Tutorial #5 - Animation Fill Mode](https://www.youtube.com/watch?v=irJXZnA3g5U)

##################################################################
## CSS Animations Tutorials #6 - Repeating Animations
##################################################################

  -   animation-iteration-count: 3;
  -   will tell the animation to repeat 3 times

```css
/*// ELEMENTS TO ANIMATE //*/
.mario {
  position: absolute;
  top: -40px;
  left: 0px;
  animation-name: drive;
  animation-duration: 1s;
  animation-fill-mode: forwards;
  animation-iteration-count: 3;
}

/*// KEYFRAMES //*/
@keyframes drive{
  from{ transform: translateX(-100px) }
  to{ transform: translateX(1600px) }
}
```

-   to make the animation keep repeating, use infinite instead of 3
-
```css
.mario {
  animation-iteration-count: infinite;
}
```

Source: [CSS Animations Tutorials #6 - Repeating Animations](https://www.youtube.com/watch?v=DCgcgXF0Fe0)

##################################################################
## CSS Animation Tutorial #7 - Animation Direction
##################################################################

  animation-direction Options:
    1. normal
      -   default value
    2. reverse
      -   animation will play in reverse direction
    3. alternate
      -   animation will play normal then reverse
    4. alternate-reverse
      -   animation will play reverse then normal

```css
.luigi {
  position: absolute;
  top: 100px;
  left: 0;
  animation-name: drive;
  animation-duration: 5s;
  animation-fill-mode: both;
  animation-iteration-count: infinite;
  animation-direction: reverse;
}

/*// KEYFRAMES //*/
@keyframes drive{
  from{ transform: translateX(-100px) }
  to{ transform: translateX(1600px) }
}
```

Source: [CSS Animation Tutorial #7 - Animation Direction](https://www.youtube.com/watch?v=Bm_36uWbV_I)

##################################################################
## CSS Animation Tutorial #8 - Animation Timing Functions
##################################################################

  -   Animation-Timing function determines rate the animation occurs
  -   the default value is ease if you don't specify anything
  -   cubic-bezier() lets you custom determine the rate of the animation
  -   You can use this [helpful website](http://cubic-bezier.com/#.24,-0.07,.93,1.93), to get 4 numbers for the cubic-bezier

Source: [CSS Animation Tutorial #8 - Animation Timing Functions](https://www.youtube.com/watch?v=t2zoXRXpCWs)

##################################################################
## CSS Animation Tutorial #9 - Animation Shorthand
##################################################################

  -   there is short hand for writing animations

  Standard
  ```css
  .cloud:nth-child(2) {
    width: 300px;
    top:0;
    animation-name: wind;
    animation-duration: 4s;
    animation-timing-function: ease-in;
    animation-direction: alternate-reverse
  }
  ```

  Shorthand Version
  ```css
  .cloud:nth-child(2) {
    width: 300px;
    top:0;
    animation: wind 4s ease-in infinite alternate-reverse;
  }
  ```

  -   This makes life way easier

Source: [CSS Animation Tutorial #9 - Animation Shorthand](https://www.youtube.com/watch?v=aGuq1euvbYc)

##################################################################
## CSS Animation Tutorial #10 - Chaining Animations
##################################################################

   -   Chaining Animations are really easy
   -   You just separate the animations by a comma in the animation attribute and you are set to go

   Example:
   ```css
   .mario {
     position: absolute;
     top: -40px;
     left: 0;
     animation: jump 0.3s ease,
                drive 3s 0.3s linear both infinite;
   }
   ```
   What Just Happened?
  -   Here Mario will jump then he will drive
  -   The jump will only happen once


   -   You can't chain more than 2 animations
   -   If you want to chain more than 2 animations, you should use states

  Example:
  ```css
  @keyframes jump{
    0%{ top: -40px; }
    50%{ top: -200px;}
    100%{ top: -40px; }
  }
  ```
  What Just Happened?
  -   at  0 % of that animation, the element is at the position of -40px top
  -   at 50% of the animation, the element is at the position of -200px top
  -   at 100% of the animation, the element is at the position of -40px top
  -   In conclusion this creates an animation like the element jumped


Source: [CSS Animation Tutorial #10 - Chaining Animations](https://www.youtube.com/watch?v=B0tClxmu_IQ)
