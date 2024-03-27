#Busquedas  Condicionales

# Operadores de Comparación

| Operador | Descripción | 
|-- | -- |
| $eq | igual|
| $gt | Mayor que |
| $gte | Mayor o Igual |
| $ in | Buscar un elemenit en array|
| $it| Menor que|
| $ lte| Menor o igual|
| $ne | Todos los elementos que no sean iguales |
| $nin | Ninguno de los valores del arreglo|


## Busquedas

_Selecciona todos los documentos de una colección_


```m
db.libros.find()
db.libros.find({})
```

_Seleccionar todos los documentos de la coleccion libros donde la editorial sea Biblio_

```m
db.libros.find({editorial: 'Biblio'})
```

_Seleccionar todos los documentos de la coleccion libros donde el precio sea igual a 25_


```m
db.libros.find({precio: 25 })

```
## Busquedas con operadores logicos

**Sintaxi**

```
{<columna>: {<operador>:<valor>}, ...}

```

_Seleccionar todos aquellos documentos de la coleccion libros donde el precio sea mayor a 25_

```m
db.libros.find({precio: {$gt:25}})

```

_Seleccionar aquellos documentos de la coleccion libros donde el precio sean mayores o iguales a 20_

```m
 db.libros.find({precio:{$gte:20}})
```

_Seleccionar aquellos documentos sea Biblio o Planeta_

```m
db.libros.find({editorial:{$in:['Biblio','Planeta']}})
```

## Recuperar una sola fila


_Seleccionar aquellos documentos que sean biblio o planeta pero mostrando solamente el primer documento encontrado_

```m
db.libros.findOne({editorial:{$in:['Biblio','Planeta']}})
```

```m
db.libros.findOne({})
```