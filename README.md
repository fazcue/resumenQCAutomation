| java                                          | API testing                 |
| --------------------------------------------- | --------------------------- |
| [Intro](#java)                                | [Conceptos](#conceptos)     |
| [POO](#programaci%C3%B3n-orientada-a-objetos) | [RestAssured](#restassured) |
| [Relaciones](#relaciones-entre-clases)        |                             |
| [Herencia](#herencia)                         |                             |
| [Colecciones](#colecciones)                   |                             |

# Java

-   lenguaje de alto nivel
-   lenguaje tipado estático (cada variable debe ser declarada y no se puede cambiar el tipo, salvo mediante una conversión)
-   creado por Sun Microsystems en 1955

## Intro

### Check conocimiento

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

1. El archivo de un programa en Java debe terminar con la extensión de archivo: **.java**
2. Cuando se compila un programa en Java, el archivo producido por el compilador termina con la extensión: **.class**
3. Java es un lenguaje de tipado: **Estatico**
4. Con qué se comienza la ejecución de un programa Java: **Con el método main()**
5. El llamado a una librería se hace haciendo uso de la sentencia: **Import**
6. El double se aplica para datos tipo: **Decimal**
7. Para mostrar mensajes por pantalla se puede usar: **System.out.println()**
8. Cuáles son sentencias de iteración: **El Bucle for, while y do/while**
9. Cuáles son las sentencias de salto: **Break y continue**
10. Qué diferencia hay entre un bucle while y un bucle for: **El bucle for se ejecuta un número determinado de veces y el while un número indeterminado de veces**
</details>

### Resumen

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

**Tipos de datos primitivos:**

-   byte, short, int, long (8, 16, 32, 64 bits), (valor por defecto: 0)
-   float, double (32, 64 bits), (valor por defecto: 0.0)
-   boolean (valor por defecto: false)
-   char (valor por defecto: '\u0000')
-   String (inmutable, java le da un soporte especial y hace parecer como si fuera primivita), (valor por defecto: null)

**Clases de utilidad:**

-   Math, Arrays

**Wrapper classes (envolventes):**

-   Integer
-   Float, Double
-   Boolean

**Las variables locales (las declaradas dentro de un método) NO tienen valor por defecto. Si no se le asigna un valor antes de utilizarlas, al momento de compilar dará un error**

**Operadores:**

-   unarios > aritméticos > bits > relacionales > booleanos > operador de asignación
-   si 2 operadores poseen mismo nivel de prioridad, se evalúa de izquierda a derecha

**Tipos de instrucciones:**

-   Instrucciones de inicio/fin
-   Instrucciones de asignación
-   Instrucciones de lectura
-   Instrucciones de escritura
-   Instrucciones de bifurcación

**Subprogramas**

-   procedimientos: funciones sin retorno (void)
-   funciones: cuando SI tienen retorno
-   Argumentos de tipo primitivos pasan como valor
-   Argumentos de tipo objeto y arreglos pasan como referencia
</details>

## Programación orientada a objetos

-   paradigma de programación, un modelo o estilo que se basa en el concepto de clases y objetos
-   se enfoca en los objetos, sus atributos y las interacciones entre ellos
-   permite que el código sea reutilizable, organizado y fácil de
    mantener (principio DRY)

### Check conocimiento

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

1. Cuando se coloca la palabra final precediendo la declaración de una variable la misma se transforma en una constante: **VERDADERO**
2. Una variable local no puede ser declarada en cualquier lugar del cuerpo de una clase o metodo: **FALSO**
3. El método constructor de una clase puede tener cualquier nombre: **FALSO**
4. Cuando un método no devuelve ningún valor se utiliza la palabra reservada void para indicar que no devuelve nada: **VERDADERO**
5. La programación orientada a objetos es un paradigma de programación: **VERDADERO**
6. Qué es un paradigma de programación: **Es una manera o estilo de programación**
7. Qué elementos crees que definen a un objeto: **Sus atributos y sus métodos**
8. Una clase es: **Un molde para crear múltiples objetos**
9. El modificador de acceso private, hace que los atributos puedan ser accedidos por: **La clase donde se encuentran**
10. Qué significa instanciar una clase: **Crear un objeto a partir de la clase**
11. Queremos crear una clase Java con atributos que puedan ser accedidos, ¿Qué opción elegirías como la mejor? **Atributos privados con getters y setters**
12. Se crean anteponiendo la palabra static a su declaración: **Atributos y métodos de clase estáticos**
13. No puede cambiar su valor durante la ejecución del programa: **Variables finales**
14. La programación procedural se denomina así porque se destacan los: **Procedimientos o tares que resuelven un problema**

 </details>

### Resumen

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

**Abstracción:**
mecanismo por el cual se proveen los límites conceptuales de los objetos y se expresan unicamente sus características esenciales

**Encapsulamiento:**
oculta lo que hace un objeto de lo que hacen otros y del mundo exterior, por lo que se denomina también ocultación de datos

**Modificadores de acceso:**

-   public: permite acceder desde cualquier clase
-   private: sólo permite acceso desde la misma clase
-   protected: acceso desde su mismo paquete y por las clases que extienda (independientemente del paquete)
-   default: igual a protected, pero sin acceso por herencia

| visibilidad           | public | private | protected     | default |
| --------------------- | ------ | ------- | ------------- | ------- |
| misma clase           | Si     | Si      | Si            | Si      |
| mismo paquete         | Si     | No      | Si            | Si      |
| subclase paquete      | Si     | No      | Si            | Si      |
| subclase otro paquete | Si     | No      | Si (herencia) | No      |
| clase otro paquete    | Si     | No      | No            | No      |

**Atributos y métodos estáticos:**

"static" indica que los atributos y métodos pertenecen a la propia clase y no a las instancias. De todas formas, las instancias tienen acceso a dichos atributos y métodos estaticos.

Si un atributo es "static", entonces éste ocupa un único lugar en memoria, independientemente de la cantidad de instancias de una clase.

**Clase servicio:**

Clase auxiliar que permite "separar" los métodos de la clase en si. Sigue los **patrones GRASP** (serie de buenas prácticas, _General Responsibility Assignment Software Patterns_)

Dentro de los patrones GRASP, se encuentra el PATRON EXPERTO, el cuál hace referencia al principio básico de asignación de responsabilidades.

-   una clase servicio por cada clase
-   diseño con mayor cohesión
-   información encapsulada (disminución del acoplamiento)

| Persona 🡺 | PersonaService | 🡸 Main           |
| --------- | -------------- | ---------------- |
| nombre    | crearPersona   | crearPersona()   |
| id        | mostrarPersona | mostrarPersona() |

</details>

## Relaciones entre clases

-   conexión semántica entre clases
-   una clase contiene una referencia a un objeto u objetos de otra clase en forma de atributo

### Check conocimiento

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

1. La relación más fuerte es la: **Composición**
2. La relación más débil es la: **Agregación**
3. La relación es entre: **Clases**
4. La relación se representa en una clase con un: **Atributo que es un objeto de otra clase**
5. Por qué usamos relaciones entre clases:

    - **Para usar la funcionalidad de una clase en otra clase**
    - **Para mejorar la comunicación entre clases**
    - **Para incrementar la reutilización de código**

6. En base al siguiente código:

    ```java
    Pagina pagina = new Pagina();
    Libro libro = new Libro(pagina);
    ```

    ¿Qué afirmación describe mejor la relación entre estas dos clases?: **Libro TIENE una página**

7. El modificador de acceso public en los UML se representa con un: **Más (+)**
8. El modificador de acceso private en los UML se representa con un: **Menos (-)**
9. En base a la siguiente imagen:

    | Auto | 🢂 | Motor |

    elegir la opción que describe la relación: **Auto TIENE motor**

10. En base a la siguiente imagen:

    | Alumno | ➪ | Libro |

    elegir la opción que describe la relación: **Alumno USA libro**
    </details>

### Resumen

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

**Tipos de relaciones:**

La relación más simple es la **asociación**: relación entre dos objetos.
Puede ser bidireccional (ambos objetos se "conocen" entre si), y unidireccional (sólo un objeto "conoce" al otro)

-   Bidireccional:

    | Padre | 🡘 | Hijo |

-   Unidireccional:

    | Curso | 🡺 | Alumno |

Dentro de esta asociación simple, existe la **composisión** y la **agregación**

-   **Agregación:** cuando los objetos son independientes entre si.

    | Programador | 🡺 usa una 🡺 | Computadora |

    _la computadora va a existir más alla de que exista o no el programador_

-   **Composición:** relación más fuerte, dónde un objeto depende de otro.

    | Cliente | 🡺 tiene una 🡺 | Cuenta bancaria |

    _si el cliente no existe más, no tiene sentido mantener la cuenta bancaria_

</details>

## Herencia

-   relación fuerte entre 2 clases
-   pilar fundamental de la POO
-   apoya el concepto de reutilización de código

### Check conocimiento

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

1.  Qué palabra se usa para generar la herencia entre clases: **extendes**
2.  Qué código de los siguientes tiene que ver con la herencia:

    ```java
    public class Componente extends Producto // <- Herencia
    ```

3.  La superclase es la clase: **Madre o Padre**
4.  Cual de estos componentes de la superclase no hereda la subclase: **Constructores**
5.  La superclase debe ser abstracta: **Depende de la situación**
6.  Podemos acceder a los atributos de una superclase desde una subclase gracias al modificador de acceso: **protected**
7.  De cuántas clases se puede derivar/heredar en Java: **Una clase**
8.  Una clase que termina la cadena de una herencia se la declarara como: **final**
9.  Qué palabra se usa para implementar una interfaz: **implements**
10. Qué código asociarías a una Interfaz en Java:

    ```java
    public class Componente implements Producto // <- Interfaz
    ```

</details>

### Resumen

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

**Herencia y atributos:**

La subclase recibe los atributos de la superclase. Se recomienda utilizar el modificador de acceso **protected** para así evitar el uso de getters y setters

**Herencia y constructores:**

Los constructores no se heredan, en cambio los métodos sí. Para hacer uso del constructor, se utiliza la keyword **super**

La keyword super, además, nos permite llamar atributos y métodos de la superclase

**Herencia y métodos:**

La herencia permite la **sobreescritura** de métodos, gracias a la anotación **@Override**. Se la utiliza para para agregar o modificar la funcionalidad del método heredado

**Polimorfismo:**

Palabra de origen griego, que significa "muchas formas". Concepto de la programación orientada a objetos que **permite que un objeto pueda tomar diferentes formas y comportarse de diferentes maneras**

Se puede lograr por:

-   **Herencia**: la clase hija puede **sobrescribir** los métodos de la clase padre para proporcionar una implementación específica.

    ```java
    public class Animal {
        public void hacerSonido() {
            System.out.println("El animal hace un sonido");
        }
    }

    public class Perro extends Animal {
        @Override
        public void hacerSonido() {
            System.out.println("El perro ladra");
        }
    }

    public class Gato extends Animal {
        @Override
        public void hacerSonido() {
            System.out.println("El gato maulla");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Animal animal1 = new Perro();
            Animal animal2 = new Gato();

            animal1.hacerSonido(); // Salida: El perro ladra
            animal2.hacerSonido(); // Salida: El gato maulla
        }
    }
    ```

    -   Cuando creas instancias de las clases Perro y Gato y las asignas a variables de tipo Animal, Java sabe que, **aunque se estén tratando como objetos de tipo Animal**, en realidad **son instancias de las subclases Perro y Gato**.
    -   Cuando se llama al método hacerSonido() en las variables de tipo Animal, Java **utiliza la implementación específica de cada subclase**. Esto se debe a que Java utiliza el enlace dinámico para determinar qué método debe ejecutarse en tiempo de ejecución, en lugar de utilizar el enlace estático en tiempo de compilación.

-   **Interfaces**: una clase puede implementar múltiples interfaces y proporcionar su propia implementación para cada método definido en la interfaz.

    ```java
    interface Animal {
        void hacerSonido();
    }

    class Perro implements Animal {
        @Override
        public void hacerSonido() {
            System.out.println("El perro ladra");
        }
    }

    class Gato implements Animal {
        @Override
        public void hacerSonido() {
            System.out.println("El gato maulla");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Animal animal1 = new Perro();
            Animal animal2 = new Gato();

            animal1.hacerSonido(); // Salida: El perro ladra
            animal2.hacerSonido(); // Salida: El gato maulla
        }
    }
    ```

    -   En este ejemplo, la interfaz Animal define un método hacerSonido(). **Las clases Perro y Gato implementan esta interfaz** y proporcionan **su propia implementación** para el método hacerSonido().

    -   Al crear instancias de las clases Perro y Gato y asignarlas a variables de tipo Animal, se puede acceder al método hacerSonido() a través de las variables de tipo Animal. Java sabe que **estas instancias son objetos de las clases Perro y Gato**, y utiliza la implementación específica de cada clase al llamar al método

El polimorfismo permite escribir un código más genérico y flexible. Esto facilita la reutilización del código y permite un diseño más modular y extensible.

**Tipos de herencia:**

-   Única: 🄰 🡰 🄱
-   Jerárquica: 🄲 🡲 🄰 🡰 🄱
-   Multinivel: 🄰 🡰 🄱 🡰 🄲
-   Múltiple (a través de interfaces): 🄲 🡰 🄰 🡲 🄱

**Modificadores de clases y métodos:**

-   Clases finales: **impedimos que se generen hijos** a partir de esta clase
-   Métodos finales: **evitamos que las clases hijas puedan sobrescribir** estos métodos
-   Clases abstractas: **impide la instanciación de objetos**. Se suele marcar como clase abstracta a una superclase. También **se debe marcar como abstracta** toda clase que contenga **al menos un método abstracto**
-   Métodos abstractos: **método declarado pero no implementado**. No tiene cuerpo. Son las subclases quienes son las encargadas de implementar su funcionalidad

**Interfaces:**

-   Similar a una clase abstracta, dónde **todos sus métodos deben ser abstractos**. Indica qué se debe hacer, pero no cómo.
-   Una clase puede implementar **cualquier cantidad de interfaces**.
-   Al no tener constructor, **no se puede instanciar** una interfaz.
-   Los métodos declarados en una interfaz son **implícitamente públicos**.
-   Las variables declaradas **NO son de instancia**. Son **implícitamente publicas y finales** (por ende, constantes) por lo que deben inicializarse.

    ```java
    public interface Animal {
        public void hacerRuido();
    }

    public class Perro implements Animal {
        @Override
        public void hacerRuido() {
            System.out.println("Guau!");
        }
    }
    ```

</details>

## Colecciones

-   grupo de objetos (elementos)
-   para crear colecciones de tipo primitivo, se debe usar las wrapper classes
-   crecen dinámicamente, a diferencia de los arreglos
-   se utiliza el Java Collections framework, del paquete java.util

### Check conocimiento

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

1. Cual es el paquete contenedor de las colecciones: **java.util**
2. Una colección en Java es: **Un grupo de objetos**
3. El Java Collection Framework es: **Un grupo de clases e interfaces**
4. El tamaño de las listas aumenta dinamicamente: **Verdadero**
5. En el framework de colecciones de Java un Set es: **Una colección que no puede contener elementos duplicados**
6. Para agregar elementos en una lista se usa la función: **.add()**
7. Qué método borra un elemento de una colección: **.remove()**
8. En Java un Iterator es: **Una interface que proporciona los métodos para recorrer los elementos de una colección y posibilita el borrado de elementos**
9. El método para devolver los elementos del iterator es: **.next()**
10. Los mapas son los unicos que constan de dos valores (llave y valor): **Verdadero**

</details>

### Resumen

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

**Java Collections Framework:**

Arquitectura compuesta de interfaces y clases, dónde se encuentran las colecciones tales como lists, sets y maps.

**Qué es un framework:**

Un framework es un marco de trabajo el cual contiene un conjunto estandarizado de conceptos, prácticas, criterios y herramientas para hacer frente a un tipo de problemática particular y resolver
nuevos problemas de índole similar

**Lists:**

-   ArrayList: tipo de lista más común. Es como **un arreglo pero dinámico**.
-   LinkedList: **lista de doble enlace**. Mejor rendimiendo al agregar y quitar elementos que un ArrayList, pero peor en set y get.

**Sets:**

-   **HashSet**: set dónde sus elementos **NO están ordenados**. Le asigna un valor único hash a cada elemento, de ésta manera evitar contener duplicados.

    **Qué es un hash:** función criptográfica hash es un **algoritmo matemático** que transforma cualquier bloque arbitrario de datos en una nueva serie de caracteres alfanuméricos (mezcla entre letras y números) con una **longitud fija**

-   TreeSet: mantiene todos sus elementos de manera **ordenada** (forma ascendente), pero los métodos de agregar, eliminar son más lentos que el HashSet ya que cada vez que le entra un elemento debe posicionarlo para que quede ordenado

-   LinkedHashSet:

</details>

# API testing

## Conceptos

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

**Qué es una API:**

Application Programing Interface. Es un **conjunto de reglas y protocolos** que permite a diferentes aplicaciones **comunicarse entre sí** (request y response).

| IN (request) | 🡲 Process 🡲 | OUT (response)   |
| ------------ | ----------- | ---------------- |
| Endpoint     |             | HTTP Status code |
| Headers      |             | Response body    |
| Type         |             |                  |
| Body         |             |                  |

**Cómo testear una API:**

Consiste en **realizar un HTTP request** y luego **verificar su respuesta**.

1. Se debe tener conocimiento del funcionamiento de la API
2. Definir los parámetros requeridos para realizar el request
3. Correr el test
4. Verificar las respuestas
5. Reportar comportamientos extraños / no deseados

Las respuestas pueden devolver los siguientes códigos:

-   **1**XX - **informational**
-   **2**XX - **success**
-   **3**XX - **redirection**
-   **4**XX - **client** error
-   **5**XX - **server** error

**Qué significa CRUD:**

Es una API que **permite realizar las operaciones básicas** en un sistema de gestion de datos.

| CRUD      | Método | Seguro | Idempotente | Body |
| --------- | ------ | ------ | ----------- | ---- |
| C: Create | POST   | ❌     | ❌          | ✅   |
| R: Read   | GET    | ✅     | ✅          | ❌   |
| U: Update | PUT    | ❌     | ✅          | ✅   |
| D: Delete | DELETE | ❌     | ✅          | ❌   |

**seguro**: _que no realiza modificaciones_ | **idempotente**: _que al ejecutarse muchas veces, debe retornar la misma respuesta_

</details>

## RestAssured

<details open>
<summary>ocultar / mostrar</summary>
&nbsp;

</details>
