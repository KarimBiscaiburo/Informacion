# GUÍA DEFINITIVA PARA COMPRENDERLOS

## 1. CÓDIGOS INFORMATIVOS (1xx) ℹ️

Indican que la solicitud se está procesando.

1. 100 Continue: El servidor recibió los encabezados y el cliente puede enviar el cuerpo de la solicitud.
2. 101 Switching Protocols: El cliente solicitó cambiar de protocolo y el servidor acepta.
3. 102 Processing: El servidor está procesando la solicitud.
4. 103 Early Hints: Permite al cliente empezar a precargar recursos mientras se procesa la respuesta final.
5. 104 Upload Resumption Supported: Indica soporte para reanudar una subida (no es estándar en todos los navegadores).

## 2. CÓDIGOS DE ÉXITO (2xx) ✅

La solicitud fue exitosa.

1. 200 OK: Solicitud exitosa. Es la respuesta más común.
2. 201 Created: El recurso fue creado con éxito (ejemplo: un nuevo usuario).
3. 202 Accepted: La solicitud fue aceptada para procesamiento, pero aún no completada.
4. 203 Non-Authoritative Information: La respuesta fue modificada por un proxy o caché.
5. 204 No Content: La solicitud fue exitosa, pero no hay contenido en la respuesta.
6. 205 Reset Content: Solicita al cliente que reinicie su interfaz (por ejemplo, borrar un formulario).
7. 206 Partial Content: Se devuelve una parte del contenido (útil en descargas por rangos).
8. 207 Multi-Status: Devuelve múltiples respuestas para diferentes operaciones (usado en WebDAV).
9. 208 Already Reported: Elemento ya listado en una respuesta anterior (WebDAV).
10. 226 IM Used: El servidor ha aplicado una transformación (como compresión) antes de enviar la respuesta.

## 3. CÓDIGOS DE REDIRECCIÓN (3xx) 🔁

Indican que el cliente debe dirigirse a otra URL. El cliente debe realizar más acciones para completar la solicitud, como seguir otra URL.

1. 300 Multiple Choices: Hay varias opciones posibles para el recurso solicitado.
2. 301 Moved Permanently: La URL ha cambiado de forma definitiva.
3. 302 Found: Redirección temporal, el recurso está en otro lugar momentáneamente.
4. 303 See Other: El recurso se encuentra en otra ubicación accesible con GET.
5. 304 Not Modified: El recurso no ha cambiado desde la última solicitud (optimización de caché).
6. 305 Use Proxy: Se debe usar un proxy específico (obsoleto en la mayoría de navegadores).
7. 307 Temporary Redirect: Igual que 302 pero manteniendo el método HTTP original.
8. 308 Permanent Redirect: Igual que 301 pero manteniendo el método HTTP original.

## 4. CÓDIGOS DE ERROR DEL CLIENTE (4xx) ⚠️

Indican que la solicitud contiene errores o el cliente no tiene permisos.

1. 400 Bad Request: Error en la solicitud (datos incorrectos o malformados).
2. 401 Unauthorized: Se requiere autenticación para acceder al recurso.
3. 402 Payment Required: Reservado para futuros usos relacionados con pagos.
4. 403 Forbidden: Acceso denegado aunque el usuario esté autenticado.
5. 404 Not Found: El recurso solicitado no existe o ha sido eliminado.
6. 405 Method Not Allowed: El método HTTP usado no está permitido para ese recurso.
7. 406 Not Acceptable: El contenido no cumple con los requisitos del cliente.
8. 407 Proxy Authentication Required: Se requiere autenticación con el proxy.
9. 408 Request Timeout: El servidor esperó demasiado sin recibir datos.
10. 409 Conflict: Conflicto con el estado actual del recurso.
11. 410 Gone: El recurso fue eliminado permanentemente.
12. 411 Length Required: Se requiere especificar la longitud del contenido.
13. 412 Precondition Failed: Una condición previa falló (por ejemplo, encabezados "If-Match").
14. 413 Content Too Large: El contenido excede el tamaño permitido.
15. 414 URI Too Long: La URL es demasiado larga para ser procesada.
16. 415 Unsupported Media Type: El tipo de contenido no es soportado por el servidor.
17. 416 Range Not Satisfiable: El rango solicitado no puede ser entregado.
18. 417 Expectation Failed: El servidor no puede cumplir con el encabezado "Expect".
19. 421 Misdirected Request: La solicitud fue dirigida a un servidor incorrecto.
20. 422 Unprocessable Content: El servidor entiende la solicitud pero no puede procesarla por errores semánticos.
21. 423 Locked: El recurso está bloqueado.
22. 424 Failed Dependency: Una acción previa falló y esta depende de ella.
23. 425 Too Early: La solicitud fue enviada demasiado pronto (riesgo de repetición).
24. 426 Upgrade Required: El cliente debe cambiar de protocolo para acceder.
25. 428 Precondition Required: El servidor requiere condiciones previas (por seguridad o concurrencia).
26. 429 Too Many Requests: Se enviaron demasiadas solicitudes en poco tiempo.
27. 431 Request Header Fields Too Large: Encabezados demasiado grandes para ser procesados.
28. 451 Unavailable for Legal Reasons: Acceso denegado por razones legales (como censura).

## 5. CÓDIGOS DE ERROR DEL SERVIDOR (5xx) 🔥

Indican fallos en el servidor que impiden procesar la solicitud.

1. 500 Internal Server Error: Un error inesperado ocurrió en el servidor.
2. 501 Not Implemented: El servidor no reconoce o no puede realizar la operación.
3. 502 Bad Gateway: Un servidor intermedio recibió una respuesta inválida.
4. 503 Service Unavailable: El servidor está sobrecargado o en mantenimiento.
5. 504 Gateway Timeout: El servidor intermedio no respondió a tiempo.
6. 505 HTTP Version Not Supported: La versión del protocolo HTTP no es compatible.
7. 506 Variant Also Negotiates: Error de configuración en la negociación de contenido.
8. 507 Insufficient Storage: No hay suficiente espacio para completar la operación.
9. 508 Loop Detected: Se detectó un bucle infinito al procesar la solicitud (WebDAV).