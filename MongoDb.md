# MongoDB 
---
## Introducción
MongoDB es una base de datos distribuida, basada en documentos y de uso general que ha sido diseñada para desarrolladores de aplicaciones modernas y para la era de la nube. Ninguna otra ofrece un nivel de productividad de uso tan alto. 
Es una base de datos documental, lo que significa que almacena datos en forma de documentos tipo JSON. Creemos que esta es la forma más natural de concebir los datos; frente al tradicional modelo de filas y columnas, esta es mucho más expresiva y potente. 

MongoDB es una auténtica plataforma de datos dotada de un completo paquete de herramientas que facilita notablemente el trabajo con datos a cualquier usuario, desde desarrolladores hasta investigadores o analistas. 

## Justificación
### ¿Qué problemas nos ayuda a resolver y cómo?
MongoDB nos ayuda a que nuestro proyecto o sistema sea escalable, que podamos modificar nuestra base de datos de acuerdo a las necesidades sin tener que crear otra base de datos y hacer las migraciones. En comparación con las bases de datos relacionales, las bases de datos NoSQL son más escalables y proporcionan un rendimiento superior , y su modelo de datos aborda varios problemas que el modelo relacional no está diseñado para abordar:
- Grandes volúmenes de datos estructurados, semiestructurados y no estructurados que cambian rápidamente
- Sprints ágiles, iteración rápida de esquemas y cambios frecuentes de código 
- Programación orientada a objetos que es fácil de usar y flexible. 
- Arquitectura escalable distribuida geográficamente en lugar de arquitectura costosa y monolítica 

La base de datos relacional se escala verticalmente, lo que significa que un solo servidor debe hacerse cada vez más poderoso para hacer frente a una mayor demanda. Es posible distribuir bases de datos SQL en muchos servidores, pero generalmente se requiere una ingeniería adicional significativa, y las características relacionales centrales como JOIN, integridad referencial y transacciones generalmente se pierden.

Mientras la base de datos no relacional se escala horizontalmente, lo que significa que, para agregar capacidad, un administrador de base de datos puede simplemente agregar más servidores básicos o instancias en la nube. La base de datos distribuye automáticamente los datos entre los servidores según sea necesario. 

MongoDB le permite satisfacer las demandas de las aplicaciones modernas con una plataforma de datos que le proporciona:

* El modelo de datos de documentos: le presenta la mejor manera de trabajar con datos.
* Un diseño de sistemas distribuidos, que le permite colocar datos de forma inteligente donde lo desee.
+ Una experiencia unificada que le da la libertad de correr en cualquier lugar, preparando su trabajo para el futuro y eliminando el bloqueo de proveedores.

## Marco Teórico
##### ¿Qué es NoSQL?
NoSQL abarca una amplia variedad de tecnologías de bases de datos diferentes que se desarrollaron en respuesta a las demandas presentadas en la creación de aplicaciones modernas:

Los desarrolladores están trabajando con aplicaciones que crean volúmenes masivos de nuevos tipos de datos que cambian rápidamente: datos estructurados, semiestructurados, no estructurados y polimórficos.

Atrás quedó el ciclo de desarrollo de la cascada de doce a dieciocho meses. Ahora los equipos pequeños trabajan en sprints ágiles, iterando rápidamente y presionando código cada semana o dos, algunas incluso varias veces al día.

Las organizaciones ahora están recurriendo a arquitecturas escalables utilizando tecnologías de software abiertas, servidores básicos y computación en la nube en lugar de grandes servidores monolíticos e infraestructura de almacenamiento.

Las bases de datos relacionales no se diseñaron para hacer frente a los desafíos de escala y agilidad que enfrentan las aplicaciones modernas, ni se crearon para aprovechar la capacidad de almacenamiento y procesamiento de productos disponibles en la actualidad.

##### Tipos de Bases de Datos NoSQL
- Las bases de datos de documentos emparejan cada clave con una estructura de datos compleja conocida como documento. Los documentos pueden contener muchos pares diferentes de clave-valor, o pares de claves-matriz, o incluso documentos anidados.
- Los almacenes de gráficos se utilizan para almacenar información sobre redes de datos, como las conexiones sociales. Las tiendas de gráficos incluyen Neo4J y Giraph.
- Las tiendas de valores clave son las bases de datos NoSQL más simples. Cada elemento individual en la base de datos se almacena como un nombre de atributo (o 'clave'), junto con su valor. Ejemplos de tiendas de valores clave son Riak y Berkeley DB. Algunos almacenes de valores clave, como Redis, permiten que cada valor tenga un tipo, como 'entero', que agrega funcionalidad.
- Los almacenes de columnas anchas como Cassandra y HBase están optimizados para consultas sobre grandes conjuntos de datos y almacenan columnas de datos juntos, en lugar de filas

##### Bases de datos de documentos
Cuando las bases de datos relacionales se introdujeron en la década de 1970, los esquemas de datos eran bastante simples y directos, y tenía sentido concebir los objetos como conjuntos de relaciones. Por ejemplo, un objeto de artículo podría estar relacionado con una categoría (un objeto), una etiqueta (otro objeto), un comentario (otro objeto), etc.

Debido a que las relaciones entre los diferentes tipos de datos se especificaron en el esquema de la base de datos, estas bases de datos relacionales podrían consultarse con un lenguaje de consulta estructurado estándar o SQL. Pero el entorno para los datos, así como la programación, ha cambiado desde el desarrollo de la base de datos SQL:

- El surgimiento de la computación en la nube ha reducido drásticamente los costos de implementación y almacenamiento, pero solo si los datos se pueden distribuir entre múltiples servidores fácilmente sin interrupciones. En una base de datos SQL compleja, esto es difícil porque muchas consultas requieren que se unan varias tablas grandes para proporcionar una respuesta. La ejecución de uniones distribuidas es un problema muy complejo en las bases de datos relacionales.

- La necesidad de almacenar datos no estructurados , como publicaciones en redes sociales y multimedia, ha crecido rápidamente. Las bases de datos SQL son extremadamente eficientes para almacenar información estructurada, y son necesarias soluciones o compromisos para almacenar y consultar datos no estructurados.

- Los métodos de desarrollo ágiles significan que el esquema de la base de datos debe cambiar rápidamente a medida que evolucionan las demandas. Las bases de datos SQL requieren que su estructura se especifique de antemano, lo que significa que cualquier cambio en el esquema de información requiere que las sentencias ALTER que requieren mucho tiempo se ejecuten en una tabla.

En respuesta a estos cambios, han surgido nuevas formas de almacenar datos (por ejemplo, bases de datos NoSQL) que permiten agrupar los datos de forma más natural y lógica, y que aflojan las restricciones en el esquema de la base de datos. Una de las formas más populares de almacenar datos es un modelo de datos de documentos, donde cada registro y sus datos asociados se consideran un "documento". En una base de datos de documentos, como MongoDB, todo lo relacionado con un objeto de base de datos se encapsula entre sí. Almacenar datos de esta manera tiene las siguientes ventajas:

- Los documentos son unidades independientes que mejoran el rendimiento (los datos relacionados se leen de forma contigua en el disco) y facilita la distribución de datos a través de múltiples servidores al tiempo que preserva su localidad.

- La lógica de la aplicación es más fácil de escribir. No tiene que traducir entre objetos en su aplicación y consultas SQL, solo puede convertir el modelo de objetos directamente en un documento.

- Los datos no estructurados se pueden almacenar fácilmente , ya que un documento contiene las claves y valores que requiere la lógica de la aplicación. Además, se evitan migraciones costosas ya que la base de datos no necesita conocer su esquema de información de antemano.

- Las bases de datos de documentos generalmente tienen motores de consulta muy potentes y funciones de indexación que facilitan y agilizan la ejecución de muchas consultas optimizadas diferentes. La fortaleza del lenguaje de consulta de una base de datos de documentos es un diferenciador importante entre estas bases de datos.

 Los documentos de MongoDB están codificados en un formato similar a JSON, llamado BSON, que facilita el almacenamiento, es un ajuste natural para las metodologías modernas de programación orientada a objetos, y también es ligero, rápido y transitable.

> Además, MongoDB admite consultas completas e índices completos, distinguiéndolo de otras bases de datos de documentos que dificultan las consultas complejas o requieren una capa de servidor separada para habilitarlas. Sus otras características incluyen fragmentación automática, replicación y más.

### NoSQL vs SQL
|           |SQL        |NoSQL      |
|-----------|-----------|-----------|
|**Tipo**|Un tipo (base de datos SQL) con pequeñas variaciones.|Muchos tipos diferentes, incluidos almacenes de valores clave, bases de datos de documentos , almacenes de columna ancha y bases de datos de gráficos|
|**Historia de Desarrollo**|Desarrollado en la década de 1970 para hacer frente a la primera ola de aplicaciones de almacenamiento de datos.|Desarrollado a finales de la década de 2000 para hacer frente a las limitaciones de las bases de datos SQL, especialmente la escalabilidad, los datos multiestructurados, la distribución geográfica y los sprints de desarrollo ágiles|
|**Ejemplos**|MySQL, Postgres, Microsoft SQL Server, Oracle Database|MongoDB, Cassandra, HBase, Neo4j   
|**Modelo de almacenamiento de datos**|Los registros individuales (p. Ej., "Empleados") se almacenan como filas en tablas, y cada columna almacena un dato específico sobre ese registro (p. Ej., "Gerente", "fecha de contratación", etc.), como una hoja de cálculo. Los datos relacionados se almacenan en tablas separadas y luego se unen cuando se ejecutan consultas más complejas. Por ejemplo, 'oficinas' podrían almacenarse en una tabla y 'empleados' en otra. Cuando un usuario desea encontrar la dirección de trabajo de un empleado, el motor de la base de datos une las tablas 'empleado' y 'oficina' para obtener toda la información necesaria.|Varía según el tipo de base de datos. Por ejemplo, los almacenes de valores clave funcionan de manera similar a las bases de datos SQL, pero tienen solo dos columnas ('clave' y 'valor'), con información más compleja a veces almacenada como BLOB dentro de las columnas de 'valor'. Las bases de datos de documentos eliminan por completo el modelo de tabla y fila, almacenando todos los datos relevantes en un solo 'documento' en JSON, XML u otro formato, que puede anidar valores jerárquicamente.|
|**Esquema**|La estructura y los tipos de datos son fijos de antemano. Para almacenar información sobre un nuevo elemento de datos, se debe modificar toda la base de datos, tiempo durante el cual la base de datos se debe desconectar.|Típicamente dinámico, con algunas reglas de validación de datos obligatorios. Las aplicaciones pueden agregar nuevos campos sobre la marcha y, a diferencia de las filas de la tabla SQL, los datos diferentes pueden almacenarse juntos según sea necesario. Para algunas bases de datos (p. Ej., Almacenes de columna ancha), es un poco más difícil agregar nuevos campos dinámicamente.|
|**Modo de desarroll**|Mezcla de tecnologías abiertas (por ejemplo, Postgres, MySQL) y de código cerrado (por ejemplo, Oracle Database)|Tecnologías abiertas|
|**Admite transacciones ACID de registros múltiples**|Sí|Sobre todo no. MongoDB 4.0 y posteriores admiten transacciones ACID de documentos múltiples.|
|**Manipulación de Datos**|Lenguaje específico que usa las instrucciones Select, Insert, Update, Delete, SELECT fields FROM tablas WHERE id=1|A través de API orientadas a objetos|
|**Consistencia**|Se puede configurar para una fuerte consistencia|Depende del producto. Algunos proporcionan una fuerte consistencia (por ejemplo, MongoDB, con consistencia ajustable para lecturas) mientras que otros ofrecen una consistencia eventual (por ejemplo, Cassandra).|

## Conclusión
Si el proyecto que desea realizar lo tiene pensado que será cada vez más grande, tiene que pensar que su base de datos tiene que ser escalable. MongoDB ofrece escalibilidad y buen redimiento y es especial para las operaciones complejas. 

## Bibliografía
<https://www.mongodb.com/nosql-explained>
<https://www.mongodb.com/document-databases>
<https://www.mongodb.com/collateral/mongodb-architecture-guide>