# Despliegue de una arquitectura altamente disponible y escalable en AWS. 
Despliegue de una arquitectura altamente disponible y escalable en AWS. 

## Planificación

### Requerimientos
* 
*  Desarrollar la plataforma web que permita a los clientes explorar los diferentes libros.
*  Se debe configurar toda la plataforma en una región y en este caso se trata de la region de North Virginia
*  se configura una VPC (IP 172.16.0.0/16) en donde se montaran las diferentes instancias, subredes y servicios
*  Deben existir dos zonas de disponibilidad A (us-east-1a) y B (us-east-1b)con una subred pública y dos subredes privadas cada una.
*  Crear las siguientes subredes:
*  PublicSubnetA:172.16.1.0/24
*  PrivateSubnetA: 172.16.3.0/24 (donde se aloja el Servidor Web WS)
*  PrivateSubnetAA 172.16.5.0/24 (donde se aloja la Base de datos RDS)
*
*  PublicSubnetB:172.16.2.0/24
*  PrivateSubnetB: 172.16.4.0/24 (donde se aloja el Servidor Web WS)
*  PrivateSubnetBB2.16.6.0/24 (donde se aloja la Base de datos RDS)
*
* Crear un Internet Gateway para darle conexión a internet a nuestra VPC --> IG_WSC
*
* Crear en cada zona de disponiblidad el Nat Getway para conectar la subred publica con la subred privada
* La pagina WEB conecta la subred privadaA con subreg privada AA ( base de datos )
* Se debe configurar un Auto Scaling para tener una alta disponibilidad del servicio WEB entre las subredes privadas A y B
*
* Se debe configurar un Aplication Load Balancer para distribuir las cargas entre los diferentes zonas de disponibilidad y el cual que permite el ingreso de los usuarios a travez del Nat GetWay directamente a la pagina web
*
* Se deben configurar varios Segurity Groups para permitir accesos a las diferentes partes del sistema utilizando diferentes puertos de comunicación
* Segurity groups para Acceso de Usuarios a la Pagina Web sg-book-ws (Instancias de los WEB SERVER) Reglas: TCP 22 y TCP 5000
*
* Segurity groups para Acceso de Administradores a la Base de datos sg-db (Base de Datos RDS) Reglas:  TCP 22 y TCP 3306
*
*
* La instancia EC2 debe poder conectarse a la base de datos en la subred privada. Para facilitar esta conexión se implementarán parámetros de conexión de la base de datos en el AWS System Manager Parameter Store, garantizando acceso seguro y eficiente a los datos almacenados.

### Diagrama (Arquitectura)

En la siguiente imagen se muestra el diseño de la arquitectura a partir de los requerimientos. 
![arquitectura aws](TalentoTech-G2/Arquitectura.png)
