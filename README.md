# Docker-y-Kubernetes
                                                           CARERA DE KUBERNETES
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

Estos contenedores se crean a partir de un fichero DOCKERFILE donde definiremos los siguiente:

* Que sistema operativo queremos usar, Windows,Linux,Mac,...
* Definir parámetros como variables de entorno.
* Que dependencias tenemos que instalar o son necesarios, por ejemplo si nuestra aplicación necesita Java 11 pues gracias al contenedro se instalara Java 11.
* Añadir nuestra aplicación diractamente al equipo.
* Que puesto utilizará nuestra aplicación y realizar un EXPOSE para poder tenerlo operativo.
* El comando que permite lanzar o arrancar nuestra aplicacción.

Conceptos básicos o inprescindibles que se deben saber o conocer de Kunernetes:

* POD: Es como si se tratase de una máquina virtual, solo que en vez de disponer de varios procesos dispone de uno o varios contenedores, pero todos los contenedores comparten una IP dinámica, almacenamiento, recursos y ciclo de vida. Esto quiere decir que si un POT se elimina todos los contenedores seran eliminados tambien.
* Replicaser:
* Service:
* Persistent Volume:
* Label:
