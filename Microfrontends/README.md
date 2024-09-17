# Microfrontends

## ¿Qué son?

Son una arquitectura para el desarrollo de aplicaciones frontend que sigue principios similares a los microservicios en el backend. En lugar de construir una aplicación monolítica de frontend, la idea es dividir la interfaz de usuario en partes más pequeñas y manejables, que pueden ser desarrolladas, desplegadas y mantenidas de forma independiente por equipos diferentes.

## Características principales

* Independencia tecnológica: Cada microfrontend puede ser desarrollado con diferentes tecnologías, frameworks, o versiones de una misma tecnología, según lo que mejor se adapte al equipo o a la funcionalidad específica.

* Despliegue independiente: Al igual que los microservicios, los microfrontends permiten desplegar actualizaciones de una parte específica de la aplicación sin necesidad de desplegar toda la aplicación completa.

* Responsabilidad clara: Cada equipo se responsabiliza de un microfrontend, lo que facilita la división de trabajo y reduce la complejidad en la gestión del proyecto.

* Composición en tiempo de ejecución: La aplicación se compone de varias partes que se ensamblan en el navegador, generalmente mediante una capa de orquestación que puede estar en el servidor o incluso en el cliente.

## Ventajas

* Escalabilidad de equipos: Facilita que equipos más grandes trabajen en una aplicación sin interferir en el trabajo de otros.

* Evolución independiente: Los microfrontends pueden evolucionar independientemente, lo que permite iterar rápidamente en funcionalidades específicas.

* Reducción de riesgos: Los errores en una parte de la aplicación no afectan a las demás, minimizando el impacto de fallos.

## Desventajas

* Complejidad en la integración: La composición de diferentes microfrontends puede ser compleja, especialmente si se manejan distintas tecnologías o estilos.

* Duplicación de dependencias: Es posible que haya duplicación de librerías o código, lo que puede aumentar el tamaño final de la aplicación.

* Coherencia visual y de experiencia de usuario: Mantener una apariencia y experiencia de usuario coherentes entre los diferentes microfrontends puede ser un desafío.