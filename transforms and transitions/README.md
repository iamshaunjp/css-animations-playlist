File created by Kai Lin Cheng - edited by myself for spelling typos to test GitHub
## CSS Animation Tutorial

Learning CSS Animation from [The Net Ninja](https://www.youtube.com/watch?v=jgw82b5Y2MU)
##################################################################
## CSS Animation Tutorial#2 Transforms
##################################################################

Transform web elements to different things

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
   -   can use translate(x, y) for x and y
   -   first value is x, second is y

  3. scale
    -   makes the element bigger or smaller depending on the magnitude you specify
    -   can use scaleX() or scaleY() to strech it based on the axis
    -   1 is the same
    ```css
    img {
      transform: scaleY(3)
    }
    ```
    -   use scale() if you want to scale it both horizontally and vertically at the same scale

  4. rotate
    -   This is better for elements that are 3d
    -   Options: rotatesX() or rotateY()
    -   rotateX() will rotate it along the X-axis
    -   imagine a stick went through the element on the x-axis and you rotate it a few degrees
    ```css
    img {
      transform: rotateX(60deg)
    }
    ```
    -   rotateZ(deg) will rotate the element, clockwise or counterclockwise
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

##################################################################
## CSS Animation Tutorial #3 - Transitions
##################################################################

  -   this is the most simple way to do animations
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
    /*here only background animation will occur because you specify it with background*/
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
      /*background transition will take 1s
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
