# Docker-y-Kubernetes
## 06/10/2022
### Inicio y finalización del curso de **Fundamentos Generales Orquestación y Automatización IT:**
Aprendí el que es la automatización: que resulta ser un método que trata de reducir la intervención humana lo máximo posible mediante varios procesos (porque así se evitan los fallos humanos).

Los pasos que se deberían seguir para automatizar un proceso que son tales como:

* **Identificación de entradas de información** (por ejemplo que un usuario se da de alta).

* Generar un **mecanismo de disparador** de la automatización (crear que mediante un evento se lance la automatización).

* **Evaluar las entradas de la información** (un ejemplo de esto sería el que cuando un usuario se registra a parte de la información general del mismo si disponemos de una clasificación por roles sepamos qué procesos se deben lanzar para ese rol determinado).

* **Ejecutar las tareas** de la automatización (Una vez hecho todo lo anterior los procesos se ejecutan).

Que existen distintos tipos de automatización que son principalmente:

* **Manual**: Consiste en que tenemos una información y nuestro proceso se lanza MANUALMENTE dando una información que disponemos previamente.

* **Programado**: Es cuando se tienen que realizar tareas repetitivas y entonces se lanzan una serie de procesos que se encargan de realizarlas.

* **Evento**: Se dispara cuando sucede un problema como por ejemplo la falta de espacio en un servidor y este se encarga de hacer los procesos necesarios para solucionar este problema resultan ser procesos proactivos dando tiempo a mejorar las estructuras del proyecto.

* **Auto-servicio**: Esta automatización permite realizar un sistema frontend y es cuando las incidencias de los usuarios o peticiones no son muy complejas y se solicitan mucho(es decir que son repetitivas pero a diferencia del programado este puede llegar a solucionar alguna incidencia más específica o no tan común), un ejemplo de ello podría ser un servicio web.

También aprendí lo que es la Orquestación que es lo que nos permite realizar un control y mantenimiento de la automatización, lo que permite tener un mantenimiento centralizado por lo que nos permite mejorar, evaluar y optimizar la automatización.

A su vez que los distintos tipos de orquestación que hay que cada uno usa un método de comunicación que son tales como:

* **Orquestación de tareas programadas:** que sus principales disparadores suele ser eventos, normalmente su principal funcionamiento es la ejecución de un proceso o una app, **Su método de comunicación es a través de comunicación local**

* **Orquestación de Cloud** como su nombre bien indica su tipo de comunicación es através de **Servicios Cloud**, se usa principalmente para APIS o webs y permite un mayor control de los recurso del Cloud que se emplean y Automatizadores de bajo nivel

* **Orquestación de mantenimiento de la configuración** Este tipo de orquestación requiere de un servidor central o un protocolo remoto al que dirigirse, es muy empleado para el mantenimiento de servidores y su metodo de comunicación es através de **un protocolo remoto**

* **Integración continua y despliegue continuo** en esencia son muy similares ambos usan como método de comunicación un **agente** necesitan de uuna base de datos y agentes pero su principal diferencia es que **la integración continua se dedica a proveer automatización a construcción de software y testing **mientras que**el de despliegue continuo provee a los despliegues del software en distintos entornos al que fue echo el servicio**


##07/10/2022
###Inicio del curso de Kubernetes para principiantes
Aprendí que Kubernetes es una herramienta que nos ayuda a realizar microservicios que nos permite realizar nuestra aplicación en varios entregables(o servicios) interconectados por red que gracias a esto podemos entregar el proyecto, realizar actualizaciones de una manera más frecuente y cómoda que antes cuando se entregaba un único archivo, esto resulta muy útil a la hora de sacar nuestras aplicaciones o proyectos a producción.

Pero estos microproyectos dispones de su base de datos propia e independiente de las bases de datos del resto de servicios (aunque podrían llegar a tener una en común), esto también resulta muy cómodo y útil puesto que el proyecto al estar dividido de esta manera un microservicio creado anteriormente puede ser empleado para el desarrollo de un proyecto diferente, pudiendo trazar así diferentes rutas del proyecto.

Kubernetes también es una herramienta que nos ayuda a solucionar un gran problema que ocurre algunas veces y todo gracias al almacenaje en contenedores algunos de estos problemas que soluciona son:
*El uso de "/" en nuestra aplicación y después de sacarlo a producción en el sistema operativo de alguien no funciona porque usa la "" en vez de la "/" dando lugar a problemas (estos problemas suelen derivas del sistema operativo).
*Que la versión utilizada de Java de la producción sea diferente a la del desarrollo por ejemplo que en desarrollo se emplee un Java 6 y en producción se emplee un java 8.

Estos contenedores se crean a partir de un **fichero DOCKERFILE** donde definiremos los siguiente:

1.Que sistema operativo queremos usar, Windows,Linux,Mac,...
2.Definir parámetros como variables de entorno.
3.Qué dependencias tenemos que instalar o son necesarios, por ejemplo si nuestra aplicación necesita Java 11 pues gracias al contenedor se instalará Java 11.
4.Añadir nuestra aplicación directamente al equipo.
5.Que puesto utilizará nuestra aplicación y realizar un EXPOSE para poder tenerlo operativo.
6.El comando que permite lanzar o arrancar nuestra aplicación.

Conceptos básicos o imprescindibles que se deben saber o conocer de Kubernetes:
* **POD**: Es como si se tratase de una máquina virtual, solo que en vez de disponer de varios procesos dispone de uno o varios contenedores, pero todos los contenedores comparten una IP dinámica, almacenamiento, recursos y ciclo de vida. Esto quiere decir que si un POT se elimina todos los contenedores seran eliminados tambien.
* **Replicaser**:
* **Service**:
* **Persistent Volume**:
Label:
