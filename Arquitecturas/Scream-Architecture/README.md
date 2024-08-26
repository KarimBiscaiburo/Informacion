# Scream Architecture

Esta arquitectura busca definir una manera de estructurar nuestro proyecto de manera tal que cada cosa sea fácil de identificar con solo verlo.

Imagina que estás mirando los planos de un edificio. Este documento, elaborado por un arquitecto, te indica los planos del edificio. ¿Qué te indican estos planos?

Si los planos que estás viendo son para una residencia familiar, entonces probablemente verás una entrada principal, un vestíbulo que conduce a una sala de estar y quizás a un comedor. Probablemente habrá una cocina a poca distancia, cerca del comedor. Quizás un área de comedor al lado de la cocina y probablemente una sala familiar cerca de eso. Cuando mires esos planos, no habrá dudas de que estás viendo una casa. La arquitectura "gritará": casa.

O si estuvieras mirando la arquitectura de una biblioteca, probablemente verías una gran entrada, un área para los empleados que registran la entrada y la salida, áreas de lectura, pequeñas salas de conferencias y galería tras galería capaces de albergar estanterías para todos los libros de la biblioteca. Esa arquitectura "gritará": Biblioteca.

Entonces, ¿qué es la Scream Architecture de una aplicación? Cuando observa la estructura de directorios de nivel superior y los archivos de origen en el paquete de nivel más alto, ¿"gritan": Sistema de atención médica, o Sistema de contabilidad, o Sistema de gestión de inventario? ¿O "gritan": Rails, o Spring/Hibernate, o ASP?

## Cual es el tema de la Scream Architecture?

Las arquitecturas no son (o no deberían ser) sobre los frameworks. Las arquitecturas no deberían ser proporcionadas por frameworks. Estos son herramientas para usar, no arquitecturas a las que hay que adaptarse. Si su arquitectura se basa en un framework, entonces no puede basarse en sus casos de uso.


## Proposito

La razón por la que las buenas arquitecturas se centran en los casos de uso es para que los arquitectos puedan describir con seguridad las estructuras que respaldan esos casos de uso sin comprometerse con marcos de trabajo, herramientas y entornos. De nuevo, pensemos en los planos de una casa. La primera preocupación del arquitecto es asegurarse de que la casa sea utilizable, no de que esté hecha de ladrillos. De hecho, el arquitecto se esfuerza por garantizar que el propietario pueda decidir sobre los ladrillos, la piedra o el cedro más tarde, después de que los planos garanticen que se cumplen los casos de uso.

Una buena arquitectura de software permite aplazar y retrasar las decisiones sobre marcos de trabajo, bases de datos, servidores web, otras cuestiones y herramientas del entorno. Una buena arquitectura hace innecesario decidir sobre Rails, Spring, Hibernate, Tomcat o MySql hasta mucho más tarde en el proyecto. Una buena arquitectura también hace que sea fácil cambiar de opinión sobre esas decisiones. Una buena arquitectura enfatiza los casos de uso y los desvincula de las preocupaciones periféricas.

## Ejemplo

``` txt
src/
    products/
        ProductsContainer.js        // Contenedor para la lista de productos
        state/
            productsState.js        // Estado de la lista de productos
        components/
            ProductList.js          // Muestra la lista de productos
            ProductItem.js          // Muestra un producto individual
        services/
            productService.js       // Comunica con la API para obtener productos
        adapters/
            productAdapter.js       // Adapta los datos de productos para la vista
    cart/
        CartContainer.js            // Contenedor para el carrito de compras
        components/
            CartView.js             // Vista principal del carrito
            CartItem.js             // Componente para un ítem individual en el carrito
        services/
            cartService.js          // Maneja la lógica de agregar/eliminar ítem del carrito
        adapters/
            cartAdapter.js          // Adapta los datos del carrito para la vista
``` 

La idea es que a simple vista podamos determinar que parte del codigo hace que cosas. Podemos adaptar esto tanto como el proyecto lo amerite, pero siempre teniendo en cuenta que los datos de los archivos fluyen (conceptualmente) como una cascada, es decir que un archivo mas profundo puede tener datos de la base del servicio o lo que sea, pero ese servicio no puede acceder de ninguna manera a los datos que haya en ese archivo mas profundo.