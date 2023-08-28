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

# Implementando Gateway Filter Factory
Tenemos que extender de AbstractGatewayFilterFactory y dentro de esta tenemos la clase statica configuracion
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/574c0f04-d304-4383-9ffb-7bfdf4f7834e)
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/75a11a51-160d-44f0-b5cf-306568e81e6e)
# Comprobamos  que cumplan las condiciones de los filtros
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/b421965b-2635-4a3b-8395-4450985e3f33)
# Postman 
1.- Header con key token y value 1234
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/4aece58b-654c-434a-82bb-3dd0a10d45d1)
2.- Parametros
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/9c837875-6d61-4b64-98f9-be7b9a3c4def)
3.- De tipo GET
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/56e95f12-81ed-49cd-a7d5-3a415d346519)
4.- Cookie
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/f7af8c65-3f4a-447b-9b30-3f7600517a2a)
Respuesta 200 Ok
![image](https://github.com/joanvasquez21/microservices-gateway/assets/70104624/3fbc5d20-77a9-4913-bf09-47303aaac49a)

