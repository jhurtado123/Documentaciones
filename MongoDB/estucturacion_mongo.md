<h1>Estructuración DB en Mongo ( Tips )</h1>

---------



<h3>Referencias con SQL</h3>

<table style="background:#071e24">
    <thead>
    	<tr>
        	<th>Mysql</th>
           <th>Mongo</th>
        </tr>
    </thead>
    <tbody>
    	<tr>
        	<td>Table</td>
            <td>Collection</td>
        </tr>
        <tr>
        	<td>Row</td>
            <td>Document</td>
        </tr>
        <tr>
        	<td>Column</td>
            <td>Field</td>
        </tr>
        <tr>
        	<td>Joins</td>
            <td>Embedded documents, linking</td>
        </tr>
    </tbody>
</table>



<h3>Tips a la hora de organizar las colecciones</h3>

relación 1-1 -> subdocumentos

relacion de 1-pocos -> array de subdocmentos

relacion de 1-muchos -> dos coleciones