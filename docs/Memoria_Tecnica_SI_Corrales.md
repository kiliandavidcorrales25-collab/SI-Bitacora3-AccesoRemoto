

# El Marco Legal y la Estructura del "Relato"

## Sistemas Informáticos

## Kilian David Corrales Pacheco

## 15/05/2026

**Índice**

[**1.1. Contexto y Problemática Actual	3**](#1.1.-contexto-y-problemática-actual)

[**1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole	3**](#1.2.-solución-propuesta:-infraestructura-híbrida-docker-guacamole)

[**1.3. Justificación Técnica y Beneficios (TCO)	3**](#1.3.-justificación-técnica-y-beneficios-\(tco\))

### 1.1. Contexto y Problemática Actual {#1.1.-contexto-y-problemática-actual}

La empresa necesita una forma eficiente para acceder remotamente a diferentes máquinas y servicios internos. hasta ese momento, cada usuario tenía que conectarse de forma manual con herramientas y protocolos SSH, utilizando las direcciones ip

Este método tenía muchos problemas importantes, primero la gestión de conexiones estaba descentralizada, esto hacía que tuviera una difícil y mala administración y cada vez sucedieran más errores  además tener tantos servicios variados en interneten, con esa gestión provocaba muchos errores, y a raíz de estos problemas nacen más problemas, como el problema del mantenimiento, configurar toda esa infraestructura y servicios de forma manual y remota en distintos dispositivos hacía que hubiera errores por incoherencias e inconsistencias entre dispositivos 

### 1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole {#1.2.-solución-propuesta:-infraestructura-híbrida-docker-guacamole}

Tras analizar los requerimientos de accesibilidad y seguridad, se ha optado por implementar una solución basada en **Apache Guacamole** desplegada mediante **Docker Compose**. Esta arquitectura permite:

* **Centralización**. Un único punto de acceso vía web (puerto 8080/443) para todos los servicios internos.  
* **Aislamiento**. Gracias a los contenedores, cada servicio (PostgreSQL, Guacamole, SSH) opera en su propio entorno estanco, evitando conflictos de dependencias.  
* **Seguridad**. Se elimina la necesidad de clientes externos pesados, permitiendo una auditoría centralizada de las conexiones.

### 1.3. Justificación Técnica y Beneficios (TCO) {#1.3.-justificación-técnica-y-beneficios-(tco)}

**\[Instrucción: Convence al lector de que tu solución es rentable y profesional\]**

La elección  de apache Guacamole y Docker, estos servicios ofrecen múltiples ventajas técnicas y económicas para cualquier empresa.

Desde el punto de vista técnico, estos programas son una solución que mejora la seguridad y evita problemas con haber múltiples servicios con RDP O SSH a internet además de centralizar todo en un único punto web para evitar problemas de administración o gestión 



5.

X El archivo LICENSES.md con las licencias identificadas.

X La carpeta docs con tu memoria técnica inicializada.

X El índice de la memoria funcionando y el análisis de necesidades redactado.

X Has hecho un Commit con el mensaje: feat: Sprint 1 completado - UD07.

x Has entregado la actividad en Classroom, recuerda que seguirás trabajando en el repositorio, así que, ¿Qué más da si la entregas?


# 2. Estimación de Costes de Infraestructura

<img width="915" height="161" alt="image" src="https://github.com/user-attachments/assets/3ba9859f-cb72-425b-ae8f-6b7651991736" />

# 3. Estrategia de Despliegue y Comunicación

*  Para poder usar la apliacacion al servidor usaremos SFTP, Usaeremos esta opcion, porque nos permite transferir archivos con citas me diante conexiones de SSH. Esta opcion soluciona los problemas de seguridad que train otras opcioens como FTP tradcional, este trasmite mensajes y contraseñas en texto normal, y puede ser facilmente interceptado

*  El proceso consite en subir los archivos del proyecto desde nuestro ordenador al servidor de la nube, donde estará alojada nuestra aplicación. De esta forma podremos actualizarla y corregir los errores de manera mas rápida y segura

*  Para la comunicacion del equipo una de las herrramientas mas comunes hoy en dia, Discord, ya que permite hablar como si fuerau na  llamada de telefono, compartir archivos, y crear grupos para la organizacion del proyeco. Ademas que es muy utlil y comoda de usar

# 4. Justificación Científica

* La investigacion sobre el uso del Docker compose, La investigacion habla sobre el uso de los contenedores del docker en el entorno de desarrollo y aplicaciones. El articulo explica que los contendroes funcinan bien por su organizacion, son una gran mejora para la orgnaziacion de aplicaciones y proceso des desarrolo, ademas de facilitar mucho el despelgar servicios de cloud

*  Este articluo es utli para nuestro proyecyo ya que puede servir como apoyo, queremos usar la infrastrcutura de docker para asegurar la aplicacion y su mantenimiento, Por eso, gracias a los servicos de uso de docker, podrmeos despelgar la aplicacion mas rapido y no tener problemas de compatibilidad el cual es uno de los requisitos principales del cliente

# 5 ¿Cuándo he terminado?
*  Tu Memoria_Tecnica.md tiene los 3 nuevos apartados (Costes, Despliegue y Justificación).
x Has incluido la tabla de la Hoja de Cálculo (con fórmulas aplicadas, no números estáticos).
x Has justificado el uso de un protocolo seguro de transferencia de ficheros (CE 7.e) y herramientas de mensajería (CE 7.d).
*  Hay al menos 1 referencia bibliográfica académica en formato IEEE extraída de un buscador especializado (CE 7.f).
x Has hecho el Commit correspondiente en tu repositorio de documentación.

# Referencias
López, L. E. G., & Alarcón, C. A. G. (2020). Extensión de la arquitectura Docker para el despliegue automático de contenedores. INGENIARE, 29, 11–26. https://dialnet.unirioja.es/servlet/articulo?codigo=8051527
