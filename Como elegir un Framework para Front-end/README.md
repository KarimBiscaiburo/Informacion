# Como elegir un Framework para Front-End

Dentro del Front End existen diferentes formas de servir páginas en la web, cada una con sus ventajas y desventajas (SSR / CSR / SSG). Por lo cual deberíamos, en primera instancia, determinar el enfoque que queremos que tenga el proyecto, y luego podríamos elegir un Framwork que se adapte mejor a nuestras necesiades.

> [!TIP]
> Tengo un documento donde hablo mas a fondo las formas de servir páginas en la web.

> [!IMPORTANT]
> El equipo de trabajo requerido no es estrictamente como se detallan en cada tecnología, son ejemplos de lo que las empresas suelen requerir más. Obviamente va a depender del proyecto y otras cuestiones.

## ASTRO

### Descripción General

* Una de sus principales caracteristicas y en lo que mas se centra es en SSG, por lo que la idea de usar Javascript es minima. Ademas trata de beneficiarce mucho de que, cada vez mas, se puede hacer mucho con HTML basico.

* Tiene un gran potencial de cara al futuro.

* Posee lo que ellos denominan "Astro Island" las cuales permiten incorporar componentes dinámicos en una página estatica, lo que permite tener alguna interactividad con el usuario sin perder las ventajas de un html estático. A su vez, estos componente, pueden ser integrados aun si son de diferentes frameworks (React, Angular, Vue, etc).

* Por último tienen lo que llaman "Átomos", que es un store global para compartir información entre islas.

### Características Claves

* Seo - Fue pensado para esto.
* No Javascript.
* Astro Island.
* Static Site Generation focus.
* El mercado todavía no lo utiliza mucho.
* Contenido dinámico pero con limitaciones.

### Usos Ideales

* Proyectos que requieran o necesiten del SEO.
* Páginas estáticas.
* Páginas con un Javascript mínimo.

### Equipo de trabajo requerido

* Front End Developers - HTML / CSS / Javascript.
* Especialistas en SEO.
* Creadores de Contenido ( ??? )
* Personas capaces de integrar diferentes Frameworks


## NextJS

### Descripción General

* Esta muy enfocado al SSR, aunque se pueden realizar configuraciones para SSG y CSR, la principal idea es que sirva para SSR.
* Posee un ecosistema muy robusto para dar mucha flexibilidad
* Orientado al SEO

### Caracteristicas Claves

* Optimizado para el SEO - Tiene herramientas que nos permite mejorarlo
* Posee "Server Components" los cuales el HTML es renderizado en el servidor.
* Enfoque hibrido - Se pueden crear paginas SSR / CSR / SSG
* Permite crear una API dentro del mismo proyecto como un backend, ya que utiliza un servidor (el cual es el mismo que utiliza para SSR)
* Brindan un routing muy sencillo de entender y no necesitas hacer nada.

### Usos Ideales

* Aplicaciones públicas - SEO
* E-Commerce - pensado para sitios complejos y de alto tráfico
* Aplicaciones dinámicas
* Proyectos basados en React

### Equipo de trabajo requerido

* React Developers
* Back End Developers (Según el caso)
* Front End Developers con conocimientos de Back End
* Especialistas en SEO
* Ingenieros Devops
* Diseñadores UX/UI


## Nuxt

### Descripción General

* Es un Framework de Vue
* Tiene muchas capacidades para realizar diferentes ecosistemas (SSR / CSR / SSG)
* Modular - Tiene muchas ventajas de Angular y React

### Caracteristicas Claves

* Optimización para SEO
* Arquitectura modular
* Sirve tanto para contenido estático como dinámico
* Tiene un muy buen ecosistema
* Automaticamente va a separar el código para aumentar el performance

### Equipo de trabajo requerido

* Vue Developers
* Front End Developers con conocimientos de Back End
* Especialistas en SEO
* Ingenieros Devops
* Diseñadores UX/UI


## Angular 18 con SSR

### Descripción General

* Es un framework creado por Google
* Gran ecosistema
* Es muy estricto
* Si o si hay que usar TypeScript
* Utiliza clases
* Tiene capacidad de SSR

### Caracteristicas Claves

* SSR
* Hidratación parcial
* Basado en TypeScript
* Util para grandes aplicaciones
* Posee Api Routes con express
* Gran ecosistema

### Usos Ideales

* Para aplicaciones grandes o complejas
* Aplicaciones basadas en SEO
* Requerimientos bien definidos
* Proyectos que requieran mantenimiento, escalabilidad, etc

### Equipo de trabajo requerido

* Angular Developers
* Front End con conocimientos de Back End
* Especialistas en SEO
* Ingeniero Devops
* Diseñador UX/UI
* Project Manager que se encargue de los requerimientos y complejidad empresarial


## Svelte Kit

### Descripción General

* Es un meta-framework porque esta basado en Svelte
* Es una solución para aplicaciones que requieran tanto SSR como CSR
* Es fácil
* Buena experiencia de desarrollo

### Caracteristicas Claves

* Optimizado para SEO
* No necesita configuración
* Posee SSR - CSR - SSG
* Al igual que Next, se basa en los archivos para generar las rutas
* Es rápido y flexible

### Usos Ideales

* Aplicaciones basados en SEO
* Proyectos con contenido estático o dinámico
* Para proyectos con alto performance

### Equipo de trabajo requerido

* Svelte Developers
* Front End con conocimientos de Back End
* Especialistas en SEO
* Ingeniero Devops
* Diseñador UX/UI


## Qwik

### Descripción General

* Creo como una nueva manera de resolver la manera en que se hidratan los componentes cuando tenemos SSR. Ellos en vez de enviar al browser el HTML y luego el JS (como lo hace el SSR), envian todo junto pero en vez de mandar un JS, mandan un JSON el cual cada elemento interactivo tiene un id que esta enlazado con los metodos que se tienen que ejecutar al realizar una acción en el JSON

### Caracteristicas Claves

* Carga instantanea
* Apps reanudables - El usuario puede salir y volver a entrar a la aplicacion sin ejecutar código nuevamente (útil para seguir desde el punto en que lo dejo)
* Optimización para SEO
* Lazy Loading
* Escalabilidad

### Usos Ideales

* Aplicaciones de alto performance

### Equipo de trabajo requerido

* Front End con conocimientos de Back End
* Especialistas en SEO
* Ingeniero Devops
* Diseñador UX/UI