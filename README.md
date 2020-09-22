# 5 maneras de centrar un 'div' con CSS!

Si justo estás empezando en el mundo de los estilos en CSS, a veces puede resultar un poco complicado. En CSS (y en programación en general) rara vez solo hay una manera de crear algo. Esta guia te enseñará 5 maneras fáciles de centrar un elemento con otro elemento.

Cuando hablamos de elementos en una página, en este ejemplo, vamos a utilizar dos 'div'. Uno va a ser el 'elemento padre' y el otro, el 'elemento hijo'.



## Centrar un 'div' horizontalmente 

#### 1. Text-align 

Aunque suene raro, la propiedad 'text-align' no solo sirve para centrar texto en una página, también es útil para los 'div'.

Esta propiedad hay que añadirsela al elemento padre, que sería quién contiene el texto o en este caso el 'div'. Pero, si solo añadimos esta propiedad por si solo no va a funcionar. Esto se debe a que el elemento secundario, por defecto, debido a la naturaleza de un 'div', abarca el ancho de su elemento padre. Para anular esto, debemos añadir al 'elemento hijo' una propiedad de display: con un valor de inline-block.



#### HTML

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="parent-div">
      <div id="children-div"></div>
    </div>
  </body>
</html>
```



#### CSS

```css
#parent-div {
  background: bisque;
  height: 95vh;
  width: 50vw;
  
  text-align: center;
}

#children-div {
  background: thistle;
  height: 100px;
  width: 100px;
  
  display: inline-block;
}
```



#### 2. Margin

 Cuando queremos centrar los elementos con la propiedad margin tenemos que darle el enfoque de manera opuesto. No tocaremos el 'elemento padre', tocaremos el 'elemento hijo', porque solamente queremos darle al 'elemento hijo' un margen para que se aleje de sus lados. 

Podemos darle varias cantidades de píxeles para tratar de centrarlo al centro pero hay una manera mucho más fácil y efectiva de lograrlo. Simplemente con darle al elemento hijo una propiedad de **margin: 0 auto**. Esto ajustará automáticamente el tamaño del margen en el lado izquierdo y derecho de manera uniforme entre sí. 

Veámos el ejemplo:

#### HTML

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="parent-div">
      <div id="children-div"></div>
    </div>
  </body>
</html>
```

#### CSS

```css
#parent-div {
  background: bisque;
  height: 95vh;
  width: 50vw;
}

#children-div {
  background: thistle;
  height: 100px;
  width: 100px;
  
  margin: 0 auto;
}
```

## Centrar un 'div' horizontalmente y verticalmente 

#### 3. Posición relativa 

Lo primero que tenemos que hacer es asignar la propiedad al 'elemento hijo' de **position: relative**. Hasta ahora lo que hemos hecho es decirle al elemento que lo vamos a mover en relación a su posición inicial. Expresando lo que queremos hacer en términos simples: queremos mover la parte superior a la mitad hacia abajo y la parte izquierda a la mitad de donde se encontraba inicialmente. 

Podemos hacer esto asignando dos propiedades más: **top** y **left** ambas al valor del 50%. Este 50% se refiere al 50% del tamaño del padre. Pero esto no está del todo correcto aún. 

Nuestro objetivo real es mover el centro de la caja hacia abajo y hacia arriba. Técnicamente podríamos ajustar los porcentajes de nuestros valores **top** y **left** para que sean más precisos, pero hay una forma más eficaz de lograrlo. Podemos usar la propiedad lamada **transform**. Lo que va a hacer esta propiedad es transformar el elemento hijo en relación a si mismo, no en relación al elemento padre. Dicho esto podemos agregar el valor de **translate (-50%, -50%)** a la propiedad **transform**. 

El primer valor entre paréntesis se refiere al movimiento ascendente/descendente y el segundo para derecha/izquierda. Los porcentajes positivos moverán el elemento hacia abajo o hacia la derecha respectivamente, mientras que los negativos moverán el elemento hacia abajo y hacia la izquierda. El porcentaje en sí mismo se refiere al tamaño del elemento real. En resumen, este valor indica que queremos mover (trasladar) el elemento hacia arriba la mitad de su propia altura y hacia la izquierda la mitad de su propio ancho.

#### HTML

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="parent-div">
      <div id="children-div"></div>
    </div>
  </body>
</html>
```

#### CSS

```css
#parent-div {
  background: bisque;
  height: 95vh;
  width: 50vw;
}

#children-div {
  background: thistle;
  height: 100px;
  width: 100px;
  
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%)
}
```

#### 4. Posición absoluta

Este es un poco diferente a los otros métodos. El elemento se colocará en relación al 'elemento padre' con una posición relativa o absoluta. Sin embargo, si no existe tal 'elemento padre', se colocará en relación con la página en sí. 

Otra nota importante es que el posicionamiento absoluto, a diferencia de los otros métodos que hemos discutido, eliminará el elemento del flujo de la página. Esto significa que el elemento podrá suporponerse a los otros elementos de la página si se usa incorrectamente. Si seguimos los mismos pasos que el método de posicionamiento relativo anterior, encontraremos resultados similares, sin embargo, el elemento aparecerá centrado en la pantalla, no necesariamente centrado dentro de su padre.

#### HTML

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="parent-div">
      <div id="children-div"></div>
    </div>
  </body>
</html>
```

#### CSS

```css
#parent-div {
  background: bisque;
  height: 95vh;
  width: 50vw;
}

#children-div {
  background: thistle;
  height: 100px;
  width: 100px;
  
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

Para remediar esto, simplemente podemos agregar **position: relative** o **position: absolute** al 'elemento padre':

#### HTML

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="parent-div">
      <div id="children-div"></div>
    </div>
  </body>
</html>
```

#### CSS 

```css
#parent-div {
  background: bisque;
  height: 95vh;
  width: 50vw;
  position: relative;
}

#children-div {
  background: thistle;
  height: 100px;
  width: 100px;
  
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

#### 5. Display Flex

Con Flexbox tenemos que asegurarnos de tener la misma mentalidad de la que hablamos anteriormente con text-align. Queremos colocar el elemento hijo dentro del elemento padre y lo haremos convirtiendo el elemento padre en un flexbox. El flexbox no afecta la posición del elemento en sí, pero cambiará la posición de los 'elementos hijos'. Todo lo que tenemos que hacer es asignar al elemento padre la propiedad de **display: flex** antes de comenzar a ver algunos cambios. 

El elemento hijo ahora se ha desplazado completamente hacia la izquieda. Otra forma de decir eso es que el contenido del flexbox se ha justificado a la izquierda. Podemos cambiar eso agregando una propiedad de **justify-content: center**, que justificará en el centro ese elemento. 

Entonces, podemos elegir alinear verticalmente este elemento dentro de su 'elemento padre' agregando la propiedad **align-items: center**. ¡No es necesario aplicar ningún estilo al elemento secundario!

#### HTML

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="index.css">
  </head>
  <body>
    <div id="parent-div">
      <div id="children-div"></div>
    </div>
  </body>
</html>
```

#### CSS

```css
#parent-div {
  background: bisque;
  height: 95vh;
  width: 50vw;
  position: relative;
  
  display: flex;
  justify-content: center;
  align-items: center;
}

#children-div {
  background: thistle;
  height: 100px;
  width: 100px;
}
```

En estos links que dejamos a continuación podras hacer una buena práctica del flexbox:

[flexbox froggy](https://flexboxfroggy.com/)

http://www.flexboxdefense.com/



Como mencionamos anteriormente, esta no es una lista completa de todas las formas de centrar un <div>, pero es un buen comienzo donde hay que profundizar!

