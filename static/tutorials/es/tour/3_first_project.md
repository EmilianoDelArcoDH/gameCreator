# Tutorial

:project Tutorial: Primer proyecto

## Primer Proyecto

:position 30,30,40,40

:overlay

### Primer Proyecto

Tu primer proyecto ya se ha creado! Vas a crear un personaje y
programar Digital House Game para mostrarlo en pantalla y asegurar que pueda ser movido
presionando las teclas de flecha de tu teclado de computadora.


## Crear un sprite

### Crear un sprite

Haz clic en **Sprites** para abrir el editor de sprites.

:highlight #projectview .sidemenu #menuitem-sprites

:auto

## Crear un sprite 2

### Crear un sprite

Haz clic en el boton "Agregar Sprite" para crear un nuevo sprite.

:navigate projects.sprites

:highlight #create-sprite-button

:auto


## Pintar tu sprite

:navigate projects.sprites

:position 0,50,30,40

### Dibuja tu personaje

Usa las herramientas de dibujo en el lado derecho de la pantalla para dibujar tu personaje.
Puedes dedicar tanto tiempo como desees en ello!

Cuando tu sprite este listo, pasa al siguiente paso.

## Codigo 1

### Codigo

Ahora haz clic en **Codigo**, estamos a punto de programar un poco!

:highlight #projectview .sidemenu #menuitem-code

:auto


## Codigo

:navigate projects.code

:position 55,30,45,40

### Codigo

El codigo de tu proyecto ya esta lleno con la definicion de tres funciones:
```init```, ```update``` y ```draw```. Vamos a trabajar en el contenido de la funcion
```draw```. Agrega la siguiente linea, entre la linea
```draw = function()``` y la linea ```end```:

```
  screen.drawSprite("sprite",0,0,20)
```

Así es como se ve ahora tu codigo:

```
draw = function()
  screen.drawSprite("sprite",0,0,20)
end
```

## Ejecutar

:navigate projects.code

:position 55,55,45,40

### Ejecuta tu programa

Vamos a probarlo! Haz clic en el boton de reproduccion para lanzar tu programa.

:highlight #run-button

:auto

## Ejecutar

:navigate projects.code

:position 55,55,45,40

### Ejecutando

Tu personaje ahora se muestra en el medio de la vista de ejecucion. La linea de codigo
que hemos agregado llama a la funcion ```drawSprite``` en el objeto
```screen```. La llamada se realiza con parametros: el nombre del sprite a mostrar  ```"sprite"```
(asegúrate de que sea realmente el nombre del sprite que creaste), coordenadas x e y del punto
donde mostrarlo (0,0 es el centro de la pantalla) y el tamaño de visualizacion (20).

Puedes jugar con estas coordenadas para cambiar la posicion de dibujo del sprite. Notaras
que tus cambios se reflejan en tiempo real en la vista de ejecucion.

## Agregar un fondo

:navigate projects.code

### Agregar un color de fondo

Encima de nuestra linea ```screen.drawSprite(...)```, vamos a agregar la siguiente linea:

```
  screen.fillRect(0,0,400,400,"#468")
```

```fillRect``` significa "llenar un rectangulo". El parametro ```"#468"``` representa
un color azul grisáceo. Haz clic en él y luego mantén presionado CTRL, aparecerá un selector de color.
Elige el color que mas te guste!


## Controlar el personaje

:navigate projects.code

### Controlar el personaje

Para controlar la posicion de dibujo del personaje, usaremos dos variables, ```x``` e ```y```.
Vamos a cambiar la linea de codigo que dibuja el sprite, de la siguiente manera:

```
  screen.drawSprite("sprite",x,y,20)
```

El personaje ahora sera dibujado en las coordenadas ```x``` , ```y```.

## Control

:navigate projects.code

### Controlar el personaje

Todo lo que necesitamos ahora es cambiar el valor de ```x``` e ```y``` cuando se presionan las teclas
de flecha del teclado. Inserta la siguiente linea entre
```update = function()``` y ```end```:

```
  if keyboard.LEFT then x = x-1 end
```

Tu codigo completo ahora se ve así:

```
init = function()
end

update = function()
  if keyboard.LEFT then x = x-1 end
end

draw = function()
  screen.fillRect(0,0,400,400,"rgb(140,198,110)")
  screen.drawSprite("sprite",x,y,20)
end
```

## Controlar el personaje

:navigate projects.code

### Controlar el personaje

Haz clic en la vista de ejecucion, luego presiona la tecla de flecha izquierda de tu teclado de computadora.
Deberías ver el personaje moviéndose hacia la izquierda!

Por que: la linea de codigo que agregamos verifica si se presiona la tecla de flecha izquierda (```keyboard.LEFT```) y
cuando es el caso, el valor de ```x``` se reduce en 1.

Sabiendo que los otros identificadores de teclas de flecha son RIGHT, UP y DOWN, agrega tres lineas a tu codigo
para asegurar que tu personaje pueda moverse en todas las direcciones.

(Solucion en el siguiente paso)

## Controlar el personaje

:navigate projects.code

### Controlar el personaje

Aqui esta el codigo completo de la funcion  ```update``` para mover el personaje en las 4 direcciones con
teclas de flecha del teclado:

```
update = function()
  if keyboard.LEFT then x = x-1 end
  if keyboard.RIGHT then x = x+1 end
  if keyboard.UP then y = y+1 end
  if keyboard.DOWN then y = y-1 end
end
```

## Fin

Este tutorial ha terminado. Ahora puedes aprender mas sobre programacion en *microScript*, comenzando
el curso sobre Programacion.
