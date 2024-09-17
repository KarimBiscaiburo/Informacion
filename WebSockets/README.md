# WebSockets

## ¿Qué son?

Los WebSockets son un protocolo de comunicación que permite establecer una conexión bidireccional y persistente entre un cliente (como un navegador web) y un servidor. A diferencia de las conexiones HTTP tradicionales, que son unidireccionales y orientadas a solicitudes/respuestas, los WebSockets permiten que tanto el cliente como el servidor envíen mensajes a la otra parte en cualquier momento después de que se haya establecido la conexión inicial.

## Características 

* Conexión persistente: Una vez que se establece la conexión WebSocket, permanece abierta hasta que el cliente o el servidor decidan cerrarla. Esto elimina la necesidad de realizar múltiples solicitudes para mantener la comunicación.

* Baja latencia: Dado que la conexión está abierta, los WebSockets permiten el intercambio de datos en tiempo real con una latencia mínima, lo que es ideal para aplicaciones que requieren actualizaciones instantáneas.

* Bidireccionalidad: Tanto el cliente como el servidor pueden enviar datos de forma independiente, lo que facilita la comunicación en ambas direcciones sin la necesidad de que el cliente solicite constantemente información nueva.

* Eficiencia: Los WebSockets utilizan menos ancho de banda que HTTP porque evitan el envío constante de encabezados y otros metadatos con cada mensaje. Además, el protocolo es ligero, lo que lo hace más adecuado para aplicaciones que requieren comunicaciones en tiempo real.

## Casos mas comunes

* Aplicaciones de chat: Los WebSockets permiten que los mensajes se envíen y reciban en tiempo real, sin retrasos.

* Actualizaciones en tiempo real: Aplicaciones como las bolsas de valores, deportes en vivo, o cualquier sistema donde los datos cambian constantemente pueden beneficiarse de los WebSockets para mostrar actualizaciones en tiempo real.

* Juegos multijugador en línea: Los juegos que necesitan comunicación rápida entre jugadores y el servidor utilizan WebSockets para garantizar una experiencia de juego fluida.

* Notificaciones en tiempo real: Para alertar a los usuarios sobre nuevos eventos o cambios, los WebSockets son ideales porque pueden enviar notificaciones instantáneamente.

## Tipos de WebSockets

Existen varios tipos y variantes de WebSockets, pero generalmente, cuando hablamos de WebSockets, nos referimos al protocolo estándar definido por la IETF en la RFC 6455 (documento que define el protocolo).

### 1. WebSocket estándar (RFC 6455):

* Protocolo: El estándar de WebSocket que se utiliza ampliamente en aplicaciones web modernas. Este protocolo se basa en TCP y establece una conexión persistente y bidireccional entre el cliente y el servidor.

* Puerto: Por defecto, los WebSockets funcionan sobre el puerto 80 para conexiones no seguras (ws://) y sobre el puerto 443 para conexiones seguras (wss://).

### 2. Secure WebSocket (WSS):

* Descripción: Una versión segura del protocolo WebSocket que utiliza TLS (Transport Layer Security) para cifrar la comunicación entre el cliente y el servidor, protegiendo los datos contra ataques de intermediarios.

* Puerto: Opera en el puerto 443, igual que HTTPS.

### 3. SockJS:

* Descripción: Una biblioteca de JavaScript que proporciona una API similar a WebSocket pero con respaldo en otros protocolos de transporte en caso de que WebSocket no esté disponible. Esto garantiza una mayor compatibilidad con navegadores antiguos o entornos con restricciones.

* Protocolos de respaldo: Incluye XHR, long polling, y streaming.

### 4. Socket.IO:

* Descripción: Una biblioteca que abstrae los WebSockets y otros mecanismos de transporte para proporcionar una API robusta y fácil de usar para la comunicación en tiempo real. Socket.IO también maneja automáticamente la reconexión, la multiplexación de canales y la compatibilidad con navegadores antiguos.

* Protocolos de respaldo: Puede caer en HTTP long polling si WebSockets no están disponibles.

### 5. SignalR (para .NET):

* Descripción: Una biblioteca para aplicaciones ASP.NET que facilita la construcción de aplicaciones web en tiempo real. SignalR utiliza WebSockets cuando están disponibles, pero puede cambiar a otros transportes como Server-Sent Events (SSE) o long polling según la disponibilidad.

* Integración: Funciona perfectamente con aplicaciones desarrolladas en .NET.

### 6. Phoenix Channels:

* Descripción: Parte del framework Phoenix para aplicaciones web en Elixir, Phoenix Channels utiliza WebSockets para manejar la comunicación en tiempo real. Proporciona una API para gestionar canales de comunicación a través de WebSockets.

* Ventajas: Ofrece soporte integrado para reconexión y la gestión de múltiples canales a través de una sola conexión WebSocket.

### 7. AWS WebSocket API:

* Descripción: Un servicio de AWS que permite crear, administrar y escalar aplicaciones en tiempo real utilizando WebSockets a través de Amazon API Gateway.

* Casos de uso: Ideal para aplicaciones en la nube que necesitan manejar un gran número de conexiones WebSocket de manera escalable.

### 8. WebRTC (aunque no es WebSocket per se):

* Descripción: WebRTC es una tecnología que permite la comunicación en tiempo real entre navegadores. Aunque no es un reemplazo directo de WebSockets, se puede utilizar para casos de uso similares, especialmente cuando se necesitan capacidades adicionales como la transmisión de video o audio.

* Diferencias: WebRTC es más complejo y está diseñado para manejar datos de mayor intensidad y múltiples canales de datos simultáneamente.

### 9. HTTP/2 WebSockets:

* Descripción: Una extensión del protocolo HTTP/2 para admitir WebSockets. Este enfoque permite aprovechar las características avanzadas de HTTP/2, como la multiplexación, mientras se utiliza WebSockets para la comunicación en tiempo real.

* Estado: Todavía en desarrollo en algunos navegadores y servidores, pero ofrece un potencial interesante para el futuro.

### 10. Long Polling:

* Descripción: Aunque no es un WebSocket, long polling es una técnica que imita el comportamiento en tiempo real de los WebSockets utilizando HTTP estándar. En long polling, el cliente hace una solicitud al servidor, que mantiene la conexión abierta hasta que hay datos disponibles para enviar, simulando así una conexión persistente.

* Usos: Se utiliza en entornos donde WebSockets no son compatibles.
Cada una de estas variantes tiene sus propias ventajas y desventajas, y la elección depende del entorno de la aplicación, la infraestructura disponible, y los requisitos específicos de comunicación en tiempo real.