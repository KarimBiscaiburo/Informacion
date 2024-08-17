# Que son las Arquitecturas

Son ideas o sugerencias de como estructurar un proyecto. A diferencia con los patrones de diseños, las arquitecturas no nos son una guia paso a paso de como solucionar un problema, sino que mas bien nos indican de que manera podriamos solucionarlo y luego nosotros aplicamos a conveniencia.

Todos los tipos de arquitecturas buscan resolver un mismo problema llamado "Separation of Concerns", que es, separar las responsabilidades para que sean fáciles de mantener, extender y comprender, separar los casos de uso de lógica de negocio de los que son funcionales, por ejemplo, en una aplicación bancaria no existe ningún requisito técnico que nos diga que una persona menor de 18 años no pueda registrarse, porque a nivel de codigo no hay nada que limite eso, pero la lógica de negocio si lo hace, entonces ahí es cuando entra la parte funcional, que nos va a "decir" como vamos a aplicar los requisitos de negocio en la aplicación.

## ¿Cómo se aplican?

Para aplicar una arquitectura primero tenemos que entender que al ser ideas/sugerencias, no es estrictamente necesario seguir al pie de la letra estas mismas. Sabiendo esto podriamos decir que se pueden aplicar distintos tipos de arquitecturas dentro de un proyecto según nos sea necesario.

## ¿Cómo elegimos una arquitectura?

Existen un monton de tipos de arquitecturas pero fundamentalmente tenemos que tener en cuenta que es lo que necesitamos. Para esto es imprescindible entender que cada tipo de arquitectura cumple ciertas condiciones y se adecuan mejor a ciertos poblemas, las ventajas y desventajas, y cual es el proposito de cada una.

A su vez hay que contemplar los requisitos técnicos, funcionales y sus limitaciones:

* Requisitos técnicos: Son aquellos requisitos que se deben cumplir para que el sistema funcione correctamente. Estos podrían ser un lenguaje o tecnología que a su vez tienen que satisfacer los requisitos funcionales.

* Requisitos funcionales: Son aquellos que definen el funcionamiento de nuestro sistema. Estos se podrían responder con algunas preguntas, "¿Qué es lo que tiene que hacer nuestro sistema?", "¿Que son las cosas que tiene que cumplir nuestro sistema para que funcione correctamente?".

* Limitaciones: Son aquellas que van a ser una contra a la hora de satisfacer los requisitos (técnicos y funcionales). Como por ejemplo la gente que trabaja en el sistema (no tengan los conocimientos, experiencias diferentes, etc).
