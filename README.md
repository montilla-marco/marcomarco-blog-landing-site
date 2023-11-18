# marcomarco-blog-landing-site

linea.io

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence

Falsy values: 0 '' undefined, NaN, null

(===) strict equality operator cause not make type coertion 


```javascript
var vegetables = ["parsnip", "potato"];
var moreVegs = ["celery", "beetroot"];

// Merge the second array into the first one
// Equivalent to vegetables.push('celery', 'beetroot');
Array.prototype.push.apply(vegetables, moreVegs);

console.log(vegetables); // ['parsnip', 'potato', 'celery', 'beetroot']
```

Using an object in an array-like fashion
```javascript
var obj = {
  length: 0,

  addElem: function addElem(elem) {
    // obj.length is automatically incremented
    // every time an element is added.
    [].push.call(this, elem);
  },
};

// Let's add some empty objects just to illustrate.
obj.addElem("Marco");
obj.addElem("Montilla");
console.log(obj.length);
// → 2
```

Usando call para encadenar constructores para un objeto
```javascript
function Producto(nombre, precio) {
  this.nombre = nombre;
  this.precio = precio;

  if (precio < 0)
    throw RangeError(
      'No se puede crear el producto "' + nombre + '" con un precio negativo',
    );
  return this;
}

function Comida(nombre, precio) {
  Producto.call(this, nombre, precio);
  this.categoria = "comida";
}
Comida.prototype = new Producto();

function Juguete(nombre, precio) {
  Producto.call(this, nombre, precio);
  this.categoria = "juguete";
}
Juguete.prototype = new Producto();

var queso = new Comida("feta", 5);
var diversion = new Juguete("robot", 40);
```

Usando call para invocar una función anónima
```javascript
var animales = [
  { especie: "Leon", nombre: "Rey" },
  { especie: "Whale", nombre: "Fail" },
];

animales.
  (function (i) {
    this.imprimir = function () {
      console.log("#" + i + " " + this.especie + ": " + this.nombre);
    };
    this.imprimir();
  }).call(animales[i], i);
}
```

```javascript
[...Array(7).keys()].forEach(element => console.log(element));

[...Array(7).keys()].reverse().forEach(arrayItem =>
    console.log(arrayItem)
)
```

<b>   -> <strong>
<i>   -> <em>

<html lang="en">          lenguaje
<meta charset="utf-8" />  conjunto de caracteres asociados al lenguaje

<!-- LVHA -->
a:link
a:visited
a:hover
a:active

Image Preview
Auto Rename Tag
Emmet
Color Highlight
EsLint
Liver Server

opt + cmd + j = console
opt + cmd + i = inspect

#1: Conflicts Between Selectors
5: !important
4.- inline-selector
3.- id-selector
2.- class-selector
1.- element-selector
0.- universal-selector
Selector specifity(0, 0, 0)

https://css-tricks.com/box-sizing/
https://css-tricks.com/exploring-the-complexities-of-width-and-height-in-css/

the **box-sizing** property was introduced in CSS3. Though **box-sizing** has three possible values (content-box, padding-box, and border-box), the most popular value is border-box.

content-box
This is the initial and default value as specified by the CSS standard. The width and height properties include the content, but does not include the padding, border, or margin. For example, .box {width: 350px; border: 10px solid black;} renders a box that is 370px wide.

Here, the dimensions of the element are calculated as: width = width of the content, and height = height of the content. (Borders and padding are not included in the calculation.)

border-box
The width and height properties include the content, padding, and border, but do not include the margin. Note that padding and border will be inside of the box. For example, .box {width: 350px; border: 10px solid black;} renders a box that is 350px wide, with the area for content being 330px wide. The content box can't be negative and is floored to 0, making it impossible to use border-box to make the element disappear.

Here the dimensions of the element are calculated as: width = border + padding + width of the content, and height = border + padding + height of the content.

img -> height / width: auto  -> original
margin: 0 auto; -> center

Html validator
diffchecker on line

Antonio Bellet 193, Of 302, 7500000 Santiago,