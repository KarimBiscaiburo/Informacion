# TDD y BDD

Las prácticas de desarrollo TDD (Test-Driven Development) y BDD (Behavior-Driven Development) son metodologías que guían la forma en que los desarrolladores escriben código, con un enfoque en la calidad y la verificación temprana de que el software cumple con los requisitos esperados.

## TDD (Test-Driven Development)

### ¿Qué es?

Es una práctica de desarrollo en la que primero se escriben las pruebas para una función antes de escribir el código que la implementa.

### Proceso

* Escribe una prueba: Antes de escribir cualquier código, creas una prueba automatizada que define una pequeña parte de la funcionalidad que quieres implementar.

* Haz que falle: Ejecutas la prueba, y como no hay código que implemente la funcionalidad, la prueba falla (esto confirma que la prueba está bien escrita).

* Escribe el código mínimo: Escribes el código necesario para hacer que la prueba pase.

* Refactoriza: Mejoras el código, asegurándote de que sigue pasando todas las pruebas.

### Beneficios

* Fomenta un código más modular y fácil de mantener.

* Reduce la cantidad de errores en el código.

* Proporciona una red de seguridad para el refactoring.

## BDD (Behavior-Driven Development)

### ¿Qué es?

Es una extensión de TDD que se enfoca en el comportamiento del software desde la perspectiva del usuario final. Utiliza un lenguaje natural para definir las pruebas, lo que facilita la colaboración entre desarrolladores, testers y stakeholders no técnicos.

### Proceso:

* Define escenarios de comportamiento: Usas un lenguaje como Gherkin para describir los comportamientos esperados en forma de escenarios. Estos escenarios se escriben en un formato dado-cuando-entonces:

    * Dado un estado inicial.
    * Cuando se ejecuta una acción.
    * Entonces se espera un resultado.

* Implementa las pruebas: Estos escenarios se convierten en pruebas automatizadas que guían el desarrollo.

* Escribe el código: Al igual que en TDD, escribes el código para que los escenarios de comportamiento pasen.

### Beneficios:

* Mejora la comunicación entre todos los involucrados en el proyecto.

* Asegura que el software cumpla con los requisitos y expectativas del negocio.

* Permite escribir pruebas en un lenguaje que cualquier persona del equipo puede entender.