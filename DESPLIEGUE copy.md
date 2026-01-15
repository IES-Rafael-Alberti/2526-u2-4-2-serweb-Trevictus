## a) Parametros de administracion mas importantes del servidor web
**Tarea**
**Localiza en el contenedor los fragmentos relevantes de /etc/nginx/nginx.conf donde aparezcan:**  

#### worker_processes
Dice cuantos procesos de trabajo lanza Nginx.
Un uso incorrecto sería poner `worker_processes 1` en un servidor de 16 nucleos.
`top` o `htop` para ver cuántos procesos nginx hay corriendo.

#### worker_connections
Controla el número máximo de conexiones simultaneas que puede manejar cada worker.


#### access_log
Ruta del archivo donde se registran todas las visitas que recibe la web.

#### error_log
Es la ruta donde se guardan los fallos criticos del servidor.

#### keepalive_timeout
El tiempo que el servidor mantiene abierta una conexión con un cliente esperando nuevas peticiones antes de cerrarla.

#### include
Permite cargar otros archivos de configuración dentro del principal.

#### gzip (aunque este comentado)  
Activa o desactiva la compresión de los archivos antes de enviarlos al navegador para ahorrar ancho de banda.


Para esta tarea utilizo un comando en powershell ejecutandolo dentro de la carpeta del proyecto.  
```powershell
docker compose exec web sh -c "grep -nE 'worker_processes|worker_connections|access_log|error_log|gzip|include|keepalive_timeout' /etc/nginx/nginx.conf"
```
![alt text](evidencias/fragmentos-relevantes.png)