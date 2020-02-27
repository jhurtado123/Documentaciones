<h1>Eslint</h1>
----

<p>Paquete NPM que te revisa el código y te "sanciona" si no estás siguiendo las reglas de Clean Code </p>


<h3>Instalación</h3>
```bash
npm install eslint --save-dev
```

Para iniciar la configuración de eslint  añadiomos la siguiente línea en el apartado scripts del package.json

```json
"init": "eslint --init",
```

A continuación ya podremos ejecutar el siguiente comando en la consola para poder configurar el eslint a nuestro gusto, es recomendable usar la plantilla de AirBnB

```bash
npm run init
```