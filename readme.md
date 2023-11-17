# SQL en MySQL 🚀

## ¿Qué es SQL?

SQL (Structured Query Language) es un lenguaje estándar para administrar bases de datos relacionales. Se utiliza para realizar consultas, actualizaciones, inserciones, y más, en bases de datos.

## Comandos SQL y Ejemplos 🎯

### Crear bases de datos

El comando para crear una base de datos es:

```sql
CREATE DATABASE registros;
```

### Borrar bases de datos

```sql
DROP DATABASE registros;
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
DROP TABLE usuarios;
```

### Crear llaves primarias

```sql
ALTER TABLE usuarios
ADD PRIMARY KEY (id);

```

### Crear llaves foráneas

```sql
ALTER TABLE pedidos
ADD CONSTRAINT usuario_id
FOREIGN KEY (usuario_id) REFERENCES usuarios (id);
```

### Insertar datos

```sql
INSERT INTO usuarios (nombre, email)
VALUES ('pepe', 'soypepe@gmail.com');
```

### Modificar datos

```sql
UPDATE usuarios
SET nombre = 'yanosoypepe' WHERE id = 1;

```

### Eliminar datos

```sql
DELETE FROM usuarios WHERE id = 1;
```

<br>
<br>

## Instrucciones de Consulta de datos 📊

### Consultar datos de una sola tabla

```sql
SELECT nombre, email FROM usuarios;
```


### Consultar datos en más de una tabla

Para consultar datos en múltiples tablas, se emplea la cláusula JOIN. Esto permite combinar datos de tablas relacionadas. Por ejemplo:

```sql
SELECT us.id, us.email FROM usuarios AS us
JOIN registros AS ta ON us.id = ta.id;
```


### Crear tablas a partir de consultas

Se puede utilizar la instrucción CREATE TABLE junto con SELECT para crear una tabla a partir del resultado de una consulta. Por ejemplo:

```sql
CREATE TABLE nuevo_registro AS
SELECT nombre, email, saldo FROM usuarios
WHERE saldo > 100;
```

### Revisar la estructura de una tabla

La estructura de una tabla se puede revisar utilizando el comando DESCRIBE o SHOW COLUMNS FROM. Por ejemplo:

```sql
SHOW COLUMNS FROM usuarios;
```

### Dar un alias a un campo

Para dar un alias a un campo en una consulta, se usa la palabra clave AS. Por ejemplo:

```sql
SELECT email AS this_correos FROM usuarios;
```

### Dar un alias a una tabla

Para dar un alias a una tabla en una consulta, se utiliza la palabra clave AS después del nombre de la tabla. Por ejemplo:

```sql
SELECT t.usuarios FROM tablas AS t;
```

<br>
<br>

## Instrucciones para utilizar funciones en cadena ⛓️

### CONCAT
El comando CONCAT se usa para concatenar dos o más cadenas en una sola:

```sql
    SELECT CONCAT(columna1, ' ', columna2) AS Concatenado
    FROM tabla;
```
Ejemplo:

```sql
    SELECT CONCAT('Hola', ' ', 'Mundo') AS Concatenado;
```

### SUBSTRING
SUBSTRING se emplea para extraer una parte específica de una cadena:

```sql
    SELECT SUBSTRING(columna, inicio, longitud) AS Subcadena
    FROM tabla;
```

### REPLACE
Para reemplazar una cadena, se utiliza la palabra reservada REPLACE:

```sql
    SELECT REPLACE(columna, 'valor_a_reemplazar', 'nuevo_valor') AS Reemplazado
    FROM tabla;
```
Ejemplo:

```sql
SELECT REPLACE('Hola Mundo', 'Mundo', 'Amigo') AS Reemplazado;
```

<br>
<br>

## Instrucciones para utilizar funciones numéricas 📠

### SUM

```sql
    SELECT SUM(columna) AS Total
    FROM tabla;
```
Ejemplo:

```sql
    SELECT SUM(Precio) AS Total FROM Productos;
```
### COUNT
COUNT cuenta el número de filas que cumplen con una condición especificada:

```sql
    SELECT COUNT(columna) AS Conteo
    FROM tabla;
```
Ejemplo:

```sql
    SELECT COUNT(*) AS TotalEmpleados FROM Empleados;
```
### MAX
MAX devuelve el valor máximo en una columna:

```sql
    SELECT MAX(columna) AS Maximo
    FROM tabla;
```
Ejemplo:

```sql
    SELECT MAX(Precio) AS PrecioMaximo FROM Productos;
```
### MIN
MIN devuelve el valor mínimo en una columna:

```sql
    SELECT MIN(columna) AS Minimo
    FROM tabla;
```
Ejemplo:

```sql
    SELECT MIN(Precio) AS PrecioMinimo FROM Productos;
```
### AVG
AVG se utiliza para calcular el promedio de valores en una columna numérica:

```sql
    SELECT AVG(columna) AS Promedio
    FROM tabla;
```
Ejemplo:

```sql
    SELECT AVG(Edad) AS EdadPromedio FROM Empleados;
```

<br>
<br>

## Instrucciones para utilizar funciones de fechas 📆

### DATEDIFF
DATEDIFF se usa para calcular la diferencia en días entre dos fechas:

```sql
    SELECT DATEDIFF(fecha1, fecha2) AS Diferencia
    FROM tabla;
```
Ejemplo:

```sql

```
### DAY
DAY extrae el día de una fecha:

```sql
    SELECT DAY(fecha) AS Dia
    FROM tabla;
```
Ejemplo:

```sql
    SELECT DATEDIFF('2023-11-16', '2023-11-10') AS DiferenciaDias;
```
### MONTH
MONTH extrae el mes de una fecha. Ejemplo: 
```sql
MONTH('2023-11-16') devuelve 11, representando noviembre.
```


### YEAR
Convierte una fecha en el año correspondiente. Ejemplo:

```sql
YEAR('2023-11-16') // devuelve 2023.
```

### DATE_FORMAT
DATE_FORMAT: Transforma una fecha al formato deseado. Ejemplo: 
```sql
DATE_FORMAT('2023-11-16', '%d/%m/%Y') // muestra la fecha como 16/11/2023.
```