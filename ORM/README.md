# ORM (Object-Relational Mapping)

Es una técnica de programación que permite interactuar con una base de datos utilizando objetos en lugar de hacerlo directamente con consultas SQL. En términos simples, un ORM mapea las tablas de una base de datos a clases en el lenguaje de programación que estés usando, y las filas de esas tablas a instancias de esas clases.

## Ventajas

* Abstracción del SQL: No necesitas escribir SQL para realizar operaciones de base de datos. Esto facilita el desarrollo para aquellos que no están familiarizados con SQL.

* Portabilidad: Al abstraer las consultas SQL, es más fácil cambiar de un motor de base de datos a otro sin cambiar mucho el código.

* Mantenimiento: El código puede ser más limpio y fácil de mantener porque se manipulan objetos en lugar de consultas SQL.

* Seguridad: Muchos ORMs ofrecen protección contra inyecciones SQL, ya que manejan internamente la creación de consultas.

## Desventajas

* Rendimiento: En algunos casos, el uso de un ORM puede ser más lento que escribir consultas SQL optimizadas manualmente.

* Flexibilidad: Puede ser limitado en cuanto a las operaciones complejas que se pueden realizar en la base de datos.

* Curva de aprendizaje: Aunque puede simplificar muchas tareas, aprender a usar un ORM de manera efectiva puede llevar tiempo.