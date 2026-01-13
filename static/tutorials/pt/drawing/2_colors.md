<!-- 1. Formas (Rect, Round, RoundRect) -->
<!-- 2. Cores -->
<!-- 3. Lines, Polygons -->
<!-- 4. Text -->
<!-- 5. Sprites e mapas -->
<!-- 6. Degradados -->
<!-- 7. Rotating, Scaling, Transparency -->


# Tutorial

:project Tutorial: Drawing

## Cores

:position 50,50,40,40

### Cores

Your computer screen can display almost any color by mixing some Red, some
Green and some Blue. We thus call it the RGB color model. In Digital House Game, a color
is given as a string value, which can comply with different formats. Let's start
with this one:

```
screen.fillRect(0,0,50,50,"rgb(255,255,255)")
```

The color used above ```"rgb(255,255,255)"``` is white, expressed as RGB
color. The value for red, green and blue is set to 255, which is the maximum accepted value
(accepted values range from 0 to 255). If you max out and mix red, green and blue, you end up
with the color white.

## Cores

### RGB Cores

Try changing the values of red, green and blue manually and see the Cores you get. Here
are a few examples:

```
// max red and zero green and blue ; Isto Ã© full red
screen.fillRect(0,0,50,50,"rgb(255,0,0)")
```

```
// max red and green gives pure yellow
screen.fillRect(0,0,50,50,"rgb(255,255,0)")
```

```
// red = green = blue will give you a shade of grey
screen.fillRect(0,0,50,50,"rgb(128,128,128)")
```

Try more Cores! VocÃª pode also use the color picker (hold CTRL down) and see how
the chosen color translates to code.

## Cores

### Omitting color

Digital House Game lets you omit Cores in all your drawing calls. When omitted, it will reuse
the color that was last used. VocÃª pode also call ```setColor``` to define a new color to use for subsequent
drawing calls.

```
screen.setColor("rgb(0,255,255)")  // cyan
screen.fillRect(0,0,50,50)
```

## Transparency

### Transparency

VocÃª pode make your Cores partly transparent. Depending on the opacity value, content
that was already drawn below your shape will remain partly visible. The opacity value
can range from 0 (fully transparent) to 1 (fully opaque). Here is an example of a half
opaque white:

```
screen.setColor("rgba(255,255,255,0.5)")
```

Note the added "a" making "rgba" and the additional parameter after the three color components.
"a" stands for "alpha channel" which is the name of the transparency channel when an image data
is encoded.

## Other formats

### Other formats

Digital House Game accepts all HTML/CSS color formats. It means VocÃª pode use RGB hex (like ```"#FF00FF"```),
HSL, etc. This won't be covered Neste tutorial though, if you want to learn more about them
VocÃª pode check out this page:

https://developer.mozilla.org/en-US/docs/Web/CSS/color_value
