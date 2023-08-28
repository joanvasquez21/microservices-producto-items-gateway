# microservices-gateway
Configurando Spring Cloud Gateway, impementando filtros pre y post, implementacion de filter factory, filtros gateway que vienen por defecto y Predicate Factory
Gateway es un servidor de enrutamiento dinamico, compuesto por filtros para  enrutar nuestros servicios pero tambien podemos construir nuestros propios filtros personalizados
# Caracteristicas principales
Puerta de enlace: en una arquitectura de microservicios es el punto de entrada a nuestros microservicios, a partir de una ruta base podemos acceder a distintas rutas
Balanceo de carga: distribuir la carga de solicitudes entre multiples instancias
Maneja filtros por defecto
Permite crear nuestros propios filtros
Manejo de Predicates
# Esquema
Cualquier cliente que se conecte a nuestro sisetma siempre pasa por gateway y mediante rutas que le damos a los microservicios accedemos a ellos y se va registando en el servidor de eureka
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/429b58de-f0ad-459e-a996-f294c443839f)
# Configuración 
Agregamos estas dependencias y configuramos application.yml

![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/40a3b988-cc8a-44d3-aac5-63803883e70c)

![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/51df16c2-c27a-4487-94fe-7527b373e41d)
Filters: es necesario porque el path esta compuesto por dos segmentos /api/productos/**
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/a07f22c5-6c29-4e69-985c-a3006bfe27da)
-StripPrefix=2

# Implementando filtros globales PRE Y POST

![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/1ad3efd5-49bf-4917-b048-4f8c665400c5)
