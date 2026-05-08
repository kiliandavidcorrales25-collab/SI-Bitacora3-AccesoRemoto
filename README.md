# SI-Bitacora3-AccesoRemoto

En esta actividad dejaremos de usar las virtual box, ya nos han dado muchos problemas asi que probaremos una nuevo metodo, 
Vamos a usar Docker Compose para levantar una infraestructura identica al que usamos en las virtuals box

## Fase 1: Despliegue de la Infraestructura

Para crear la infraestrucutra seguremos una seire de pasos y preparar todo el entorno

1. Primero crearemos una carpeta en tu equipo llamada SI_Bitacora4_NombreApellido donde sera con la que trabajemos
2. Dentro de esta carpeta guardaremos el archivo Docker con el siguiente nombre docker-compose.yml, y dentro del archivo tendra este codigo
   **codigo**
```yaml
version: '3.8'
services:
  servidor_ssh:
    image: linuxserver/openssh-server:latest
    container_name: lab_ssh_servidor
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/Madrid
      - USER_NAME=alumno
      - USER_PASSWORD=sistemas_informaticos
      - PASSWORD_ACCESS=true
    ports:
      - "2222:2222" # Mapeamos el puerto 2222 local al 2222 del contenedor
    restart: unless-stopped

  servidor_rdp:
    image: linuxserver/webtop:ubuntu-xfce
    container_name: lab_rdp_servidor
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/Madrid
    ports:
      - "3389:3389" # Puerto estándar de Escritorio Remoto (RDP)
      - "3000:3000" # Puerto para acceso vía navegador (HTTP/Guacamole)
    shm_size: "1gb" # Importante para evitar cuelgues en el entorno gráfico
    restart: unless-stopped
```
3. Abriremos el docker en nuestro dispositivo y luego abriremos una terminal en visaul code y usaremos `docker-compose up -d` para ejecutarlo  
4. Por ultimo Verificaremos que los contenedores están funcionando correctamente y para ello usaremos `docker ps`
5. 
