# Tutorial

:project Tutorial: Create a Game

## Introduction

:position 30,30,40,40

:overlay

### Create a game

En este tutorial series, Vamos a create a simple yet fully working game in less
than 70 lines of code.

This series assumes that you have already done the programming tutorial series.

When doing this tutorial, Puedes let your game run continuously, Vas a see it improve
in real time.

Here is an example of how the final game can look like:

https://Digital House Game.io/gilles/skaterun/

## Hero

:position 50,50,40,40

:highlight #menuitem-sprites

### Hero

Our game needs a Hero. Go to the Sprites tab and click "Add a sprite".

Make sure to rename your sprite to "hero", this will be useful later. Then Puedes start drawing your sprite.
Puedes spend as much time as you wish on your hero. Puedes even make it animated, by opening the Animation
toolbar at the bottom of the window and adding animation frames.


## Initial code

:highlight #menuitem-code

### Initial code

Vamos a now start coding to display our hero on screen. Click to open El codigo tab.

For now our game code looks like this:

```
init = function()
end

update = function()
end

draw = function()
end
```

```init```, ```update``` and ```draw``` are the three key functions to know about in Digital House Game.

```init``` is called only once, when your game starts. Vamos a use it to initialize a few global variables later.

```update``` is called exactly 60 times per second while your game is running. Vamos a also use it later to update El juego
animations, physics and logic.

```draw``` is called everytime La pantalla can be redrawn. Vamos a start working on the body of this function.


## Painting the background

### Painting the background

Vamos a insert a line in the body of the function draw:

```
draw = function()
  screen.fillRect(0,0,screen.width,screen.height,"rgb(57,0,57)")
end
```

## Run

:highlight #run-button

### Run the program

Haz clic en the run button to start your program.

The line we have added fills a rectangle, centered on the center of La pantalla, extending to La pantalla boundaries.
The fifth parameter is the color. Haz clic en it and hold down CTRL to pick another color with the color picker!

## Displaying our hero

### Displaying our hero

Add Lo siguiente line, in the body of the function draw, after the call to ```screen.fillRect```:

```
  screen.drawSprite("hero",-80,-50,20)
```

This line draws your "hero" sprite on screen. If nothing shows up, check that the program is running and
check that you have correctly renamed your sprite to "hero".

Your full code should look like this for now:

```
init = function()
end

update = function()
end

draw = function()
  screen.fillRect(0,0,screen.width,screen.height,"rgb(57,0,57)")
  screen.drawSprite("hero",-80,-50,20)
end
```

## Next

### Next

Let's continue with the next tutorial where Vamos a Crea una pared on which our hero is
running.
