<h1>Handlebars</h1>

----

<p>Motor de renderizado de plantillas para express </p>



<h3>Instalación</h3>

```bash
npm install hbs --save
```



<h3>Configuración</h3>

<p>Indicamos a express que el que se va a encargar de renderizar las plantillas va a ser handlebars(hbs)</p>

```javascript
app.set('view engine', 'hbs');
```

<p>Por defecto coje las plantillas que están dentro de la carpeta views</p>

<p>Para renderizar la vista simplemente</p>

```javascript
res.render('index');
```



<h3>Documentación</h3>

<ul><li><a href="https://handlebarsjs.com/guide/#what-is-handlebars">Documentación oficial</a></li></ul>