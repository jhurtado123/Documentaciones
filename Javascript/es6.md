<h1>ES6+</h1>
--------------



<h3>Spread (...)</h3>
<p>Divide un objeto iterable en valores individuales</p>
```javascript
function sum(num1, num2) {
	return num1 + num2;
}
const nums = [1, 5];

sum(...nums);
```

<p>También puede servir para que los valores de un array pasen a otro array</p>
```javascript
const array1 = [2, 3, 4];
const array2 = [1, ...array1, 5, 6, 7 ];
console.log(array2);  // [ 1, 2, 3, 4, 5, 6, 7 ]

//O si lo queremos añadir al final
const array1 = [2, 3, 4];
const array2 = [1];
array2.push(...array1); // [1,2,3,4]
```

<p>Y para juntar varios arrays</p>
```javascript
const array1 = [1];
const array2 = [2];
const array3 = [...array1, ...array2, ...[3,4,5]]; //[1,2,3,4,5];
const array4 = [6];

function sumArrays(a, b, c, d, e, f) {
    return a+b+c+d+e+f;
}

sumArrays(...array3, ...array4);
```

<p>O para agrupar varios parametros envíados a una función en un array</p>
```javascript
function namesToArray(...names) {
	console.log(names);//['name1', 'name2', 'name3']
}
namesToArray('name1', 'name2', 'name3')
```





<h3>Desestructuración de objetos y arrays</h3>
<p>Extraer datos de arrays o objetos y añadir el valor a variables </p>
```javascript
//Con objetos
let object = {
	name = 'object',
    color = 'red',
    width = '200'
}
const {name, color, width} = object;
console.log(name, color, width); // object red 200

//Con arrays
const [num1, num2] = [1,3];
console.log(num1, num2); //1 3

//Con funciones
function showValues({name, color, width}) {
    console.log(name, color, width); // object red 200
}
showValues(object);

//También podemos añadir valores por defecto en caso de que el valor no exista
function showValues({name, color, width, height = 400}) {
    console.log(name, color, width, height); // object red 200 400
}
showValues(object);

```

