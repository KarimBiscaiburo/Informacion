# Que son CI y CD

Son prácticas que buscan automatizar y mejorar el ciclo de vida del desarollo de software

- CI (Continuous Integration) y CD (Continuous Deployment/Delivery)

## CI

CI es la práctica de integrar cambios de código de múltiples desarrolladores en un proyecto de forma frecuente, al menos una vez al día. Cada integración se verifica mediante una construcción automatizada y pruebas (testing), lo que permite detectar errores lo antes posible.

### Propósitos

* Detectar errores temprano: Al integrar código con frecuencia y probarlo de inmediato, se identifican problemas de compatibilidad o errores en etapas tempranas.

* Automatizar el build: Asegura que el proceso de construcción del software sea reproducible y no dependa de la máquina local de un desarrollador.

* Mejorar la colaboración: Al integrar y probar cambios constantemente, se evita la "integración en bloque" al final del ciclo de desarrollo, lo que reduce conflictos.


## CD (Continuous Delivery)

CD extiende la idea de CI al automatizar la preparación del código para su despliegue a cualquier entorno (staging, QA, producción). Con Continuous Delivery, el código que pasa por el pipeline de CI está listo para ser desplegado en producción en cualquier momento.

### Propositos

* Desplegar rápidamente: Facilita que los equipos puedan lanzar nuevas versiones del software de forma rápida y con menor riesgo.

* Automatización de pruebas: Aparte de las pruebas unitarias, se suelen incluir pruebas de integración, pruebas de aceptación, y pruebas de usuario automatizadas en el pipeline.

* Versiones estables: Asegura que cada cambio es probado y validado, lo que resulta en versiones más estables y con menos errores.


## CD (Continuous Deployment)

Una extensión adicional es Continuous Deployment, que va un paso más allá y automatiza el despliegue del código directamente en producción cada vez que pasa todas las etapas de pruebas sin intervención manual.

### Propositos

* Automatización total: Cada cambio que pasa las pruebas automatizadas se despliega automáticamente en producción, reduciendo el tiempo entre escribir el código y tenerlo en manos de los usuarios finales.

* Menor tiempo de comercialización: Permite que los productos lleguen al mercado rápidamente, lo que es crucial en entornos competitivos.


# Herramientas de CI/CD

- Hay varias herramientas disponibles que ayudan a implementar CI/CD. Algunas de las más populares incluyen:

## Jenkins

* Descripción: Una de las herramientas de CI/CD más populares y ampliamente utilizadas. Es altamente configurable y tiene una gran comunidad de plugins para adaptarse a cualquier flujo de trabajo.

* Características: Integración con casi cualquier herramienta de desarrollo, pipelines personalizables, soporte para contenedores y microservicios.

* Ideal para: Equipos con necesidades de personalización complejas.

## GitHub CI/CD

* Descripción: Una solución CI/CD integrada directamente en GitHub. Permite a los desarrolladores crear y ejecutar pipelines automatizados directamente en su repositorio.

* Características: Workflows configurables, integración con el ecosistema de GitHub, marketplace de acciones predefinidas.

* Ideal para: Proyectos alojados en GitHub que buscan una integración fácil y directa.

## GitLab CI/CD

* Descripción: Parte de GitLab, una plataforma DevOps completa que ofrece CI/CD junto con control de versiones, seguimiento de issues, y más.

* Características: Pipelines configurables, integración con Docker, runner autohospedado.

* Ideal para: Equipos que desean una solución integrada de control de versiones y CI/CD.

## CircleCI

* Descripción: Un servicio CI/CD que se enfoca en la simplicidad y la velocidad. Ofrece pipelines rápidos y configuraciones intuitivas.

* Características: Soporte para múltiples lenguajes, integración con contenedores y Kubernetes, tiempos de construcción rápidos.

* Ideal para: Startups y empresas que buscan tiempos de construcción rápidos y una fácil configuración.

## Travis CI

* Descripción: Una herramienta CI/CD que se integra perfectamente con GitHub, proporcionando pipelines automáticos para proyectos de código abierto y privado.

* Características: Configuración simple basada en archivos .travis.yml, soporte para múltiples lenguajes y entornos.

* Ideal para: Proyectos de código abierto y equipos pequeños que buscan una configuración sencilla.

## Bamboo

* Descripción: Una herramienta CI/CD desarrollada por Atlassian, que se integra bien con otras herramientas de Atlassian como Jira y Bitbucket.

* Características: Soporte para despliegue continuo, integración con Jira, gestión de permisos detallada.

* Ideal para: Equipos que ya utilizan el ecosistema de Atlassian.

## Azure DevOps

* Descripción: Una solución de Microsoft que ofrece una gama completa de herramientas para DevOps, incluyendo CI/CD.

* Características: Integración con el ecosistema de Microsoft, soporte para múltiples lenguajes y plataformas, pipelines YAML.

* Ideal para: Empresas que ya están en el ecosistema de Microsoft o que utilizan Azure.


# Beneficios de Implementar CI/CD

* Mayor productividad: Automatizar tareas repetitivas libera tiempo para los desarrolladores, permitiéndoles centrarse en el código.

* Menos errores en producción: Al probar y validar continuamente, se reducen los errores y fallos en el entorno de producción.

* Rápida entrega de valor: Los cambios se despliegan más rápidamente, permitiendo a los usuarios finales acceder a nuevas funcionalidades y correcciones antes.

# Consideraciones

* Inicio pequeño: Comienza con un pipeline básico y ve agregando complejidad conforme se estabilice.

* Automatización de pruebas: Invertir en pruebas automatizadas es clave para aprovechar al máximo CI/CD.

* Monitoreo continuo: Implementa herramientas de monitoreo para identificar problemas rápidamente después del despliegue.