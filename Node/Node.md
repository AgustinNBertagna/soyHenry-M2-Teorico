> # ***Modulo 2 - Clase 4: Node***

> ## ***Objetivos***

* ### *Conocer el runtime node JavaScript.*

* ### *Comprender la estructura y configuración de un proyecto de node.*

* ### *Conocer la librería NPM y aprender su uso para instalar dependencias.*

* ### *Entender la gestión de versiones en node.*

> ## **NodeJS**

Cuando queríamos agregar lógica de JavaScript a un archivo de HTML utilizábamos la etiqueta script. Estas implementaciones funcionaban ya que los navegadores cuentan con un motor que permite ejecutar código JavaScript.

* ### **¿Sabías que cada navegador tiene su propio motor?**

  * ***El motor de Chrome es V8.***

  * ***El motor de Firefox es SipderMonkey.***

  * ***El motor de Safari es JSCore.***

  * ***El motor de Explorer es Chakra.***

* ### ¿Qué sucede cuando no estamos trabajando dentro de un navegador y debemos ejecutar scripts? ***Es aquí donde nace Node.***

* ### **¿Qué es?**

    Node es un entorno de ejecución de JavaScript, también llamado runtime. Imagina a Node como una especie de contenedor que tiene todo lo necesario para ejecutar código JavaScript: APIs propias, funciones integradas, etc. De esta manera, podemos trabajar con JavaScript sin depender de los navegadores y sus motores, ya que node trabaja como un motor en nuestra computadora.

* ### **Elementos**
    
    Node fue desarrollado a partir del motor V8 de Chrome. Este utiliza el lenguaje C++ y una librería llamada libuv escrita en C.  
    Esto hace posible la creación de servidores y la construcción de APIs de forma rápida y escalable, así como el uso de un solo lenguaje tanto para el desarrollo de software. Este entorno de ejecución es utilizado por grandes empresas...

> ## ***Modulos***

* ### **¿Qué es?**
    
    Este concepto se refiere a un conjunto de código organizado y encapsulado que se puede reutilizar en otras partes de un programa. Estos ayudan a estructurar y mantener proyectos ya que dividen el código en piezas más pequeñas y manejables.  

    Node proporciona un sistema de módulos que permite la exportación e importación. Es decir, que nos permite importar y exportar código de un archivo a otro. Cada módulo tiene su propio ámbito, lo que significa que las variables y funciones definidas en un módulo no están automáticamente disponibles en otros módulos, a menos que sean exportados.

    Para exportar código desde un módulo se utiliza un objeto llamado ***`exports`***. Guardaremos en este objeto las propiedades y valores que se expondrán para ser reutilizados desde cualquier otra parte del proyecto. 

    ```javascript
    // archivo1.js

    function creadorDeNombre(nombre) {
      const miNombre = nombre + 'JavaScript';
      return miNombre;
    }

    module.exports = creadorDeNombre;
    ```
    
    Para importar ese código en otro archivo se utiliza la función **require()**, que recibe por argumento la ruta (path) de la ubicación del módulo desde la cual se realiza la exportación.

    ```javascript
    // archivo2.js

    const creadorDeNombre = require("./archivo1.js");
    creadorDeNombre("Este es un nombre");
    ```

> ## ***[NPM](https://www.npmjs.com/) (Node Package Manager)***

* ### **¿Qué es?**
    
    Node cuenta con una librería open source gigante con muchos módulos que nos ayudarán a desarrollar nuestros proyectos reduciendo la cantidad de lógica y código que debe implementarse. Esto es gracias a que, en lugar de nosotros construir este código, utilizaremos el que otras personas ya han hecho.  

    NPM también tiene su propia clasificación. A este tipo de herramienta se lo conoce como gestor de paquetes. Existen muchos otros como Bun, Yarn o Pip.

    Se le llama paquete a un conjunto de módulos (código) que podemos descargar e instalar en nuestro proyecto.

    NPM gestiona estos paquetes porque facilita la instalación, manejo y compartición de paquetes que podemos usar dentro de nuestros proyectos.

    Cuando utilizamos módulos externos dentro de nuestra aplicación, nos referimos a estos como una dependencia.

* ### **Beneficios de utilizar Modulos externos**

  * ***Reutilización del código:*** Suelen ser soluciones a problemas comunes. Con ellos evitarás escribir código desde cero para funcionalidades estándar.

  * ***Eficiencia en el desarrollo:*** Optimizan el proceso de desarrollo al proporcionar implementaciones ya probadas y mejoradas.

  * ***Colaboración y comunidad:*** Te integras en la comunidad de desarrolladores. También podrás aprovechar al máximo la documentación y foros relacionados con estos módulos.

  * ***Actualizaciones:*** Suelen ser mantenidos por la misma comunidad. Te beneficiarás de tales mejoras de rendimiento, correcciones de errores y nuevas características.

  * ***Foco en el core de tu app:*** Estas soluciones te permitirán concentrarte en desarrollar las características únicas y específicas de tu aplicación.

  * ***Ecosistema de desarrollo:*** Muchas plataformas y frameworks fomentan el uso de módulos de terceros para crear un ecosistema robusto.

> ## ***Versionado***

* ### **¿Qué es?**
    
    Node nos permite manejar las versiones de los paquetes. Es decir, podremos controlar y definir qué versiones de los paquetes queremos utilizar en nuestro proyecto.  

    Node utiliza un archivo llamado package.json para definir las dependencias de un proyecto y especificar sus versiones.

    En el archivo package.json, las dependencias pueden tener diversas formas de versionado, pero la convención común es utilizar el formato semántico SemVer. Este consta de tres números separados por puntos

    ***`MAJOR:`*** Se incrementa cuando hay cambios incompatibles con versiones anteriores. No funcionará para proyectos con versiones menores al valor.

    ***`MINOR:`*** Se incrementa cuando hay nuevas características o mejoras compatibles con versiones anteriores. Se introducen nuevas funcionalidades, pero no se rompen las antiguas (retro-compatibles).

    ***`PATCH:`*** Se incrementa para correcciones de errores y parches menores. Es retro-compatible.
    
    Otra cosa que nos permite ver el versionado qué otras versiones son compatibles gracias a los símbolos ^ y ~.

    ```JSON
    {
      "dependencies": {
        "express": "^4.17.1",
        "lodash": "~4.17.21"
      }
    }
    ```
    Esto indica que el proyecto depende de "express" en cualquier versión compatible con la 4.17.1 pero no la 5.0.0, y de lodash en cualquier versión compatible con la 4.17.21 pero no la 4.18.0.

    El manejo de versiones en Node.js ayuda a prevenir problemas de compatibilidad y a garantizar que todos los desarrolladores que trabajan en un proyecto compartan las mismas versiones de las dependencias.

> ## ***¡Mejora la calidad de tu código!***

* ### Better the quality, less the work
    
    La calidad del código es una inversión a mediano y largo plazo ya que nos permitirá tener un código escalable y fácil de manipular.

* ### Pasos para mejorar tu código

  1. ***Identificar el problema.***

  2. ***Explorar todas las soluciones posibles.***

  3. ***Aplicar los cambios de la solución más adecuada.***

  4. ***Evaluar los resultados en comparación con los anteriores.***
***
> ## ***Cierre***

* ### En conclusión...

  * ***Hemos explorado las bases fundamentales de Node:***, un entorno de ejecución. Además, abordamos el concepto de módulos. La capacidad de exportar e importar módulos nos permite construir aplicaciones más organizadas y mantenibles.

  * ***Revisamos el manejo de versiones:*** Las dependencias nos garantizan la coherencia y prevención de problemas de compatibilidad.

  ![Node](./cierreNode.jpg)