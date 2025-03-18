# Ejemplo con n8n

1. Instalar pm2 (si no lo tienes)

Si aún no tienes pm2 instalado globalmente, instálalo con:
```
npm install -g pm2
```

2. Ejecutar n8n con pm2

Como npx n8n es un comando temporal, lo mejor es ejecutar n8n directamente con pm2:
```
pm2 start npx --name n8n -- run n8n
```
Aquí:

* npx es el binario que ejecuta n8n
* --name n8n asigna un nombre al proceso para que sea más fácil gestionarlo
* -- run n8n le indica a npx que ejecute n8n

3. Guardar el proceso para que se inicie automáticamente

Para asegurarte de que pm2 reinicie n8n después de un reinicio del servidor, ejecuta:
```
pm2 save
pm2 startup
```
El comando pm2 startup te mostrará un comando adicional que debes copiar y ejecutar para habilitar pm2 como servicio en tu VPS.

4. Verificar el estado del servicio

Para ver si n8n está corriendo correctamente:
```
pm2 list
```

Si necesitas ver los logs:
```
pm2 logs n8n
```

5. Detener o reiniciar n8n

Si necesitas detener o reiniciar el servicio:
```
pm2 stop n8n
pm2 restart n8n
pm2 delete n8n  # Para eliminar el proceso de pm2
```