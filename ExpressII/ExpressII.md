># ***Modulo 2 - Clase 08: Express II_***

> ## ***Objetivos***

* ### *Profundizar en el concepto de servicios y comprender la columna vertebral de una aplicación Express, desempeñando funciones especializadas y cruciales.*

* ### *Explorar los middlewares como herramientas flexibles que moldean y optimizan el flujo de solicitudes y respuestas en nuestro servidor Express.*

* ### *Comprender qué son las validaciones y aprender cómo asegurarnos de que nuestra aplicación maneje información de manera segura.* 

> ## ***Servicios***

* ### **¿Qué es?**
    
    Los servicios representan segmentos específicos de lógica de negocio. En otras palabras, se definen como una parte puntual de la aplicación que "brinda servicio" a una funcionalidad específica de la aplicación.

    ***¿Cómo se diferencian los servicios de los controladores?*** Si bien los controladores manejan la lógica de manejo de solicitudes y respuestas, los servicios se centran en tareas más amplias y especializadas. Mientras que un controlador puede ocuparse de responder a una solicitud específica, un servicio manejará una funcionalidad completa, desde la autenticación hasta la gestión de bases de datos.

> ## ***Middlewares***

* ### **¿Qué es?**

    En el contexto de Express, un middleware es una función que tiene acceso a los objetos de solicitud (req), respuesta (res), y a la siguiente función en el ciclo de solicitud-respuesta de la aplicación (next). Se usan para realizar diversas acciones en el flujo de solicitud y respuesta. Ilustremos esta idea con la vida cotidiana. 

* ### **Estos se pueden dividir en dos categorías principales:**

  * #### ***Pre-built***

    Podemos ver a los middlewares pre-built como componentes listos para usar que ofrecen distintas funcionalidades que son específicas para cada tarea en Express. Entre los más utilizados se encuentran:
    
    * ***Morgan:*** Es un middleware de registro de solicitudes HTTP que facilita el seguimiento y la visualización detallada de la información de las solicitudes que llegan al servidor, como por ejemplo método HTTP, ruta de la solicitud, tiempo que tarda en obtener respuesta, etc.

    * ***express.json():*** Convierte automáticamente los cuerpos de las solicitudes con formato JSON, facilitando el manejo de datos enviados por los clientes. En términos más simples, convierte los datos JSON enviados en el cuerpo de la solicitud en un objeto JavaScript para que puedan ser fácilmente manipulados.

    * ***CORS (Cross-Origin Resource Sharing):*** Permite o restringe el acceso a recursos, un aspecto esencial para la seguridad en las solicitudes desde el navegador.

  * #### ***Middlewares personalizados***
    
    Un middleware personalizado se refiere a funciones o conjuntos de funciones que tú mismo creas para adaptar el flujo de manejo de solicitudes según las necesidades específicas de tu aplicación. Estos middlewares se insertan en la cadena de manejo de solicitudes entre el momento en que se recibe la solicitud y el momento en que se envía la respuesta. Se usan para realizar tareas adicionales, manipular datos, validar información, entre otros.

    ***¿Cuándo usar middleware personalizado?*** En situaciones donde los middlewares pre-built no cubren exactamente lo que necesitas o cuando deseas una lógica de manejo de solicitudes específica para tu aplicación.

   * #### ***Beneficios de los middlewares personalizados***
    
      1. ***Adaptabilidad:*** Puedes personalizar la lógica de manejo de solicitudes según los requisitos específicos de tu aplicación.

      2. ***Reutilización de Código:*** Al encapsular funciones específicas en middlewares personalizados, puedes reutilizar el código en diferentes partes de tu aplicación.

      3. ***Mejora la Mantenibilidad:*** Separar la lógica de manejo de solicitudes en middlewares facilita el mantenimiento del código.
    
   ### En resumen, la creación de Middlewares personalizados te brinda flexibilidad y control total sobre el flujo de manejo de solicitudes en tu aplicación de Express, permitiéndote adaptarla de manera precisa a tus necesidades.

   ### Contrastando con los pre-built, los middlewares personalizados son funciones creadas por el desarrollador para abordar necesidades específicas con relación a la tarea que esté implementando, mientras los pre-built son middlewares ya definidos que cualquier desarrollador puede consultar en el gestor de paquetes npm y usar dentro de sus proyectos.

> ## ***Validaciones***
* ### **Importancia de las validaciones en la app de backend**

    En un servidor, las validaciones son esenciales para garantizar la integridad, seguridad y eficiencia del sistema, asegurando la fiabilidad y consistencia general de la aplicación.

    Al validar los datos de entrada, puedes verificar que cumplen con las condiciones necesarias antes de procesarlos, evitando errores, protegiendo tu aplicación contra posibles vulnerabilidades y mejorando el desempeño de tu código. Además, permite también brindar una buena experiencia de usuario al proporcionar retroalimentación de parte de estos.

* ### **Estrategias de validación utilizando middlewares**

    En cuanto a las estrategias de validación utilizando middlewares, existen varias maneras de implementar validaciones en Express. Puedes crear middlewares personalizados que verifiquen los datos de entrada, asegurándote de que cumplan con ciertos criterios antes de pasarlos a la lógica principal de la aplicación. Además, también puedes aprovechar middlewares pre-construidos o bibliotecas especializadas en validaciones para simplificar este proceso.
***
> ## ***Cierre***

* ### **En conclusión...**

  * ***Profundizamos en Express:*** Y exploramos conceptos clave como servicios hasta la implementación de middlewares validadores.

  * ***Vimos qué es un Servicio y cuál es su diferencia con los Controladores:*** Luego, exploramos middlewares pre-construidos como `morgan`, `express.json()` y `cors`, y también creamos nuestros propios middlewares personalizados.

  ![ExpressII](./cierreExpressII.png)
***