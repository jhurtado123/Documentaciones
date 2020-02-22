<h1>MongoDB</h1>
-----

<p>Gestor de datos no relacional </p>
<h3>Instalación</h3>
```bash
sudo apt install -y mongodb
```



<h3>Configuración</h3>
```bash
sudo service mongod status
```

<p>Comprobamos que el servicio está iniciado y si no lo está lo iniciamos </p>

<h3>Importar base de datos</h3>

```bash
mongoimport --db companiesDB --collection companies --file data.json
```

