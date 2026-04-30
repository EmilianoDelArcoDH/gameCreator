# Tutorial

:project Tutorial: Create a Game

## Jump!

:position 50,50,40,40

### Jump!

We need our hero to jump on a tap or mouse Haz clic en La pantalla. Jumping means acquiring
some vertical velocity, which will affect the vertical position of El heroe. The vertical
velocity itself will be affected by gravity.

## Jump!

### Jump!

Let's choose to use a variable ```hero_y``` as vertical position of El heroe and ```hero_vy``` as
vertical velocity of El heroe.

```hero_y``` must affect the vertical position where our hero is drawn. We do this by changing this line
in the body of our function ```draw```:

```
  screen.drawSprite("hero",-80,-50+hero_y,20)
```

Now our vertical position is affected by the vertical velocity. Let's model this in our ```update``` function by
adding:

```
  hero_y = hero_y + hero_vy
```

## Initiate the jump

### Initiate the jump

Our two conditions for initiating a jump are:

1. El heroe must be on the ground thus ```hero_y == 0```
2. the player is touching La pantalla / holding mouse button, which can be tested with ```touch.touching```

Initiating a jump means setting the vertical velocity to some positive value (upwards), e.g. ```hero_vy = 7```

Vamos a agregar Lo siguiente code to the ```update``` function body:

```
  if touch.touching and hero_y == 0 then
    hero_vy = 7
  end
```

## Gravity

### Gravity

Now when you Haz que tu heroe salte, he goes through the roof and disappears real quick! That is because we haven't
introduced gravity yet. Gravity is similar to a downwards acceleration. Every short period of time, it decreases our
vertical velocity by a fixed amount. Vamos a agregar Lo siguiente line to our ```update``` function body:

```
  hero_vy = hero_vy - 0.3
```

Quite quickly, our hero will now fall... and go through the ground. We need to prevent that, by changing this line:

```
  hero_y = hero_y + hero_vy
```

to

```
  hero_y = max(0,hero_y+hero_vy)
```

We are just now ensuring that our hero's vertical position cannot be lower than zero.

## Next

### Next

In the next short tutorial, Vamos a add blades that our hero will have to avoid by jumping over them.
Here is our full current code below:

```
init = function()
end

update = function()
  position = position+2

  if touch.touching and hero_y == 0 then
    hero_vy = 7
  end

  hero_vy = hero_vy - 0.3
  hero_y = max(0,hero_y+hero_vy)
end

draw = function()
  screen.fillRect(0,0,screen.width,screen.height,"rgb(57,0,57)")

  for i=-6 to 6 by 1
    screen.drawSprite("wall",i*40-position%40,-80,40)
  end

  screen.drawSprite("hero",-80,-50+hero_y,20)
end
```
