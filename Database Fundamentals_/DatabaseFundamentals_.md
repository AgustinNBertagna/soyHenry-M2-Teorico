> # ***Modulo 2 - Clase 9: Database Fundamentals_***

> ## ***Objetivos***

* ### *Establecer cimientos conceptuales en el ámbito de las bases de datos, comenzando con una introducción detallada a este campo.*

* ### *Definir conceptos fundamentales como la naturaleza de las bases de datos y la distinción crucial entre datos e información.*

> ## ***Introducción a bases de datos***

Las bases de datos desempeñan un papel fundamental en el mundo de la tecnología de la información al proporcionar un medio estructurado y eficiente para almacenar, gestionar y recuperar datos de manera organizada. Son la columna vertebral de numerosas aplicaciones y sistemas, abarcando desde aplicaciones empresariales hasta plataformas web y servicios en la nube. 

La importancia de las bases de datos radica en su capacidad para ofrecer acceso rápido y fiable a grandes volúmenes de información, facilitando la toma de decisiones informadas, mejorando la eficiencia operativa y permitiendo el desarrollo de aplicaciones escalables.

* ### **Antes de comenzar a diseñar una base de datos, es importante comprender algunos conceptos claves:**

  * ***Datos:*** Iniciemos definiendo qué son los datos. Los datos son representaciones simbólicas de un hecho o un concepto. Pueden ser, por ejemplo, números, textos, valores alfanuméricos o cualquier elemento que pueda almacenarse y ser procesado.

  * ***Información:*** La información, por su parte, es el resultado del procesamiento de esos datos, esto es, cuando los datos se organizan e interpretan de manera que adquieren un contexto y significado específicos. 

  * ***Base de datos:*** Finalmente, una base de datos es un conjunto organizado para recopilar, almacenar y gestionar datos de manera eficiente.

  Nuestro objetivo es almacenar datos de manera estructurada para que, cuando sea necesario, podamos procesarlos y obtener información significativa.

* ### **Entidades y atributos**

  Una entidad representa un objeto o concepto del mundo real que puede ser identificado, almacenado y gestionado en una base de datos.

  Estas entidades pueden ser objetos físicos como una persona, un producto o un lugar, o conceptos abstractos como un pedido o una transacción. 

  #### ***"Las características o propiedades de una entidad, las cuales denominaremos atributos, describen a la entidad y la información específica que ésta representa."***

  En resumen, una entidad es una representación organizada y estructurada de un objeto o concepto del mundo real y se utiliza para almacenar información relevante sobre ese objeto o concepto en particular, con sus respectivos atributos que lo definen.

  Ahora bien, la definición de estos modelos de entidad nos ayuda a planificar la estructura de cada tabla que se genera dentro de la base de datos. Diseñar y construir las tablas de la base de datos para mejorar su eficiencia puede ser un proceso complejo al principio, pero gracias a la normalización de datos tenemos formas de simplificarlo

* ### **Normalización de Datos**

  La normalización es un proceso en el diseño de bases de datos que busca organizar la información de manera eficiente y reducir la redundancia, mejorando la integridad de los datos. Este proceso implica dividir las tablas de la base de datos para evitar la repetición innecesaria de información y garantizar que los datos se almacenen de manera coherente.

  Existen reglas específicas para realizar este proceso de normalización de tablas definidas por formas normales, Estas formas normales son niveles de organización de una BDD con reglas específicas a cumplir Pero implementarlas de forma puntual  requiere un conocimiento más profundo del manejo de base de datos.

> ## ***Introducción a persistencia de datos***

* ### **¿Qué es?**

  La persistencia de datos es fundamental en el desarrollo de software pues nos permite almacenar y recuperar información a través del tiempo incluso cuando un programa o aplicación haya terminado su ejecución por cierre o actualización. Esto nos permitirá tener los datos disponibles más allá de la ejecución temporal de un programa.

  Existen diversas formas de lograr la persistencia de datos, obviamente dentro de ellas encontramos a las bases de datos que nos permiten almacenar y gestionar la información de una aplicación ya sea de forma relacional(SQL) o no relacional(NoSQL).

* ### **Sistemas de archivos y almacenamiento Local**
  
  La persistencia de datos se refiere a la capacidad de almacenar información de manera duradera, incluso cuando apagamos nuestros dispositivos, para acceder a esta en cualquier momento a futuro. Hay dos maneras principales de lograr esto: mediante sistemas de archivos y almacenamiento local.

  * #### ***Sistemas de archivos***

      Un sistema de archivos es una estructura utilizada por un sistema operativo para organizar y guardar datos en un dispositivo como un disco duro o memoria USB, a través de carpetas y archivos. Cada carpeta puede contener muchos archivos y estos archivos pueden almacenar datos.

      | **VENTAJAS** | **DESVENTAJAS** |
      |:------------:|:---------------:|
      |Simple de entender y usar.|Puede volverse desordenado si muchas aplicaciones usan muchos archivos.|
      |Cada aplicación puede tener su propio archivo de datos.|No es tan eficiente para buscar y organizar grandes cantidades de datos.|


  * #### ***Almacenamiento Local (Local Storage)***

      Dentro de los navegadores disponemos de herramientas que nos permiten tener un almacenamiento local y de sesión mediante la API Web Storage nativa. Esto permite que las aplicaciones puedan almacenar datos del lado del cliente utilizando la persistencia de datos con Local Storage o la información de una sesión con Session Storage.

      |**VENTAJAS**|**DESVENTAJAS**|
      |:------:|:---------:|
      |Facil de utilizar: Requiere pocas lineas de código.|El almacenamiento puede ser limitado dependiendo de las políticas de seguridad del navegador.|
      |Tiene más capacidad de almacenamiento que otras herramientas del navegador.|Capacidad de almacenamiento muy limitada, es mas útil para pequeños fragmentos de información.|
      |Beneficiosos para la seguridad del usuario ya que no son enviados automáticamente al servidor.|Al ser sincrónico, la carga de información puede llegar a bloquear otras tareas de la aplicación.|
      |Están disponibles de forma rápida y son accesibles de forma sincrónica.|Almacena datos como cadenas de texto. Datos más complejos pueden ser difíciles de manejar.|
      ||No es seguro para datos sensibles como contraseñas porque no cuenta con expiración automatica.|

  ***Ahora que hemos explorado cómo persisten los datos mediante sistemas de archivos y almacenamiento local, es importante entender cómo estructuramos esos datos. Aquí es donde entra en juego el concepto de formatos de almacenamiento.***

* ### **Formatos de almacenamiento**

  * ***XML (eXtensible Markup Language):*** Es un lenguaje de marcado que utiliza etiquetas para definir documentos que pueden almacenar, transportar y organizar datos de manera jerárquica y estructurada.

  * ***CSV (Comma-Separated Values):*** Es un formato de texto que representa datos tabulares utilizando comas u otros delimitadores para separar campos. Cada línea del archivo representa una fila y los valores se separan por comas (o algún otro delimitador).

  * ***YAML (YAML Ain't Markup Language):*** Es un formato de serialización de datos legible por humanos y fácil de escribir. Utiliza sangrías para definir estructuras jerárquicas y se centra en la legibilidad.

  * ***BSON (Binary JSON):*** Es una representación binaria del formato JSON que incluye tipos de datos adicionales, como fechas y binarios. Se utiliza principalmente en bases de datos NoSQL, como MongoDB.

  * ***Protobuf (Protocol Buffers):*** Es un formato de serialización desarrollado por Google que permite la serialización eficiente de datos estructurados. Utiliza un esquema binario y es eficiente en términos de espacio y velocidad.

  Uno de los formatos más comunes es el formato JSON. Este proporciona una estructura clara y legible para organizar datos, lo que lo hace ideal para almacenar información en el contexto del desarrollo web. Es un formato ligero de intercambio de datos que utiliza una sintaxis legible por humanos. Está basado en pares clave-valor y es fácil de entender para tanto humanos como máquinas. Ampliamente utilizado en la comunicación entre clientes y servidores web, configuración de aplicaciones y almacenamiento de datos estructurados.

  ```json
  {
    "nombre": "Juan",
    "edad": 30,
    "ciudad": "Ciudad de Ejemplo",
    "contacto": {
      "email": "juan@example.com",
      "telefono": "+123456789"
    },
    "intereses": ["programación", "viajes", "lectura"]
  }
  ```

  ***Nota:*** El uso de formatos de almacenamiento adecuados es esencial para garantizar que los datos se guarden y recuperen de manera eficiente. Al comprender los sistemas de archivos, el almacenamiento local y los formatos de almacenamiento, como desarrolladores podemos tomar decisiones informadas sobre cómo estructurar y gestionar datos en nuestras aplicaciones.
***