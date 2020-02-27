<h3>Pasos para crear un proyecto con express (express-generator)</h3>

----------

Creamos la carpeta contenedora del proyecto

```bash
mkdir example
cd example
```

Ejecutamos el siguiente comando 

```bash
npx express-generator --hbs --git 
```

El `--hbs`nos añade la dependencia del handlebars como motor de vistas y el `--git`nos añade un .gitignore al proyecto ya  configurado.

Enlace con la documentación y más parametros:

https://expressjs.com/es/starter/generator.html

Una vez termine ejecutamos  el siguiente comando para instalar los paquetes

```bash
npm install
```

Ahora ya tenemos los paquetes por defecto del express-generator instalados, ahora vamos a instalar los nuestros propios.

Para paquetes de producción :

```bash
npm install --save mongoose body-parser dotenv
```

Para paquetes de dev:

```bash
npm install --save-dev eslint nodemon
```

Pasamamos a añadir los scripts que necesitaremos para usar la aplicación, los añadimos en package.json en el apartado scripts :

```json
"start": "node app.js",
"init": "eslint --init",
"start-dev": "nodemon app.js"
```

Para configurar eslint ejecutaremos 

```bash
npm run init
```

Y el último paso será reemplazar todos los require con `var` a require con `const`