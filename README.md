# Docker-y-Kubernetes
                                                           CURSO DE KUBERNETES
1.1 KUBERNETES PARA PRINCIPIANTES

Kubernetes es una herramienta que nos ayuda a realizar microservicios que nos permite realizar nuestra aplicación en varios entregables(o servicios) interconectados
por red que gracias a esto podemos entregar el proyecto, realizar actualizaciones de una manera más frecuente y cómoda que antes cuando se entregaba un único archivo, 
esto resulta muy util a la hora de sacar nuestras aplicaciones o proyectos a producción.

Pero estos microproyectos dispones de su base de datos propia e idependiente de las bases de datos del resto de servicios (aunque podrian llegar a tener una en común),
esto tambien resulta muy cómodo y útil puesto que el proyecto al estar dividido de esta manera un microservicio creado anteriormente puede ser empleado para el desarrollo de un proyecto diferente, pudiendo trazar así diferentes rutas del proyecto.

Kubernetes tambien es una herramienta que nos ayuda a solucionar un gran problema que ocurre algunas veces y todo gracias al almacenaje en contenedores algunos de estos problemas que soluciona son:

* El uso de "/" en nuestra aplicación y despues de sacarlo a producción en el sistema operativo de alguien no funciona porque usa la "\" en vez de la "/" dando lugar a problemas (estos problemas suelen derivas del sistema operativo).
* Que la versión utilizada de Java de la producción sea diferente a la del desarrollo por ejemplo que en desarrolo se emplee un Java 6 y en producción se emplee un 
java 8. 
