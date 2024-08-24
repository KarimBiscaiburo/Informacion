# Como elegir un Framework para Front-End

Dentro del Front End existen diferentes formas de servir páginas en la web, cada una con sus ventajas y desventajas (SSR / CSR / SSG). Por lo cual deberíamos, en primera instancia, determinar el enfoque que queremos que tenga el proyecto, y luego podríamos elegir un Framwork que se adapte mejor a nuestras necesiades.

> [!TIP]
> Tengo un documento donde hablo mas a fondo las formas de servir páginas en la web.

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