# SQL-Eval
Evaluación 
Sección 1: Preguntas teóricas (20 puntos - 20 minutos)

Define con tus palabras qué es una base de datos. (2 pts).

Una base de datos es un arreglo genérico de datos, su función es presentar un fácil acceso y manejo de los mismos; en Ciencia de Datos se acostumbra separar a estos arreglos en 2 tipos, relacionales y no relacionales, sin embargo en aplicaciones funcionales hay otras estructuras muy utilizadas como lo serían archivos de excel (.xlm) que son Hojas de Cálculo o hasta archivos tipo XLS (.xls).


Menciona dos diferencias entre bases de datos relacionales y NoSQL. (2 pts).
Una de las principales diferencias entre las bases relacionales y NoSQL (no relacionales), es su estructura, las bases de datos relacionales (SQL) tienen una estructura de "tablas" para su orden es decir, una estructura de filas y columnas; siendo la columna más importante de cada tabla la llamada "llave primaria" que es la utilizada para la relación entre las diferentes tablas. 

La estructura de las bases de datos no relacionales (NoSQL),  no tienen la obligación de seguir una estructura de tablas con filas y columnas, ni tienen la obligación de tener una llave primaria (columna con el identificador más importante de la tabla), para consultar el acceso de los datos se utilizan queries (solicitudes) que permiten el acceso a datos particulares y heterogeneos.

El objetivo de las bases de datos relacionales (SQL) es generar método de resguardo y acceso a información para datos que tienen una estructura fácil de definir y que puede ser facilmente estandarizable, como puede ser la base de datos de una primaria pequeña, donde se espera que todos los alumnos tengan 2 apellidos (España y la mayoría de los países de LATAM), y no existan cambios en los apellidos por situaciones como latinización del apellido (personas originalmente nacidas en países donde se usa otro alfabeto), matrimonio (donde se adopta el apellido del cónyuge). En estos casos, se escalan usualmente de forma vertical; más tablas y más alumnos con el mismo estándar para los apellidos.

El objetivo de las bases de datos no relacionales (NoSQL) es generar método de resguardo y acceso a información para datos que tienen una estructura que no es fácil de definir y que dificilmente es estandarizable, como bases de datos nacionales donde que pese a que existen usualmente identificadores universales como los "números de seguridad social" o bien el DNI (Documento Nacional de Identidad) en España, muchos residentes de origen extranjero no poseen o en ocasiones existieron errores al momento de generar el DNI (la lógica de la estructura es incorrecta), des decir un DNI verídico con un error en la estructura lógica al momento de generarse o bien donde los apellidos de una persona con el tiempo pueden cambiar por situaciones como matrimonio o latinización del apellido y nombres.

Escribe el nombre de dos gestores de bases de datos y un caso de uso de cada uno. (2 pts)

Para bases de datos SQL (relacionales) -> MySQL
Para bases de datos NoSQL (no relacionales) -> MongoDB

¿Qué representa un modelo entidad-relación y qué elementos lo componen? (2 pts)

Un modelo entidad-relación (ER) es una representación gráfica y conceptual de la estructura de una base de datos (similar a una prueba de escritorio), que describe las entidades (objetos del mundo real), sus características y las relaciones entre ellas. Es una parte fundamental en el diseño de bases de datos relacionales.
Donde:

Entidades: Representan construcciones concepturales que engloban de forma bien un estructura como "alumnos, productos, calificaciones, facturas (invoice tickets).
Atributos: Representan las características bien definidas que se asocian a una entidad, para la estructura de "alumnos", los atributos podrían ser "nombres, edad, apellidos".

¿Qué es la cardinalidad en un diagrama ER? Da un ejemplo. (2 pts).

La cardinalidad en un Diagrama ER (Entidad-Relación) define la cantidad de instancias de una entidad que pueden asociarse con otra de acuerdo a su relación(es), hay 3 tipos.

Cardinalidad 1:1 (Uno a uno): Es el tipo de relación donde la existe una sola relación entre 2 entidades particulares, como ejemplo sería el "nombre completo" y  "CURP" (Clave Única de Población en México), cada alumno debe tener un nombre completo único, y una clave poblacional nacional única (DNI en España o CURP en México)

Uno a Muchos (1:N): Es el tipo de relación donde existe una entidad que puede tener relación a más de otra entidad de una forma bien definida, como ejemplo un registro de automóviles donde para que exista la relación mínimo cada persona debe ser dueña de un auto pero un coleccionista puede ser dueño de cientos de autos únicos.

Muchos a Muchos (M:N): Es el tipo de relación donde existen entidades (más de una) que pueden tener relación con otras entidades (más de una) de una forma bien definida, tales como la relación "estudiante-materia" en una escuela, en donde más de un estudiante puede comprar una bebida en la cafetería (agua, jugo, café, leche o Coca-Cola) pero al mismo tiempo pueden comprar más de una de esas bebidas o bien ninguna.

Explica brevemente qué es la normalización y su objetivo. (2 pts)

La normalización en base de datos relacionales (SQL) es el proceso donde se trata de simplificar las relaciones con la intención de hacer más eficiente y optimizar las mismas, esto se hace principalmente eliminando redundancias, esto implica por ejemplo que no exista duplicidad de llaves primarias (también llamadas columnas principales)  en este supuesto se simplifica a una sola tabla. 

¿Cuál es la diferencia entre una clave primaria y una clave foránea? (2 pts)
La clave primaria en una base de datos relacional es la columna principal de una determinada tabla, es aquella columna que debe tener un valor siempre para cada fila y tiene que existir para intersección fila-colunma (no puede ser un valor tipo NULL), y tiene que ser única para cada registro (también llamada fila o renglón), un ejemplo del mundo real es el DNI donde cada ciudadano español debe tener uno diferente.

La clave foránea en una base de datos relacional es una columna diferente a la principal de la tabla, puede tener un valor o no tenerlo (puede ser un valor tipo NULL), no tiene la obligación de ser única para cada registro de cada tabla independiente, esta misma columna, un ejemplo de mundo real sería un producto que está repetido en muchos pedidos.

Menciona dos funciones de texto en SQL y da un ejemplo de uso. (2 pts)
 1era función:

Función AVG, viene del inglés que significa "promedio", nos entrega el valor promedio de un argumento (una columna) de una determinada tabla, la notación es AVG ().

Ejemplo en sintaxis de mysql: 

SELECT nombre_alumno, AVG(calificación_examen)
       FROM alumno
       GROUP BY nombre_alumno;
       
Esta instrucción debe calcular el promedio en las calificaciones de exámenes para un alumno de nombre particular.

Función COUNT, viene del inglés que significa "contar", nos entrega el valor de la cantidad de filas (registros) en una determinada tabla ya sea tales registros presenten no valores del tipo "NULL" y coincidad con un condición. 

Ejemplo en sintaxis de mysql:

SELECT dueño, COUNT(*) FROM mascotas GROUP BY dueño;

Esta instrucción debe entregar la cantidad de mascotas para cada dueño en una tabla que de dueños de mascotas. 

¿Qué hace la función AVG() en SQL? ¿Con qué tipo de datos se usa? (2 pts)
Función AVG, viene del inglés que significa "promedio", nos entrega el valor promedio de un argumento (una columna) de una determinada tabla.

¿Para qué sirve IS NULL en una consulta SQL? (2 pts)
Es para comprobar si los argumentos de una determinada columna existen o no, arroja como resultados particulares valores "booleanos" 1 ó 0 (si no es NULL y sí es NULL respectivamente).
