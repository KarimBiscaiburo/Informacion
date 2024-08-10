# Glosario de definiciones de siglas comunmente utilizadas

- Puede que algunas definiciones mas extensas o detalladas esten en otras carpetas o documentación

## CDN:

CDN (Content Delivery Network) es una red de servidores distribuidos geográficamente que trabajan juntos para entregar contenido a los usuarios de manera más rápida y eficiente. Los CDNs almacenan copias en caché del contenido de un sitio web (como imágenes, videos, archivos CSS y JavaScript) en diferentes ubicaciones alrededor del mundo, conocidas como "PoPs" (Points of Presence).

### Ventajas

* Reducción del tiempo de carga: Al servir el contenido desde el servidor más cercano al usuario, se reducen los tiempos de carga.

* Mejora en la disponibilidad: Si un servidor falla, otro servidor en la red puede tomar su lugar, lo que mejora la fiabilidad.

* Descarga del servidor de origen: Al manejar la mayoría de las solicitudes, el CDN reduce la carga en el servidor principal del sitio.

* Seguridad: Muchos CDNs ofrecen protección DDoS y otras medidas de seguridad.

### Ejemplos

* Cloudflare
* Akamai
* Amazon CloudFront
* Fastly


## SPA:

Single Page Applications (SPA) son aplicaciones web que cargan una sola página HTML y actualizan dinámicamente el contenido conforme el usuario interactúa con la aplicación, sin necesidad de recargar la página completa.

### Ejemplos

* Gmail: Casi toda la interacción con el correo electrónico ocurre dentro de una sola página web.

* Google Maps: Puedes desplazarte, hacer zoom y buscar ubicaciones sin que la página se recargue.

* Facebook: Cuando navegas entre diferentes secciones, como el feed de noticias, mensajes y notificaciones, la página no se recarga por completo.

* Trello: Es una aplicación de gestión de proyectos donde las interacciones, como mover tarjetas y listas, no requieren recargas de página.

### Caracteristicas

* Interactividad: La mayoría de las interacciones se manejan en el lado del cliente con JavaScript.

* Navegación sin recargas: Se utiliza el historial del navegador para manejar la navegación dentro de la página sin recargar.

* Desafíos de SEO: Dado que la mayoría del contenido se carga dinámicamente, puede ser más difícil para los motores de búsqueda indexar el sitio.


## CI/CD

CI/CD son siglas que representan Continuous Integration (CI) y Continuous Deployment/Delivery (CD), dos prácticas que buscan automatizar y mejorar el ciclo de vida del desarrollo de software.

> [!NOTE]
> Hay una carpeta especifica donde trato mas en detalle este tema.