# Ejemplo con n8n

1. Instalar pm2 (si no lo tienes)

Si aún no tienes pm2 instalado globalmente, instálalo con:
```
npm install -g pm2
```

2. Instalar n8n globalmente
```
npm install -g n8n
```

3. Guardar el proceso para que se inicie automáticamente
```
pm2 start n8n --name n8n
pm2 save
```

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

## Posibles errores

* Error: Cannot find module '/n8n':
Esto indica que pm2 está intentando ejecutar n8n, pero no encuentra el módulo. Esto puede deberse a que el path configurado en pm2 es incorrecto o a que n8n no está instalado correctamente.

Solución:

1. Ejecuta:
```
which n8n
```

Si n8n está instalado globalmente, te devolverá una ruta como:
```
/usr/local/bin/n8n
```

Si no devuelve nada, significa que n8n no está instalado correctamente. Instálalo con:
```
npm install -g n8n
```

Luego, vuelve a verificar con "which n8n".

2. Eliminar y volver a agregar n8n en pm2

Es posible que pm2 esté usando una ruta incorrecta. Para corregirlo:
```
pm2 delete n8n
pm2 start $(which n8n) --name n8n
pm2 save
pm2 logs n8n
```