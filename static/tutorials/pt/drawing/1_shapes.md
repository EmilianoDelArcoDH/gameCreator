<!-- 1. Formas (Rect, Round, RoundRect) -->
<!-- 2. Cores -->
<!-- 3. Lines, Polygons -->
<!-- 4. Text -->
<!-- 5. Sprites e mapas -->
<!-- 6. Degradados -->
<!-- 7. Rotating, Scaling, Transparency -->


# Tutorial

:project Tutorial: Drawing

## Drawing

:position 30,30,40,40

:overlay

### Drawing

In Digital House Game, VocÃª pode consider O computador screen as a drawing board.
You will be able to draw Formas, text, lines, polygons, images (sprites) and
maps with code, by calling predefined functions.

Let's start by drawing Formas!


## Rectangle

### Drawing a rectangle

:position 50,50,40,40

For this tutorial VocÃª pode delete all the default code contents in the code window.
Now just start with O seguinte line of code:

```
screen.fillRect(0,0,50,50,"#F00")
```

## Rectangle

### Drawing a rectangle

:position 50,50,40,40

:highlight #run-button

Click the button "Run". Your program starts and you will see it draws a red
square in the center of the run window. Let's have a closer look at the code:

* ```screen``` is the base object representing the screen
* ```fillRect``` is a member function of screen, which fills a rectangle, at given coordinates, with the given color
* ```0,0,50,50``` are the drawing coordinates in this order: 0,0 are the x and y coordinates of the center of our rectangle ; 50,50 are the width and height of our rectangle.
* ```"#F00"``` defines the color as red. VocÃª aprenderÃ¡ more about Cores in the next tutorial.


## Rectangle

### Drawing a rectangle

:position 50,50,40,40

To better understand your code, VocÃª pode start playing with the values: click in your code
on one of the values (```0,0,50,50```) then hold down the CTRL key of your computer keyboard. A slider
will show up, use it to change the value and see how it affects the rectangle being drawn in the
execution window.

You may also Clique em the color ```"#F00"``` and hold down CTRL to pick other Cores.

## Screen coordinates

### Screen coordinates

In *Digital House Game*, the coordinate system is based on the center of the screen. Thus the center
of the screen has the coordinates 0,0. In portrait mode, the x coordinate will range from -100 (leftmost point) to +100 (rightmost point).
In landcape mode, the y coordinate will range from -100 to 100 as well. Isto Ã© illustrated below:

![Screen coordinates](/doc/img/screen_coordinates.png "Screen coordinates")

This coordinate system will help you to scale your content correctly and fit any screen size regardless of the actual,
physical pixel resolution of the screen.

## Rectangle outline

### Drawing a rectangle outline

:position 50,50,40,40

VocÃª pode draw a rectangle outline by changing your code to:

```
screen.drawRect(0,0,50,50,"#F00")
```

When before drawing outlines, VocÃª pode use ```screen.setLineWidth``` to define the
thickness of the lines. The default line width is 1. Try for example:

```
screen.setLineWidth(4)
screen.drawRect(0,0,50,50,"#F00")
```

## Round Formas

### Drawing circles and ellipses

:position 50,50,40,40

Similarly, VocÃª pode draw a round shape (circle, ellipse depending on the size used) using ```fillRound``` or
```drawRound``` methods. Examples:

```
screen.fillRound(0,0,50,50,"#F00")
```

or

```
screen.drawRound(0,0,50,50,"#FFF")
```


## Rounded rectangle

### Rounded rectangle

:position 50,50,40,40

VocÃª pode draw rounded rectangles with ```fillRoundRect``` and ```drawRoundRect```. The corners of your
rectangle area will be rounded. There is an additional parameter here which is the radius of the rounding
for the corners. Try for example:

```
screen.fillRoundRect(0,0,50,50,10,"#F00")
```

or

```
screen.drawRoundRect(0,0,50,50,10,"#FFF")
```

The rounding radius in the examples above is 10. VocÃª pode change its value and see how it affects the drawing.


## Move to Cores

### Time to learn about Cores!

VocÃª pode now continue with the next tutorial, where VocÃª aprenderÃ¡ about Cores.
