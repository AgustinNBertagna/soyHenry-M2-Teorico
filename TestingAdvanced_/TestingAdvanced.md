> # ***Modulo 2 - Clase 4: Node***

> ## ***Objetivos***

* ### *Comprender el testing de código Javascript a través del uso de Jest.*

* ### *Aprender la implementación y sintaxis básica de Jest.*

* ### *Conocer qué es un Mock y cómo funciona.*

* ### *Entender la resolución de un ejercicio recreando un flujo real de trabajo, en el cual se iniciará por el desarrollo del test y luego la implementación bajo TDD.*

> ## ***[Jest](https://jestjs.io/)***
* ### **¿Qué es?**
  
  Jest es un framework de testing diseñado para brindar un conjunto de tests (a los que llamaremos suites) para proyectos de JavaScript. Puede pensarse como un kit de herramientas y reglas que permiten testear nuestro código de una manera simple y eficiente.

  Jest además, cuenta con funciones integradas llamadas mocks que permiten imitar la conducta de nuestro código de manera controlada y de las que hablaremos al final de la clase.

* ### **Características**

  * ***Configuración:*** Simplicidad y facilidad de uso. Puedes comenzar a escribir pruebas sin mucha configuración adicional.
  
  * ***Rapidez:*** Es veloz y puede ejecutar pruebas de forma paralela, lo que lo hace eficiente en entornos de desarrollo grandes.
  
  * ***Mocks:*** Facilita la creación y el uso de funciones mock, que permiten simular comportamientos específicos durante las pruebas.
  
  * ***Snapshots:*** Captura y almacena los resultados de pruebas. Guarda una instantánea de la salida del test y luego la verifica con futuros tests para detectar cambios inesperados.

  ***Nota:*** El testing es un área de la programación que se enfoca en evaluar el comportamiento del código de forma aislada y controlada, a partir de metodologías como el TDD (Test Driven Development).  
  El TDD consiste en el desarrollo de código a partir de tests, y no al revés. Es decir, primero diseño el testing de la aplicación y luego desarrollo el código.

> ## ***Integración de Jest***

Con Jest vamos a generar tests unitarios. Es decir, utilizando el conjunto de métodos que nos ofrece Jest, verificaremos que se cumplan las condiciones específicas del código con la aserción expect y comparando los resultados con matchers

* ### **WatchAll**
  
  La opcion watchAll nos va a permitir dejar la ejecución del testing corriendo de forma constante y que esté atento a los cambios. De esta manera, no tendremos la necesidad de ejecutar el comando npm test cada vez que realicemos modificaciones en el archivo de tests.  

  Esta opción debe ser integrada dentro del script de test del archivo package.json. Donde esta el script "test" deberemos igualarlo de la siguiente manera...

  ```json
  "scripts": {
    "test": "jest --watchAll"
  };
  ```
  
  ***Nota:*** Entendemos como pruebas unitarias aquellas que evalúan pequeñas porciones de código de forma individual.

* ### **¡A testear!**

  La estructura es sencilla, crearemos una función donde vamos a comparar un resultado con los valores esperados descritos dentro de la aserción expect utilizando matchers.

  * #### **Lo primero será iniciar nuestro test unitario con el método it el cual tomará dos argumentos:** 

    1. Un string con una descripción del resultado o lo que esperamos de esa prueba en particular.

    2. Una función de callback donde se indica el test a realizar.

  ```javascript
  describe('Ejemplo de pruebas', () => {
    const arreglo = [1, 2, 3, 4, 5];

    it('debería verificar que 2 + 2 sea 4', () => {
      expect(2 + 2).toBe(4); // toBe indica igualdad total "===", es decir, apuntan al mismo punto en memoria tanto el expect como el matcher
    });

    it('debería verificar que dos objetos sean iguales', () => {
      const objeto1 = { nombre: 'Juan', edad: 30 };
      const objeto2 = { nombre: 'Juan', edad: 30 };
      expect(objeto1).toEqual(objeto2); // toEqual indica igualdad parcial "==", es decir, el valor de expect y matcher es el mismo
    });

    it('debería verificar que arreglo contenga a 3', () => {
      expect(arreglo).toContain(3); // toContain indica que el expect debe poseer dentro de si mismo el valor del matcher
    });

    // Mas ejemplos: 
  
    expect(value).toBeTruthy() // Comprueba si value es verdadero.

    expect(value).toBeFalsy() // Comprueba si value es falso.

    expect(value).toBeNull() // Comprueba si value es nulo.

    expect(value).toBeUndefined() // Comprueba si value es indefinido.

    expect(value).toBeDefined() // Comprueba si value está definido.
  });
  ```

> ## ***Mock Functions***

* ### **¿Qué es?**
  
  Mock significa "imitación". Es una manera de simular ciertos comportamientos en nuestro código durante los tests.  

  Los mocks son útiles cuando estamos probando código y queremos asegurarnos de que ciertas partes funcionen correctamente sin ejecutar todo código completo.  

  Cuando queremos controlar el comportamiento de las funciones dependientes durante las pruebas unitarias hacemos uso de los mocks. Debemos considerar también no utilizar mocks innecesariamente.

  Es importante asegurarse que los mocks reflejen el correcto funcionamiento de lo que se testea. Debemos usar mocks cuando realmente sea necesario, preferiblemente probando el código en su contexto real siempre que sea posible.

  ```javascript
  // operaciones.js

  function sumar(a, b) {
    return a + b;
  };

  module.exports = sumar;
  ```
  
  ```javascript
  // calcularTotal.js

  const sumar = require('./operaciones');

  function calcularTotal(a, b, c) {
    const subtotal = sumar(a, b);
    return subtotal + c;
  };

  module.exports = calcularTotal;
  ```

  ```javascript
  // calcularTotal.test.js

  const calcularTotal = require('./calcularTotal');
  const sumar = require('./operaciones');

  jest.mock('./operaciones', () => ({
    __esModule: true,
    default: jest.fn(),
  }));

  describe('calcularTotal', () => {
    it('debería devolver el total correctamente', () => {
      sumar.mockReturnValueOnce(5); // Mockear la función sumar para devolver 5

      const total = calcularTotal(2, 3, 4);

      expect(total).toBe(9); // 5 (retorno de sumar) + 4 (c) = 9
      expect(sumar).toHaveBeenCalledWith(2, 3); // Verificar que sumar fue llamada con los argumentos correctos
    });
  });
  ```
***