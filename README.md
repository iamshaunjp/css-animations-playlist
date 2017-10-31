## CSS Animation Tutorial

Learning CSS Animation from [The Net Ninja](https://www.youtube.com/watch?v=jgw82b5Y2MU)

## CSS Animation Tutorial#2 Transforms

Transform transform web elements to different things

Transform's options:
  1. matrix
  -   combines all 2D transform methods into one
  -   syntax of matrix( scaleX(), skewY(), skewX(), scaleY(), translateX(), translateY())
  ```css
  div {
    -ms-transform: matrix(1, -0.3, 0, 1, 0, 0); /* IE 9 */
    -webkit-transform: matrix(1, -0.3, 0, 1, 0, 0); /* Safari */
    transform: matrix(1, -0.3, 0, 1, 0, 0);
  }
  ```

  2. translate
   -   move element from one location to another
   -   move on X-axis use translateX()
   -   move on Y-Axis use translateY()
   ```css
    img {
      transform: translateX(200px)
    }
    img {
      transform: translateY(200px)
    }
   ```
   -   can use translate() for x and y
   -   first value is x, second is y

  3. scale
    -   makes the element bigger or smaller depending on the mangnitude you specify
    -   can use scaleX() or scaleY() to strech it based on the axis
    -   1 is the same
    ```css
    img {
      transform: scaleY(3)
    }
    ```
    -   use scale() if you want to scale it both horizontally and vertically at the same scale

  4. rotate
    -   This is better for elmenets that are 3d
    -   Options: rotatesX() or rotateY()
    -   rotateX() will rotate it along the X-axis
    -   imagine a stick went through the element on the x-axis and you rotate it a few degrees
    ```css
    img {
      transform: rotateX(60deg)
    }
    ```
    -   rotateZ(deg) will rotate the element, clockwise or counterclock wise
    -   can do all three transforms at ago

  5. skew
    -   this will skew an element along the X, Y axis by given angles
    ```css
    div {
      -ms-transform: skew(20deg, 10deg); /* IE 9 */
      -webkit-transform: skew(20deg, 10deg); /* Safari */
      transform: skew(20deg, 10deg);
    }
    ```

  6. perspective
  7. initial
  8. inherit

  -   You can chain transform options
  -   It will occur in the order you wrote it down
  ```css
  img {
    transform: rotateZ(-90deg) translateY(200px) scale(2);
  }
  ```

Source: [CSS Animation Tutorial #2 Transforms](https://www.youtube.com/watch?v=PH35-BDak0M)
Source: [W3Schools: Transform Property](https://www.w3schools.com/cssref/css3_pr_transform.asp)

## CSS Animation Tutorial #3 - Transitions

  -   this is the most simple want to do animations
  -   this controls the state of the transition
  -   set how long to occur? delay?


  ```css
  .circle  {
    width: 100px;
    padding: 50px 0;
    line-height: 0;
    margin: 60px auto;
    background: pink;
    color: white;
    border-radius: 50px;
    cursor: pointer;
    text-align: center;
    /*the background color and rotation will take 1s to change */
    transition: 1s;
  }

  .circle:hover {
    background: salmon;
    transform: rotate(360deg);
  }
  ```

  -   can isolate what animation to take place by specifying in transition
  ```css
  .circle  {
    width: 100px;
    padding: 50px 0;
    line-height: 0;
    margin: 60px auto;
    background: pink;
    color: white;
    border-radius: 50px;
    cursor: pointer;
    text-align: center;
    /*here only background animation will occur becase you specify it with background*/
    transition: background 1s;
  }

  .circle:hover {
    background: salmon;
    transform: rotate(360deg);
  }
  ```

    -   can change it too, decide how long it takes for each animation to occur
    ```css
    .circle  {
      width: 100px;
      padding: 50px 0;
      line-height: 0;
      margin: 60px auto;
      background: pink;
      color: white;
      border-radius: 50px;
      cursor: pointer;
      text-align: center;
      /*bacground transition will take 1s
      transform transition will take 0.3s */
      transition: background 1s, transform 0.3s;
    }

    .circle:hover {
      background: salmon;
      transform: rotate(360deg);
    }
    ```

   -   the first number is the duration, the second number is the delay
   -   you can also pass in the timing function as the third one

   Timing Functions:
   1. linear
    -   same speed throughout the animation

   2. ease
    -   slow start    fast middle    slow end
    -   this is the default one, if you didn't specify one

   2. ease-in
    -  slow start

   3. ease-out
    -   slow end

   4. ease-in-out
    -   slow start  normal middle   slow end

   5. cubic-bezier(n,n,n,n)
   -   you can custom select the timing


Source: [CSS Animation Tutorial #3 - Transitions](https://www.youtube.com/watch?v=oYlJR4Le228)
Source: [W3Schools transition-timing-function](https://www.w3schools.com/cssref/css3_pr_transition-timing-function.asp)


## CSS Animation Tutorial #4 - KEYFRAMES

  -   define animations, tell css how we want animation to work,
      which properties to change, how and when to do it
  -   use diff keyfram block for diff elements
  -   similiar to functions for animations

  Example: Mario Cart
  ```css
  /*// ELEMENTS TO ANIMATE //*/
  .mario {
    position: absolute;
    top: -40px;
    left: 0px;
    /*This is tieing the animation to the element*/
    animation-name: drive;
    animation-duration: 3s;
  }

  /*
  this is how you define an animation
  the name of the animation is drive
  from{}  goes from this state
  to{}  ends up at this state
  */
  @keyframes drive{
    from{ transform: translateX(0) }
    to{ transform: translateX(700px) }
  }
  ```

Source: [CSS Animation Tutorial #4 - KEYFRAMES](https://www.youtube.com/watch?v=PjR97QzOrJM)


## CSS Animation Tutorial #5 - Animation Fill Mode

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


## CSS Animations Tutorials #6 - Repeating Animations

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


## CSS Animation Tutorial #7 - Animation Direction

  animation-direction Options:
    1. normal
      -   defaut value
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

## CSS Animation Tutorial #8 - Animaton Timing Functions

  -   Animation-Timing function determines rate the animation occurs
  -   the default value is ease if you don't specify anything
  -   cubic-bezier() lets you custom determine the rate of the animation
  -   You can use this [helpful website](http://cubic-bezier.com/#.24,-0.07,.93,1.93), to get 4 numbers for the cubic-bezier

Source: [CSS Animation Tutorial #8 - Animaton Timing Functions](https://www.youtube.com/watch?v=t2zoXRXpCWs)

## CSS Animation Tutorial #9 - Animation Shorthand

  -   there is short hand for writing animations

  Standard
  ```css
  .cloud:nth-child(2) {
    width: 300px;
    top:0;
    animation-name: wind;
    animation-duraton: 4s;
    animation-timing-function: ease-in;
    animation-direction: alternate-reverse
  }
  ```

  ShortHand Version
  ```css
  .cloud:nth-child(2) {
    width: 300px;
    top:0;
    animation: wind 4s ease-in infinite alternate-reverse;
  }
  ```

  -   This makes life way easier

Source: [CSS Animation Tutorial #9 - Animation Shorthand](https://www.youtube.com/watch?v=aGuq1euvbYc)
