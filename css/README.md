## URLS

- [Game: CSS Dinner](https://flukeout.github.io/)
- [Game: Garden](https://cssgridgarden.com/#es)
- [Game: Froggy](https://flexboxfroggy.com/#es)
- [Color Hunt](https://colorhunt.co/)
- [icons](https://iconos8.es/)
- [Picular](https://picular.co/Video)
- [Colors](https://coolors.co/)
- [Gradient](https://cssgradient.io/gradient-backgrounds/)
- [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Stylus](https://stylus-lang.com/)
- [Sass](https://sass-lang.com/guide)
- [Experiments](https://labs.jensimmons.com/)
- [Flaticons](https://www.flaticon.com/)

![CSS](./imgs/reglacss.png)

## Modelo de caja

![CSS](./imgs/mdc.png)

![CSS](./imgs/mdcd.png)

### Margin:

> Es el espacio de la caja hacia afuera

### Border:

> Es el atributo del borde, el contorno de la caja

### Padding:

> Es un espacio de la caja hacia adentro, para ordenar mejor

### Content:

> Comprende el alto y ancho de la caja

### Calc

> Hay una forma de hacer que CSS calcule el tamaño de un elemento restandole cierta cantidad (width o height). Imagina que quieres colocar 2 cajas dentro de una caja padre y quieres que cada una tome el 50% del ancho, pero cada caja tenga un margen a la izquierda de 10px.

> Si colocas el 50% de la caja y ademas colocas el margen, esto hará que las cajas queden una encima de otra, por lo que se estan agregando 20 px al contenido y ya no se ajustará al 50% cada elemento

```
.caja-hijo{
width: calc(50% -20px);
}
```

- Se le coloca 20px porque estamos aumentado un padding-;eft de 10px a cada elemento, como son 2, entonces se aumenta 20px al content

### RESETEAR EL ESTILO DE LA PAGINA

```
*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html{
  font-size: 62.5%;
}
```

## Especificidad

> Es la gerarquía que tienen las diferentes asignaciones de estilo en CSS

|              Tipo              | Caracteristica                                                                                                   |
| :----------------------------: | ---------------------------------------------------------------------------------------------------------------- |
|           !important           | Se coloca sin importar el resto de estilos, este es el de mayor gerarquía (evitar usarlo)                        |
| css inyectado en etiqueta HTML | Se aplicará sin importar el resto de CSS excepto si existe un !important (evitar usarlo)                         |
|               id               | Los id se aplican si no existe un css inyectado en una etiquta HTML y si no existe un !important (evitar usarlo) |
|             clases             | Las clases se aplican si lo anterior no existe en el CSS, si se quiere aplicar CSS se debe aplicar con clases    |
|            etiqueta            | Las etiquetas son de menor gerarquía, se aplican si no existen clases                                            |

## [Combinadores](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators)

|             Tipo              | Caracteristica                                                    |
| :---------------------------: | ----------------------------------------------------------------- |
| h2 + p {} (hermano adyacente) | aplica la propiedad si p sigue despues de h2                      |
|  h2 + p {} (hermano general)  | Aplica la propiedad siempre y cuando p este al mismo nivel que h2 |
|   div > p {} (hijo directo)   | si p es hijo directo de div, aplicale el estilo                   |
|    div p {} (desenciente)     | Si dentro de un div existe un p, aplicale este estilo             |

## Medidas

- Relativas

  > Las medidas relativas si cambian

- Absolutas
  > Son una medida que no va a cambiar

| Absolutas | Relativas            |
| :-------: | -------------------- |
|    px     | %                    |
|           | em                   |
|           | rem(root em)         |
|           | max-width/max-height |
|           | min-width/min-height |
|           | vw (viewport width)  |
|           | vh (viewport height) |

> em: Es una relativa que toma el tamaño de fuente de su padre directo

> rem: Siempre toma el valor de la etiqueta root osea la etiqueta HTML

> width: Será el tamaño de referencia para usar

- min-width
  > indica el tamaño minimo que tendrá un elemento
- max-width

  > es el tamaño maximo que tendra un elemento

- min-height:
  > es para que el elemento tenga un tamaño minimo pero si el contenido supera ese tamaño, entonces crecerá con el contenido el tamaño del elemento

## Position

| Position | caracteristica                                                               |
| :------: | ---------------------------------------------------------------------------- |
|  static  | Viene en todos los elementos por defecto y no se puede modificar su posición |
| absolute | se puede modificar su posición (bottom,top,left,right)                       |
| relative | se puede modificar su posición (bottom,top,left,right)                       |
|  fixed   | se puede modificar su posición (bottom,top,left,right)                       |
|  sticky  | se puede modificar su posición (bottom,top,left,right)                       |

## Display

|   Display    | Caracteristica                                                                                                                       |
| :----------: | ------------------------------------------------------------------------------------------------------------------------------------ |
|    block     | ocupa el 100% del width sin importar el tamaño del contenido                                                                         |
|    inline    | ocupa el espacio del contenido del elemento, si queda espacio otras etiquetas se acomodaran alado (❌margin/paddin/🔝🔛width/height) |
| inline-block | Es una combinación de inline y block                                                                                                 |
|     flex     | Ayuda al responsive design                                                                                                           |

- flex-direction

  - Default: row
  - column
  - row-reverse (voltea el orden de los elementos)
  - column-reverse (voltea el orden de los elementos)

- flex-wrap: wrap;
  > lo elementos se acomodan al tamaño del viewport uno alado del otro o hacia abajo
- flex-wrap: wrap-reverse;

  > funciona igual que el anterior pero lo hace invertido

- justify-content:

  - center: alinea los elementos al centro
  - flex-end: alinea todo a la derecha
  - flex-start: alinea todo a la izquierda (viene por default)
  - space-around: alinea todos los elementos con un espacio entre ellos
  - space-evenly: alinea los elementos con un espacio igual para todos

- align-items:
  - flex-end: alinea todo en la parte de abajo
  - flex-start: alinea todo en la parte de arriba
  - stretch: Hace que el elemento se estire hasta ocupar todo el height de su contenedor padre
  - baseline: Tomará el espacio del height que ocupe su contenido

# Order

> El orden se puede modificar desde el CSS con el atributo order: y todos los elementos que se encuentren en el mismo contenedor, que tengan este atributo se ordenaran, y los que no lo contengan dentro del mismo contenedor, se moveran a la izquierda.

- Ejemplo:
  - si tenemos 6 elementos y a 4 de ellos les colocamos el atributo order, 2 de los 6 elementos se moverán a la izquierda, el resto estarán ordenados como los colocamos

> flex-grow:1; El elemento que tenga esta propiedad crecerá hasta llenar el espacio del width, respetando el tamaño de los demnás elementos

> flex-basis: recibe valor número como parametro (ejem: 10rem) y funciona como colocarle un width a un elemento solo que en este caso el elemento actua de manera responsive

# VARIABLES en CSS

> Se declaran de la siguiente forma, dentro del root

```
:root{
  --nombre-variable: atributo;
  --primary-color: #003476;
}
```

> Debe llevar el -- al incio

- Se llama de la siguiente forma

  ```
  main{
      color: var(--primary-color);
  }
  ```
