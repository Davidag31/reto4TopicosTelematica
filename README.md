# dalvarezg-st0263
# Info de la materia: ST0263 Topicos especiales en Telematica.

## Estudiante(s):
- **David Alvarez Grisales**
- **Julio Cesar Posada Torres** 

## Profesor:
- **Nombre:** Alvaro Enrique Ospina Sanjuan
- **Correo Electrónico:** aeospinas@eafit.edu.co

## Reto 4.

## 1. Breve descripción de la actividad.

Se ha desarrollado un sistema P2P donde cada nodo o peer contiene varios microservicios que soportan un sistema de compartición de archivos distribuido y descentralizado, Se ha utilizado el middleware gRPC para la comunicación entre los diferentes nodos o peers, para esto se creo un servidor el cual seria el principal donde cada cliente peer se conecta a este, alli se realizan los metodos API REST como el login, logout, index y search, el servidor prinicipal cuenta con una base de datos simulada la cual va en un .json, en esta se encuentra la informacion de cada peer, su usuario, su contraseña y los archivos que este contiene, luego se simulo la descarga de los archivos con la conexion gRPC entre los peers, esto mediante el server peer.

# 1.1. Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
Se cumplio todo lo requerido para el reto 4:
- Implementación del clúster de kubernetes en AWS.
- Implementación de un balanceador de carga con Nginx.
- Implementación de sistema de archivos NFS.
- Implementación de certificado SSL para la página web, además de redireccionar el tráfico http a https en el dominio (https://reto4.construmarket.tech/)
# 1.2. Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
Se cumplieron todos los requerimientos necesarios
# 2. información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas.
Arquitectura:
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/c9cbd79c-61bf-4ffd-84b8-07f1945580f3)

El usuario se conecta a la pagina web mediante https gracias al certificado ssl luego el balanceador en nginx actua y distribuye las peticiones del usuario entre las distintas instancias de wordpress, luego cada wordpress apunta a un server NFS y a la base de datos, esta se encuentra fuera del cluster y la realizamos en GPC.


# 3. Descripción del ambiente de desarrollo y técnico: lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones.
Se uso AWS y GPC, en AWS se uso EKS para el uso de kubernets. Mientras que en GPC se utilizo el servicio SQL para la base de datos en MYSQL. Ademas un servidor en NFS en una instancia EC2 de AWS para almacenar los archivos de la aplicación Wordpress.

# 4 Ambiente de ejecucion:
El proyecto se encuentra en https://reto4.construmarket.tech/  
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/de3ee76c-fd2c-4514-b01a-d25924e789a0)
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/7bb1afce-5e52-4729-9e2c-7fb6b206df89)
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/2be05236-3f35-4422-be97-788c01cf8bcd)
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/84ad4a4f-5fb3-4d52-b6bf-14e1d783f9e8)

# Resultados del proyecto
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/f33ab29f-183f-4466-9ddc-afc75b75a462)
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/a167c489-9ecd-4a90-95ac-69bd5ebd0192)
![image](https://github.com/Davidrk31/reto4TopicosTelematica/assets/89051979/d46254ef-cf62-442f-b344-ea65793306e4)



# Referencias:

* [Instalación Kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)

* https://foolcontrol.org/?p=3754

* [Instalación Helm](https://helm.sh/docs/intro/install/)


