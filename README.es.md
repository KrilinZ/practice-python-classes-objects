<!-- hide -->
<div align="center">

# Práctica de Clases y Objetos en Python

[![Certificado por 4Geeks Academy](https://img.shields.io/badge/4Geeks%20Academy-Tutorial%20Certificado-2563eb?style=for-the-badge)](https://4geeks.com)
[![Autocorregido con LearnPack](https://img.shields.io/badge/LearnPack-Autocorregido-2563eb?style=for-the-badge)](https://github.com/learnpack/learnpack)
[![Abrir en GitHub Codespaces](https://img.shields.io/badge/Abrir%20en-Codespaces-fb5a1f?style=for-the-badge&logo=github)](https://codespaces.new/4GeeksAcademy/practice-python-classes-objects)

🇬🇧 [Read this page in English](https://github.com/4GeeksAcademy/practice-python-classes-objects/blob/HEAD/README.md)

</div>
<!-- endhide -->

Práctica de Clases y Objetos en Python es un tutorial de LearnPack con 12 pasos: una guía de bienvenida y 11 ejercicios autocorregidos que van desde definir tu primera clase hasta el polimorfismo. Cada ejercicio trae una plantilla `app.py` y un fichero de `pytest`, 39 pruebas en total. La corrección es incremental, así que avanzas paso a paso. Funciona en GitHub Codespaces o en tu propia máquina, en español e inglés.

<!-- hide -->
## 📋 Sobre este tutorial

- **Dificultad:** fácil
- **Duración estimada:** 12 horas
- **Pasos:** 12 carpetas dentro de `exercises/` (1 de introducción + 11 de código)
- **Pruebas automáticas:** 39 funciones de prueba de `pytest` repartidas en 11 ficheros `test.py`
- **Tecnologías:** Python, programación orientada a objetos, clases, objetos
- **Corrección:** incremental
- **Idiomas:** español e inglés (cada ejercicio tiene `README.es.md` y `README.md`)
- **Entorno:** contenedor con Python 3.10, `pytest` 6.2.5 y LearnPack 5.0.13
<!-- endhide -->

## 🎯 ¿Qué vas a aprender?

El tutorial recorre los pilares de la programación orientada a objetos en Python, un concepto por paso, sin frameworks y sin más dependencia externa que `pytest`:

- Declarar una clase e instanciar objetos a partir de ella
- Inicializar el estado con `__init__` y guardar atributos de instancia
- Añadir comportamiento con métodos de instancia que usan `self`
- Encapsular el estado tras la convención `_name` / `_age` con getters y setters
- Validar la entrada y lanzar `ValueError` para que el objeto nunca quede inconsistente
- Implementar los métodos especiales `__str__`, `__repr__` y `__eq__`
- Distinguir atributos de clase de atributos de instancia, y `@classmethod` de `@staticmethod`
- Modelar relaciones "tiene un" mediante composición
- Gestionar una colección de objetos dentro de una clase contenedora
- Reutilizar comportamiento con herencia y `super()`
- Aplicar polimorfismo a través de un contrato de método compartido

## 👀 ¿Qué vas a construir?

Aquí no hay un proyecto final único. Escribes 11 programas pequeños e independientes, cada uno resuelto en su propio `app.py` y comprobado por su propio fichero de pruebas:

1. **Crea tu primera clase** — declara `Person` e instancia `student`. Dos pruebas: que la clase existe y que `student` es instancia suya.
2. **Constructor y estado inicial** — añade `__init__(name, age)`, guarda `self.name` y `self.age`, y crea `student` con `"John"` y `21`.
3. **Métodos de instancia** — escribe `greet()`, que devuelve `"Hi, my name is John"`, y `have_birthday()`, que suma uno a la edad.
4. **Encapsulamiento básico** — guarda el estado en `_name` y `_age`, expón `get_name()` y `get_age()`, y escribe `set_age(new_age)` que devuelve `True` cuando actualiza y `False` cuando el valor es negativo.
5. **Validación de datos** — rechaza un `name` vacío o una `age` negativa lanzando `ValueError`, tanto en el constructor como en `set_age()`.
6. **Métodos especiales** — devuelve `"Person: John (21 years old)"` desde `__str__`, `"Person(name='John', age=21)"` desde `__repr__`, y compara dos personas por nombre y edad en `__eq__`.
7. **Atributos y métodos de clase** — mantén un contador `population` compartido, exponlo con un `@classmethod` y añade un `@staticmethod` `is_adult(age)`.
8. **Composición** — crea una clase `Address`, mete una instancia suya dentro de `Person` y devuelve `"Miami, USA"` desde `full_address()`.
9. **Colecciones de objetos** — escribe una clase `Classroom` que añade, busca, elimina y cuenta objetos `Person` guardados en una lista.
10. **Herencia y reutilización** — extiende `Person` en `Student` con un atributo `cohort` y sobrescribe `describe()` reutilizando el constructor del padre con `super()`.
11. **Polimorfismo y abstracción** — dale a `Animal` un `speak()` que lanza `NotImplementedError`, impleméntalo en `Dog` y `Cat`, y llama a ambos desde la misma función `make_it_speak(animal)`.

## 🎓 ¿Qué necesitas saber antes de empezar?

Conviene que ya te muevas con soltura en Python básico: variables, tipos de datos, condicionales, bucles, listas y funciones. El primer ejercicio da por hecho que sabes definir una función y llamarla, y varios ejercicios se apoyan en f-strings para construir el valor de retorno.

No hace falta que hayas tocado antes programación orientada a objetos, decoradores ni `pytest`. Todo lo relativo a clases se explica desde cero y las pruebas se ejecutan solas.

Si aún no llegas, calienta motores con [Aprende Python Interactivamente (principiante)](https://4geeks.com/es/interactive-exercise/python-beginner-exercises-es) y [Aprende las funciones de Python Interactivamente](https://4geeks.com/es/interactive-exercise/python-function-exercises-es).

## ✅ ¿Cómo funciona la corrección automática?

Cada ejercicio de código tiene un fichero `test.py` que importa tu módulo y ejecuta aserciones reales contra él. Nada se comprueba buscando patrones en tu código fuente, así que cualquier implementación que se comporte bien aprueba.

1. Escribe tu solución en `app.py`. El fichero llega casi vacío, con una única línea de comentario.

2. Pulsa **Run** en la interfaz de LearnPack para ejecutar tu fichero y ver su salida.

3. Pulsa **Test**. LearnPack lanza `pytest` solo sobre ese ejercicio y te informa de cada aserción por su nombre.

4. El fichero de pruebas importa directamente de tu módulo los objetos que necesita, con una línea del estilo `from app import Person, student`. Si falta cualquiera de esos nombres, la importación revienta y fallan todas las pruebas del fichero a la vez, no solo una.

5. Cuando el fichero entero esté en verde, pulsa **Next** para pasar al siguiente ejercicio.

Si quieres volver al punto de partida, cada ejercicio guarda una copia intacta de su `app.py` en `.learn/resets/`, y un `solution.hide.py` con el que comparar una vez hayas terminado.

## 💡 ¿Qué errores conviene evitar?

Estos son los tropiezos que te frenan aunque el código parezca correcto. La mayoría salen de lo que las aserciones comprueban de verdad; un par salen del criterio de éxito que trae el propio ejercicio:

- **Imprimir en lugar de devolver.** `greet()`, `describe()`, `full_address()` y `speak()` se comprueban con igualdades del tipo `assert student.greet() == "Hi, my name is John"`. Un `print()` devuelve `None` y falla.
- **Devolver valores "verdaderos" en vez de booleanos reales.** `set_age()` del ejercicio 4 e `is_adult()` del 7 se comprueban con `is True` e `is False`. Devolver `1`, `0`, una cadena no vacía o `None` falla la comprobación de identidad aunque pasaría un `if`.
- **Equivocarse en el texto exacto.** Las cadenas se comparan carácter a carácter: `"Person: John (21 years old)"` y `"Person(name='John', age=21)"`, con comillas simples alrededor del nombre dentro de `__repr__`. Un espacio de más y ya no cuadra.
- **Incrementar el contador en la instancia.** En el ejercicio 7, escribir `self.population += 1` crea un atributo de instancia nuevo y deja el de clase a cero. Usa `Person.population += 1` para que `get_population()` lo vea.
- **Hacer `Animal` abstracta con `abc`.** El ejercicio 11 comprueba que `Animal().speak()` lanza `NotImplementedError`, o sea que la clase base tiene que poder instanciarse. Declararla con `ABC` y `@abstractmethod` hace que `Animal()` lance `TypeError` y la prueba falla.
- **Olvidar los objetos globales.** Casi todos los ejercicios esperan una instancia a nivel de módulo con un nombre exacto: `student`, `student_clone`, `bootcamp`, `dog`, `cat`. Definir solo la clase nunca basta.
- **Ignorar la instancia que pide el ejercicio.** El ejercicio 10 marca `Student("John", 21, "42")`, con la cohorte como la cadena `"42"`, y la única aserción compara `student.describe()` con `"Name: John, Age: 21, Cohort: 42"`. Construye ese texto con las etiquetas y las comas exactas.
- **Declarar la lista de alumnos a nivel de clase.** El ejercicio 9 pide entre sus criterios de éxito que la colección viva en una lista interna inicializada en `__init__`, así que escribe ahí `self.students = []`. Una lista definida en el cuerpo de la clase la comparten todas las `Classroom` que crees, y `bootcamp` acaba con alumnos que añadiste en otro sitio.
- **Dejar un `input()` en el nivel superior.** El fichero de pruebas importa `app`, así que todo el código que esté fuera de una función o una clase se ejecuta durante el test y una llamada bloqueante lo deja colgado.

## ❓ Preguntas frecuentes

### ¿Cuál es la diferencia entre una clase y un objeto en Python?

La clase es el molde que describe cómo es un tipo de objeto y qué sabe hacer; el objeto, o instancia, es una cosa concreta fabricada con ese molde. En este tutorial `Person` es la clase y `student = Person("John", 21)` es un objeto. Una sola clase y tantos objetos como necesites, cada uno con su propio estado.

### ¿Necesito instalar algo para empezar?

No, si abres el repositorio en GitHub Codespaces. El contenedor viene con Python 3.10, Node 20, `pytest`, LearnPack y la extensión de LearnPack para VS Code ya configurados. También puedes instalarlo en local: son tres comandos.

### ¿Tengo que hacer los ejercicios en orden?

Sí, y compensa. La corrección está configurada como `incremental` y el contenido es acumulativo: el ejercicio 5 valida el constructor que escribiste en el 2, y el 10 hereda de la clase `Person` que llevas puliendo desde el 1. Saltar pasos significa releer después lo que te saltaste.

### ¿Cómo sé que mi respuesta es correcta?

Ejecutando las pruebas. Hay 39 funciones de prueba repartidas entre los 11 ejercicios de código, desde 2 en el primero hasta 5 en los de encapsulamiento y validación. Cada una comprueba un comportamiento real, así que aprobarlas significa que tu objeto se comporta como debe, no que se parezca a la solución.

### ¿Qué hago si rompo mi `app.py`?

Cada ejercicio de código guarda una copia limpia de su fichero de partida en `.learn/resets/<nombre-del-ejercicio>/app.py`. La copias encima de tu fichero y vuelves a la casilla de salida, sin necesidad de clonar otra vez el repositorio.

### ¿Este tutorial es gratis y de quién es el código que escribo?

Acceder no cuesta nada: el repositorio es público, así que puedes abrirlo en Codespaces o clonarlo sin pagar. No incluye fichero `LICENSE`, de modo que el contenido del tutorial no se publica bajo una licencia de código abierto y sus derechos siguen siendo de sus autores. Las soluciones que escribes en `app.py` son tuyas.

<!-- hide -->
## 📝 Tutoriales relacionados

Si quieres profundizar en la orientación a objetos o en Python en general:

- [Aprende Programación Orientada a Objetos con Python](https://4geeks.com/es/interactive-exercise/aprende-programacion-orientada-a-objetos-con-python)
- [Programación Orientada a Objetos en Javascript](https://4geeks.com/es/interactive-exercise/object-oriented-programing-in-javascript-es)
- [Aprende listas y bucles de Python Interactivamente](https://4geeks.com/es/interactive-exercise/python-loops-lists-exercises-es)
- [Domina Python Practicando](https://4geeks.com/es/interactive-exercise/master-python-exercises-es)
- [Capítulo de clases en la documentación oficial de Python](https://docs.python.org/3/tutorial/classes.html)

## 🚀 Cómo empezar

El camino más rápido es GitHub Codespaces, sin instalar nada en tu máquina:

1. Abre el repositorio en un codespace:

    [![Abrir en GitHub Codespaces](https://img.shields.io/badge/Abrir%20en-Codespaces-fb5a1f?style=for-the-badge&logo=github)](https://codespaces.new/4GeeksAcademy/practice-python-classes-objects)

2. Espera a que termine de construirse el contenedor. Él solo instala Python 3.10, `pytest`, LearnPack y el plugin `@learnpack/python`.

3. Arranca el tutorial desde la terminal integrada:

    ```bash
    learnpack start
    ```

4. Abre el puerto reenviado en la pestaña del navegador que te ofrece VS Code y empieza por `00-Welcome`.

## 💻 Instalación local

Si prefieres trabajar en tu propia máquina, necesitas Python 3 y Node.js instalados:

1. Clona el repositorio y entra en la carpeta:

    ```bash
    git clone https://github.com/4GeeksAcademy/practice-python-classes-objects.git
    cd practice-python-classes-objects
    ```

2. Instala las dependencias de Python que usan las pruebas:

    ```bash
    pip3 install pytest==6.2.5 pytest-testdox mock
    ```

3. Instala LearnPack y su plugin de Python:

    ```bash
    npm i @learnpack/learnpack@5.0.13 -g
    learnpack plugins:install @learnpack/python@1.0.6
    ```

4. Lanza el tutorial:

    ```bash
    learnpack start
    ```

## 📚 Cómo están organizados los ejercicios

Todo vive dentro de `exercises/`, una carpeta por paso y numeradas para que LearnPack sepa ordenarlas. Las 11 carpetas de código comparten los mismos cuatro ficheros:

- **`README.es.md` y `README.md`** — el enunciado en español e inglés, con el objetivo, el concepto clave, las instrucciones numeradas y el criterio de éxito.
- **`app.py`** — tu fichero de trabajo, que llega con un simple comentario de marcador.
- **`test.py`** — el fichero de `pytest` que corrige el ejercicio. Merece la pena leerlo: es el contrato exacto que tu código tiene que cumplir.
- **`solution.hide.py`** — una solución válida, que LearnPack te oculta mientras trabajas.

`00-Welcome` es la excepción: solo tiene los dos READMEs, porque explica la mecánica y no hay nada que resolver. Fuera de `exercises/`, las rutas interesantes son `learn.json` (configuración del tutorial) y `.learn/resets/` (copias intactas de cada `app.py`).

## 🤝 Colaboradores

Este tutorial lo construye y mantiene [4Geeks Academy](https://4geeks.com) y funciona sobre [LearnPack](https://github.com/learnpack/learnpack), el motor que hay detrás de sus tutoriales interactivos.

¿Has visto una errata, un enunciado confuso o una prueba que no se comporta como dice la documentación? Abre un issue o una pull request en el [repositorio](https://github.com/4GeeksAcademy/practice-python-classes-objects).
<!-- endhide -->
