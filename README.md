># SI-Bitacora3-AccesoRemoto

En esta actividad dejaremos de usar las virtual box, ya nos han dado muchos problemas asi que probaremos una nuevo metodo, 
Vamos a usar Docker Compose para levantar una infraestructura identica al que usamos en las virtuals box

## Fase 1: Despliegue de la Infraestructura

Para crear la infraestrucutra seguremos una seire de pasos y preparar todo el entorno

1. Primero crearemos una carpeta en tu equipo llamada SI_Bitacora4_NombreApellido donde sera con la que trabajemos
2. Dentro de esta carpeta guardaremos el archivo Docker con el siguiente nombre docker-compose.yml, y dentro del archivo tendra este **codigo**
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
3. Abriremos el docker en nuestro dispositivo y luego abriremos una terminal en visual code y usaremos el comando `docker-compose up -d` para ejecutarlo
   <img width="1333" height="261" alt="image" src="https://github.com/user-attachments/assets/c42e295c-359c-4549-b8ab-12c3fc16d1a7" />
5. Una vez el proceso anterior termine nos tocara verificar que los contenedores están funcionando correctamente y para ello usaremos `docker ps`
<img width="1353" height="194" alt="image" src="https://github.com/user-attachments/assets/4263d8ee-34bf-4492-88bd-40ce6e4a01d2" />

# Fase 2: La Llave Maestra
En vez de usar contraseña usaremos una criptografía de clave pública.

Paso A  Conéctataremos al contenedor usando ssh `alumno@localhost -p 2222`, Luego nos pedira La contraseña la cual es `sistemas_informaticos.`

Paso B En la terminal haremos un par de llave usando el comando: `ssh-keygen -t ed25519 -C "kiliandavidcorrales.25@campuscamara.es"` y tras eso nos pedira en que archivo queremos guardarla y generar una contraseña
Paso C Por ultimo ya habiendo establecido la contraseña, Copiaremos la llave pública al servidor.Usaremos el comando `ssh-copy-id -p 2222 alumno@localhost` 
Aquí tienes la información organizada en una tabla de dos filas, tal como me pediste para tu bitácora:

<img width="523" height="72" alt="image" src="https://github.com/user-attachments/assets/d8fec8cc-cbe7-4dbb-bc70-5e23f9a50631" />
```yaml
+--[ED25519 256]--+
|. ooo . ..       |
|.o . o .. .      |
|o . .    o .     |
| +        o .    |
|  + .   S.   .   |
|Eo . o = + oo    |
|. =   o B.O++    |
|oo .   oo*+Bo    |
|+o     .+=*+     |
+----[SHA256]-----+
0142b6fd94a3:~$ ^C
0142b6fd94a3:~$ 
```

# Fase 3: El Escritorio en el Navegador
Para terminar esta actividad dejaremos de usar solo la terminal y usaremos mejor algo mas inteactivo, 
y usaremos un entorno como una virtual vox, solo que esta vez sera en el navegador
1. Para ellos abriremos el escritorio remoto y abriremos el localhost con el enlace: `http://localhost:3389/` sin embargo, este parece estar fuera de servicio actualmente asi que optaremos por otra opcion
<img width="1915" height="981" alt="image" src="https://github.com/user-attachments/assets/5eea0360-6ff1-44e5-8648-437252747ce7" />
2. Abriremos el `http://localhost:3000` lo que nos abrirar un escriturio de ubuntu, eso signfica que funcionara
<img width="1911" height="976" alt="image" src="https://github.com/user-attachments/assets/d3fbbf14-65d2-43ee-9380-aac131a2777a" />
3. Por ultimo para comprobar que todo funciona en perfecto estado haremos una preuba y crearemos un archivo llamado **"PRUEABA_EXITOSA"**
<img width="475" height="429" alt="image" src="https://github.com/user-attachments/assets/d4941543-00fc-4261-a93e-b6a40e4c7e59" /><img width="1333" height="261" alt="image" src="https://github.com/user-attachments/assets/26d3cdab-6f36-40a3-8792-4c994c87d7ba" /

# Fase 4: Documentacion de errores durante la actividad


b. Me dio un error con el escritorio remoto, y por eso tuve que usar otra opcion abriento el `localhost:3000` en vez del `localhost:3389`
<img width="584" height="413" alt="image" src="https://github.com/user-attachments/assets/24be175e-566e-444a-9a31-ba3396b79fc3" />

