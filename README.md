# db-sql-tutorial
Un tutorial básico sobre Bases de Datos y SQL.

## Conceptos básicos sobre Bases de Datos:
### Base de Datos (DB):
Es un software capaz de almacenar, recuperar, modificar, eliminar y relacionar grandes cantidades de datos en forma de estructurada.
### Motor o Gestor de Base de Datos:
Es un software capaz de generar y mantener bases de datos a través de un conjunto de instrucciones definido por el usuario. 
Los más populares son MySQL, Oracle, MSServer, PosgreSQL y MongoDB, por mencionar algunos. Todos ellos utilizan lo que se denomina 
como "lenguaje de consulta" como intrucciones acerca de como generar y mantener bases de datos.
### SQL:
Es el lenguaje de consultas (o queries) más popular y estandarizado en la programación. Consiste de un lenguaje descriptivo y declarativo 
que se auxilia de la teoría de conjuntos para realizar consultas a DB's relacionales, como MySQL, MaríaDB, PosgreSQL, entre otros.
## Referencia rápida de SQL:
### Detalles comunes acerca del servidor de DB:
* Host: "localhost" (Para una instalación local)
* Puerto/Port: 3306 (Puuerto por defecto para las conexiones basadas en MySQL)
* Usuario: "root" (Usuario con privilegios de administrador por defecto en todas las DB's)
* Password: "" (No hay, por defecto. Se puede cambiar más adelante)
### Crear y utilizar una nueva DB:
```Sql
	CREATE DATABASE IF NOT EXISTS <nombre de la base de datos>;
	USE <nombre de la base de datos>;
```
### Crear una nueva tabla:
```Sql
	CREATE TABLE IF NOT EXISTS <nombre de la tabla>(
		<nombre de la columna 1> <tipo de dato>(<tamaño>) [NOT NULL] [DEFAULT <valor por defecto>] [PRIMARY KEY] [AUTO_INCREMENT],
		<nombre de la columna 2> <tipo de dato>(<tamaño>) [NOT NULL] [DEFAULT <valor por defecto>],
		<nombre de la columna 3> <tipo de dato>(<tamaño>) [NOT NULL] [DEFAULT <valor por defecto>],
		<nombre de la columna 4> <tipo de dato>(<tamaño>) [NOT NULL] [DEFAULT <valor por defecto>],
		...
		<nombre de la columna N> <tipo de dato>(<tamaño>) [NOT NULL] [DEFAULT <valor por defecto>]
	);
```
### Consultar datos de una tabla:
```Sql
	SELECT <lista de columnas a consultar> FROM <nombre de la tabla> [WHERE <columna> <operador> <valor>];
```
Si queremos todas las columnas de una tabla, basta con escribir un asterisco ("*") en lugar de toda la lista.
### Insertar nueva fila en una tabla:
```Sql
	INSERT INTO <tabla> (<lista de columnas>) VALUES(<lista de valores para cada columna>);
```
O bien:
```Sql
	INSERT INTO <tabla> SET <columna 1> = <valor 1>, <columna 1> = <valor 1>, ... <columna N> = <valor N>;
```
### Actualizar datos de una fila:
```Sql
	UPDATE <tabla> SET <columna 1> = <valor 1>, <columna 1> = <valor 1>, ... <columna N> = <valor N> [WHERE <columna> <operador> <valor>];
```
Si omitimos el "WHERE", TODOS los registros de la tabla se actulizarán! Así que nunca hay que olvidar eso.
### Eliminar filas:
```Sql
	DELETE FROM <tabla> WHERE <columna> <operador> <valor>;
```
Si quremos vaciar una tabla, podemos usar la siguiente instrucción:
```Sql
	TRUNCATE TABLE <tabla>;
```
