<h1>Mongoose</h1>
--------

ODM para mapear documentoa de la base de datos ( royo doctrine o eloquent pero no relacional )

**odm** -> object document mapping , bases de datos no relacionales

**orm** -> object relational mapping , para bases de datos relacionales



<h3>Instalación</h3>
Primero instalamos el paquete npm de mongoose:

```bash
npm install --save mongoose
```



<h3>Configuración</h3>
Para establecer una conexión usaremos el siguiente código

```javascript
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost:27017/test', {//27017 es el puerto por defecto de mongo
  useNewUrlParser: true, 
  useUnifiedTopology: true
});
```

Podemos añadir el parametro usecreateIndex, para que se generen solos los indices de la bd, si la base de datos es pequeña está bien, pero si es un poco grande mejor no hacerlo porque gastará mucha memoria en crear todos los indices y mantenerlos.

```javascript
mongoose.connect('mongodb://localhost:27017/test', {
    useCreateIndex true, // true o false
    useNewUrlParser: true, 
  	useUnifiedTopology: true
});
```



<h3>Creación del modelo (colección)</h3>
Primero creamos una instanacia de un modelo, que irá directamente relacionada con un colección en la bd.

```javascript
const Cat = mongoose.model('Cat', {name: String, age: Number});
```

Una vez instanciada está colección prodremos usarlo para consultar en mongo, insertar, update etc.

Ejemplo de inserción de un documento en la colección Cat:

```javascript
const kitty = new Cat({name: 'Zilawddjian'});
kitty.save() //Guardamos el documento

Cat.find({}, {name:1, _id:0}); //Buscamos todos los documentos en la colección Cat
```

Si queremos tratar mas a fondo la colección por ejemplo, añadir validadores a los campos hemos de crear un schema de la siguiente manera:

```javascript
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const catSchema = new Schema({
  name: String,
  color: String,
  age: Number
});

const Cat = mongoose.model('Cat', catSchema);
```

Ahora vamos a hacer que age sea númerico y name sea obligatorio :

```javascript
const catSchema = new Schema({
  name: {
     type: String,
     required: true
  },
  color: {
    type: String
  },
  age: {
    type: Number,
    match: '[0-9]/g'
  }
});
```

Tabla de parametros que podemos añadir a cada campo del schema:

<table style="background:#071e24">
<thead>
<tr><th>Field property</th><th>Possible values</th><th>Description</th></tr>
</thead>
<tbody>
<tr>
<td><code>type</code></td>
<td><code>String</code>, <code>Number</code>, …</td>
<td>Sets a type for the field</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-default"><code>default</code></a></td>
<td>Anything</td>
<td>Sets a default value</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-required"><code>required</code></a></td>
<td><code>true</code></td>
<td>Adds a required validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-unique"><code>unique</code></a></td>
<td><code>true</code></td>
<td>Declares an unique index</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-enum"><code>enum</code></a></td>
<td>An array</td>
<td>Adds an enum validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-min"><code>min</code></a></td>
<td>A number</td>
<td>Sets a minimum number validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-max"><code>max</code></a></td>
<td>A number</td>
<td>Sets a maximum number validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-minlength"><code>minlength</code></a></td>
<td>A number</td>
<td>Sets a minimum length validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-maxlength"><code>maxlength</code></a></td>
<td>A number</td>
<td>Sets a maximum length validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-trim"><code>trim</code></a></td>
<td><code>true</code></td>
<td>Adds a trim setter</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-lowercase"><code>lowercase</code></a></td>
<td><code>true</code></td>
<td>Adds an lowercase setter</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-match"><code>match</code></a></td>
<td>A regex</td>
<td>Sets a regex validator</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-validate"><code>validate</code></a></td>
<td>An object</td>
<td>Adds a custom validator (see next part)</td>
</tr>
<tr>
<td><a href="https://mongoosejs.com/docs/api.html#schematype_SchemaType-validate"><code>set</code></a></td>
<td>A function</td>
<td>Adds a custom setter (see next part)</td>
</tr>
</tbody>
</table>

