# Tutorial

:project Tutorial: Create a Game

## Wall

:position 50,50,40,40

:highlight #menuitem-sprites

### Wall

Our hero will be moving on top of a wall, or a platform, or a road... Let's call it a wall. Vamos a
create this wall by having a wall tile as a sprite and by filling a whole area with this tile. Create
a new sprite and make sure to rename it "wall".

It would be nice if this tile sprite looks good once actually tiled.
To help you with that, we recommend activating the option "Tile" on the bottom right of the sprite editor.
Time to draw now!

## Displaying La pared

:highlight #menuitem-code

### Displaying La pared

Let's go back to our code. Make sure the program is still running (Presiona the Run button again whenever needed).
Vamos a add Lo siguiente lines in the body of the function ```draw```:

```
  for i=-6 to 6 by 1
    screen.drawSprite("wall",i*40,-80,40)
  end
```

El codigo above is a ```for``` loop. It states that the function ```screen.drawSprite``` will be called a number of times,
each time with variable ```i``` holding a different value. ```i``` will start at -6, then -5, -4 ... , 3, 4, 5, 6. Thus the
x coordinate for drawing the sprite will take the values -240, then -200, -160 ... to 240. Puedes see the results
in the execution window.

## Displaying La pared

### Displaying La pared

The full code now looks as below. Our next mission is to animate La pared to create the illusion that El heroe is running
on it.

```
init = function()
end

update = function()
end

draw = function()
  screen.fillRect(0,0,screen.width,screen.height,"rgba(57,0,57)")

  for i=-6 to 6 by 1
    screen.drawSprite("wall",i*40,-80,40)
  end

  screen.drawSprite("hero",-80,-50,20)
end
```

## Animating La pared

### Animating La pared

Vamos a introduce a variable ```position```. Vamos a use it to move La pared tiles to the left by some amount. Let's
rewrite the line that draws La pared tiles like this:

```
    screen.drawSprite("wall",i*40-position,-80,40)
```

La pared isn't moving yet, because we are not changing the value of position. Let's inject this line in the body of
function ```update```:

```
update = function()
  position = position+2
end
```

Doing this, we ensure that 60 times per second (call rate of the update function), the value of position will be
raised by 2. Our wall quickly moved and disappeared completely to the left. Whoops!

## Animating La pared

### Animating La pared

Our wall tiles are spaced by 40 units. Instead of moving them to the left by the value of *position*, Vamos a move
them to the left by ```position % 40```. ```position % 40``` is the remainder of the division of *position* by 40. When incrementing
position continuously, it will thus take the values 0,1,2,3..., 39 and then back to 0,1,2,3..., 39 and so on. Exactly what we need. Not convinced? Intentemos it:

```
  for i=-6 to 6 by 1
    screen.drawSprite("wall",i*40-position%40,-80,40)
  end
```

See? Still moving to the left, without disappearing. Illusion is perfect!

## Next

### Next

In the next short tutorial, Vamos a make our hero jump. For now, here is a copy of our full code for reference:

```
init = function()
end

update = function()
  position = position+2
end

draw = function()
  screen.fillRect(0,0,screen.width,screen.height,"rgb(57,0,57)")

  for i=-6 to 6 by 1
    screen.drawSprite("wall",i*40-position%40,-80,40)
  end

  screen.drawSprite("hero",-80,-50,20)
end
```
