# consultas2_sql-


## MODELO FISICO

![Modelo fisico](img/Empresa.jpg "modelo fisico")

## ESTRUCTURA BD

![EstructuraBD](img/estructura_BD.jpg "estructura_BD")

![Departamento](img/departamento.jpg "departamento")

## CONSULTAS

1. Obtener la lista de los apellidos de todos los empleados.
`SELECT apellido_empleado FROM Empleado;`


![Consulta1](img/consulta1.jpg "consulta1")

2. Obtener los apellidos de todos los empleados sin repeticiones.
`SELECT DISTINCT apellido_empleado FROM Empleado;`


![Consulta2](img/consulta2.jpg "consulta2")

3. Obtener todos los datos de los empleados que se apellidan 'Macias'.
`SELECT * FROM Empleado WHERE apellido_empleado = "Macias";`

![Consulta3](img/consuta3.jpg "consulta3")

4. Obtener todos los datos de los empleados que se apellidan "Diaz" y los que se apellidan "Rodriguez".  Usar OR o IN
`SELECT * FROM Empleado WHERE apellido_empleado LIKE "Macias" OR apellido_empleado LIKE "DUQUE";`


![Consulta4](img/consulta4.jpg "consulta4")

5. Obtener los nombres de los empleados que trabajan en el departamento 11
`SELECT nombre_empleado FROM Empleado WHERE id_departamento LIKE 11;`


![Consulta5](img/consulta5.jpg "consulta5")

6. Obtener todos los datos de los empleados cuyo apellido empiece por 'P'
`SELECT * FROM Empleado WHERE apellido_empleado LIKE "C%";`


![Consulta6](img/consulta6.jpg "consulta6")

7. Obtener el presupuesto total de todos los departamentos.

`SELECT (presupuesto_departamento) AS Presupuesto FROM Departamento;`


![Consulta7](img/consulta7.jpg "consulta7")


8. Obtener el número de empleados de cada departamento.

`SELECT id_departamento, COUNT(*) AS numero_empleados FROM Empleado GROUP BY id_departamento`


![Consulta8](img/consulta8.jpg "consulta8")

9. Obtener un listado completo de empleados, incluyendo por cada empleado los datos del empleado y de su departamento.

`SELECT * FROM Empleado, Departamento WHERE Empleado.id_departamento = Departamento.id_departamento;`


![Consulta9](img/consulta9.jpg "consulta9")

10. Obtener un listado completo de empleados, incluyendo el nombre y apellidos del empleado junto al nombre y presupuesto de su departamento.

`SELECT nombre_empleado, apellido_empleado, nombre_departamento, presupuesto_departamento FROM Empleado , Departamento WHERE Empleado.id_departamento = Departamento.id_departamento;`


![Consulta10](img/consulta10.jpg "consulta10")



11. Obtener los nombres y apellidos de los empleados que trabajen en departamentos cuyo presupuesto sea mayor a 100000000

`SELECT nombre_empleado , apellidos_empleado FROM empleado , departamento WHERE empleado.id_departamento = departamento.id_departamento AND presupuesto_departamento > 100000000;`


![Consulta11](img/consulta11.jpg "consulta11")


# Clausula inner join

#### Imagina que las bases de datos son como grandes archivos de información, y a veces, necesitamos cruzar datos de distintos archivos para obtener la imagen completa. El INNER JOIN es esa herramienta mágica que nos permite hacerlo, pero con una condición: solo nos muestra los resultados donde haya una coincidencia exacta.

![inner join](img/inner_join.png "inner join")


# Subconsultas

#### El Reto: Se plantea una pregunta clara: "¿Qué empleados trabajan en departamentos con un presupuesto mayor a 45,000?".

Misión 1 (La Subconsulta): En azul, resolvemos primero la pregunta interna: "¿Qué departamentos tienen ese presupuesto?". La imagen muestra cómo se interroga a la Tabla Departamento y se obtiene una "Lista de IDs Mágicos" (en este caso, los IDs 1 y 3, que corresponden a Ventas e IT).

Misión 2 (La Consulta Principal): En verde, usamos esos "IDs Mágicos" para preguntar a la Tabla Empleado. El algoritmo busca qué empleados tienen esos IDs en su columna id_departamento.

El Resultado: Se muestra la tabla final con los empleados que cumplen la condición, relacionándolos visualmente con sus departamentos originales.

Esta estructura de "misiones" ayuda a entender que una subconsulta no es más que una consulta pequeña que ayuda a resolver una más grande.

![subconsultas](img/subconsultas.png "subconsultas")

