# SQL en MySQL 🚀

## ¿Qué es SQL?

SQL (Structured Query Language) es un lenguaje estándar para administrar bases de datos relacionales. Se utiliza para realizar consultas, actualizaciones, inserciones, y más, en bases de datos.

## Comandos SQL y Ejemplos 🎯

### Crear bases de datos

El comando para crear una base de datos es:

```sql
CREATE DATABASE nombre_de_la_base_de_datos;
```

### Borrar bases de datos

```sql
DROP DATABASE nombre_de_la_base_de_datos;
```

### Crear tablas

```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    email VARCHAR(100)
);
```

### Borrar tablas

```sql
DROP TABLE nombre_de_la_tabla;
```

### Crear llaves primarias

```sql
ALTER TABLE nombre_de_la_tabla
ADD PRIMARY KEY (nombre_de_la_columna);

```

### Crear llaves foráneas

```sql
ALTER TABLE nombre_de_la_tabla
ADD CONSTRAINT nombre_de_la_llave_foranea
FOREIGN KEY (nombre_de_la_columna) REFERENCES otra_tabla (columna_referenciada);
```

### Insertar datos

```sql
INSERT INTO nombre_de_la_tabla (columna1, columna2, columna3)
VALUES (valor1, valor2, valor3);
```

### Modificar datos

```sql
UPDATE nombre_de_la_tabla
SET columna = nuevo_valor WHERE condicion;

```

### Eliminar datos

```sql
DELETE FROM nombre_de_la_tabla WHERE condicion;
```

<br>
<br>

## Instrucciones de Consulta de datos 📊

### Consultar datos de una sola tabla

Para consultar datos de una sola tabla, se utiliza la instrucción `SELECT`. Por ejemplo:

```sql
SELECT columna1, columna2 FROM nombre_de_la_tabla;
```


### Consultar datos en más de una tabla

Para consultar datos en múltiples tablas, se emplea la cláusula JOIN. Esto permite combinar datos de tablas relacionadas. Por ejemplo:

```sql
SELECT t1.columna1, t2.columna2 FROM tabla1 AS t1
JOIN tabla2 AS t2 ON t1.id = t2.tabla1_id;
```


### Crear tablas a partir de consultas

Se puede utilizar la instrucción CREATE TABLE junto con SELECT para crear una tabla a partir del resultado de una consulta. Por ejemplo:

```sql
CREATE TABLE nueva_tabla AS
SELECT columna1, columna2 FROM tabla_existente
WHERE condicion;
```

### Revisar la estructura de una tabla

La estructura de una tabla se puede revisar utilizando el comando DESCRIBE o SHOW COLUMNS FROM. Por ejemplo:

```sql
SHOW COLUMNS FROM nombre_de_la_tabla;
```

### Dar un alias a un campo

Para dar un alias a un campo en una consulta, se usa la palabra clave AS. Por ejemplo:

```sql
SELECT columna1 AS alias_columna FROM nombre_de_la_tabla;
```

### Dar un alias a una tabla

Para dar un alias a una tabla en una consulta, se utiliza la palabra clave AS después del nombre de la tabla. Por ejemplo:

```sql
SELECT t.columna1 FROM nombre_de_la_tabla AS t;
```

<br>
<br>

## Instrucciones para utilizar funciones en cadena ⛓️

### CONCAT
### SUBSTRING
### REPLACE
<br>
<br>

## Instrucciones para utilizar funciones numéricas 📠

### SUM
### COUNT
### MAX
### MIN
### AVG
<br>
<br>

## Instrucciones para utilizar funciones de fechas 📆

### DATEDIFF
### DAY
### MONTH
### YEAR
### DATE_FORMAT
