# Despliegue de una arquitectura altamente disponible y escalable en AWS. 
Despliegue de una arquitectura altamente disponible y escalable en AWS. 

## Planificación

### Requerimientos
* Requerimiento 1
*  Desarrollar la plataforma web que permita a los clientes explorar los diferentes libros.
*  Se debe configurar toda la plataforma en una región y en este caso se trata de la region de North Virginia
*  se configura una VPC (IP 172.16.0.0/16) en donde se montaran las diferentes instancias, subredes y servicios
*  Deben existir dos zonas de disponibilidad A (us-east-1a) y B (us-east-1b)con una subred pública y dos subredes privadas cada una.
*  Crear las siguientes subredes:
*  PublicSubnetA:172.16.1.0/24
*  PrivateSubnetA: 172.16.3.0/24
*  PrivateSubnetAA 172.16.5.0/24 ( Base RDS)

*  PublicSubnetB:172.16.2.0/24
*  PrivateSubnetB: 172.16.4.0/24
*  PrivateSubnetBB2.16.6.0/24 ( Base RDS)
*  Se configura dos zonas de disponibilidaduna base de datos 
* Requerimiento 3
