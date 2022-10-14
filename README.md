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


## 07/10/2022
### Inicio del taller de Kubernetes para principiantes
Aprendí que Kubernetes es una herramienta que nos ayuda a realizar microservicios que nos permite realizar nuestra aplicación en varios entregables(o servicios) interconectados por red que gracias a esto podemos entregar el proyecto, realizar actualizaciones de una manera más frecuente y cómoda que antes cuando se entregaba un único archivo, esto resulta muy útil a la hora de sacar nuestras aplicaciones o proyectos a producción.

Pero estos microproyectos dispones de su base de datos propia e independiente de las bases de datos del resto de servicios (aunque podrían llegar a tener una en común), esto también resulta muy cómodo y útil puesto que el proyecto al estar dividido de esta manera un microservicio creado anteriormente puede ser empleado para el desarrollo de un proyecto diferente, pudiendo trazar así diferentes rutas del proyecto.

Kubernetes también es una herramienta que nos ayuda a solucionar un gran problema que ocurre algunas veces y todo gracias al almacenaje en contenedores algunos de estos problemas que soluciona son:
*El uso de "/" en nuestra aplicación y después de sacarlo a producción en el sistema operativo de alguien no funciona porque usa la "" en vez de la "/" dando lugar a problemas (estos problemas suelen derivas del sistema operativo).
*Que la versión utilizada de Java de la producción sea diferente a la del desarrollo por ejemplo que en desarrollo se emplee un Java 6 y en producción se emplee un java 8.

Estos contenedores se crean a partir de un **fichero DOCKERFILE** donde definiremos los siguiente:

1. Que sistema operativo queremos usar, Windows,Linux,Mac,...
2. Definir parámetros como variables de entorno.
3. Qué dependencias tenemos que instalar o son necesarios, por ejemplo si nuestra aplicación necesita Java 11 pues gracias al contenedor se instalará Java 11.
4. Añadir nuestra aplicación directamente al equipo.
5. Que puesto utilizará nuestra aplicación y realizar un EXPOSE para poder tenerlo operativo.
6. El comando que permite lanzar o arrancar nuestra aplicación.

Conceptos básicos o imprescindibles que se deben saber o conocer de Kubernetes:
* **POD**: Es como si se tratase de una máquina virtual, solo que en vez de disponer de varios procesos dispone de uno o varios contenedores, pero todos los contenedores comparten una IP dinámica, almacenamiento, recursos y ciclo de vida. Esto quiere decir que si un POT se elimina todos los contenedores seran eliminados tambien.
* **Replicaser**: Es lo que va comprobando periodicamente como está nuestro pod para saber si esta en su estado óptimo o no y dentro de lo que cabe ejerce los cambios necesarios.
* **Service**: Agrupa los pots por etiquetas para poder referirnos por un nonbre al pod puesto que su ip es dinámica y cambia continuamente haciendo que sea dificil llamarlo
* **Persistent Volume**: Es el COMO se puede almacenar el contenido que es lo que nos permite tener esta persistencia de datos.
**Label**: Es como se le llama el valor al que asociamos los objetos en Kubernetes (aunque tambien se le puede conocer como tupla).

## 10/10/2022
### Continuación del taller de Kubernetes para principiantes(remate de la parte teórica y retoques en lo realizado el día 07/10)
En Kubernetes podemos dividirlo en dos partes principales con las que se controla y organizan las cosas:
* **El Master:** Denominamos master o master node a lo que seria llamado el controlador de los nodos, puesto que en el encontramos:
1. **La Api** a la que está asociada nuestro contenedor o nuestros nodos
2. **La etcd** es por así decirlo la base de datos que tienen en comun nuestros nodos en donde esta guardado todos los datos de este grupo de nodo o contenedor
3. **Los scheduler y los controlers** como pueden indicar sus nombres constan de las herramientas,métodos o conjunto de instrucciones que podemos ejecutar para el contenedor.
* **Los Nodos:** Son nuestros pods en donde cada uno dispondra de unos datos o información en concreta almacenada en ellos y donde los scheduler y controlers sueltan sus intrucciones con referencia a ellos.

Por ultimo en kubernetes en caso de que uno de los nodos falle, la información que el nodo dispusiera se reparte entre el resto de nodos que está estea en el pod y tambien si solicitamos que se envia X informacion a Y nodos en caso de que en uno no llegue o falle esta sera enviada a otros de los nodos puesto que la información debe ser almacenada en el pod.

## 12/10/2022
### Finalización del taller y ejemplos prácticos de algunos comandos básicos de kubernetes en consola

#### Comandos básicos de creación y visualización de pods y deployments

* Para poder crear un servicio necesitaremos insertar en consola el comando **kubectl apply -f + (nombre del fichero .yml o el contenido escrito todo en consola)**

![Contenido que debe tener el fichero .yml o lo que se debe redactar junto el comando](/capturas/ContenidoYML.PNG)

* Una vez creado podemos usar el comando **kubectl get services/deployment/..** 

![En caso de obtener un servicio utilizando el comando watch en una consola a parte mirariamos algo tal que así](/capturas/resultado.PNG)

![Esto resultaria la visualización normal en consola sin un watch](/capturas/get.PNG)

* Con el comando **kubectl create + (fichero .yml o contenido escrito en consola)** podemos crear nuestros servicios,pods,deployments...

![Cuando creamos un algo nuevo el watch nos pondrá en el status que se está creando](/capturas/Captura.PNG)

* Con el comando **kubectl delete + (el nombre, o la ip de lo que deseamos borrar)** eleminará el servicio pero esto es difente si lo hacemos con un deployment o no (tambien se puede aplicar un **kubectl delete all** para eleminar todos el contenido incluido los deployments).

**Cuando eleminamos un servicio que no está en un deployment el status nos pondra que se esta terminando**.

![Cuando eleminamos un servicio que no está en un deployment el status nos pondra que se esta terminando](/capturas/TerminatingServiceNoDeploy.PNG)

![Nos quedará algo tal que así](/capturas/resultado.PNG)

**Sin embargo si es en un deployment podremos ver como esta terminando el servicio y a su vez esta creando uno nuevo con los datos e información que disponia el que está terminando**.

![Sin embargo si es en un deployment podremos ver como esta terminando el servicio y a su vez esta creando uno nuevo con los datos e información que disponia el que está terminando](/capturas/deploy.PNG)

* Aunque nosotros en el fichero .yml o en el contenido podremos definir una label añadiendo la propiedad **label: MiLabel** en el fichero y entonces el servicio dispondra de una label.

![Ahora disponemos de un servicio que dispone de una label identificadora propia](/capturas/label.PNG)

* Si queremos entrar en nuestro servicio o pod simplemente tendremos que poner el comando **kubectl exec -ti +nombre del servicio o pod** aunque tambien se puede acceder con el comando **curl +ip y puerto del servicio**.

![El resultado al entrar seria algo tal que así con ejemplo de alguna ejecución con el curl del servicio](/capturas/entrarEnKubernetes.PNG)

* Como ultimo comando básico seria el comando **kubectl log + el nombre de mi aplicacción o servico** que gracias a este podremos ser capaces de detectar algunos errores que pudiera llegar a tener.

![Así es como se miraría el comando log en consola con la información del servicio](/capturas/log.PNG)

### Inicio del taller de Creación de contenedores y despliegue de aplicaciones.
Aprendí como lanzar un DOCKERFILE y la importancia que tiene el limitar los recursos que emplee nuestro contendor, puesto que esto nos puede generar problemas dado que cada contener consume recursos físicos de una maquina o host y si tenemos por ejemplo 5 contenedores de kubernetes y uno de ellos esta empleando una gran cantidad de CPU o de memoria hará que no quede sufience para los otros 4 restantes siendo perjudicial para nuestros servicios.

**Lanzamiento de un DOCKERFILE desde consola**.

![Imagen de DOCKERFILE EN CONSOLA](/capturas/curso2/Captura.PNG)

Gracias a herramientas como **Docker build** podremos crear la imagen de nuestro contenedor poniendo el comando **docker build -t + nombre de ka imagen**.

**Resultado del lanzamiento del comando**.

![Resultado](/capturas/curso2/Creacion_de_imagen.PNG)

**Con docker run -ti --rm -p + puerto + nombre** podremos lanzar nuestro contenedor.

![Ejecutando Contenedor](/capturas/curso2/dockerRun.PNG)

Si queremos limitar los recursos que consume nuestro contenedor tenemos 2 maneras de hacer:
* La primera es escribiendo en la consola el comando **docker run -ti --rm -p + puerto + nombre + puerto que se empleará + -m + los megabytes de ram que le otorgaremos + --cpus="cantidad de cpus" + nombre servicio**.
Ejemplo de comando con 1 de cpu y 400 megas de ram.

![Ejemplo](/capturas/curso2/ComandoLimitador.PNG)

* La segunda manera seria escribiendo en el fichero .yml que se escribiria de la siguiente manera:

![ejemplo](/capturas/curso2/YmlConLimitación.PNG)

Si realizamos un curl my resources en Java 8 veremos que no nos pone 1 cuarto de lo que nosotros limitamos si no el de la máquina en si.

![ejemplo](/capturas/curso2/ResultadoMentiroso.PNG)

En cambio si estamos en Java 11 veremos que el resultado es correcto y usa de lo limitado anteriormente.

![ejemplo](/capturas/curso2/ResultadoEnJava11.PNG)

De manera normal cada servicio consume hasta 1 cuarto del recurso que dispone lo malo es que en **caso de que realicemos un servicio en java, este tendrá que ser en java 11 porque si lo ponemos en java 8 este elegirá consumir 1 cuarto de los recursos que dispone la máquina NO de los recursos que tiene definidos para consumir el contenedor**.

Un comando muy útil es el "kuberctl describe + nombre del pod,deployment,contenedor" que nos da la información que esta definida en el mismo como se ve en la imagen el deployment de ejemplo dispone de los limitadores definidos anteriormente.

![ejemplo](/capturas/curso2/ComandoDescribeServices.PNG)

**Si realizasemos la request en Java 8 con los limitadores no saltaria una excepción dado que consume más recursos de lo que dispone y eso no es lo que se busca**.

![ejemplo](/capturas/curso2/ExecuteJava8.PNG)

**Sin enbargo si lo realizamos en Java 11 (o superior) no sucedera ningún problema dado que hace caso de los limitadores puestos**

![ejemplo](/capturas/curso2/request.PNG)

## 13/10/2022
### Finalización del taller de Creación de contenedores y despliegue de aplicaciones
**Nota en lo explicado anteriormente aunque se empleen comando estilo docker en algunos casos en kubernetes se realiza exactamente igual, lo que pasa es que kubernetes y docker suelen ir muy de la mano.**

En kubernetes hay 2 conceptos super importantes a la hora de actualizar nuestro servicio que son el **LivessProbe** y el **ReadynessProbe** porque sin ellos nuestro servicio sufriria algun que otro timeDown como la imagen de ejemplo:

![ejemplo](/capturas/curso2/DownTimes.PNG)

* **LivessProbe:** Es lo que se denomina cuando nuestra aplicación esta corriendo o está "viva", pero si se le hace una llamada y esta no está respondiendo la aplicación pasa a estar en lo que se llama **"estado zombie"** que significa que nuestra aplicación existe esta gastando recuerso esta lanzada, pero no hace nada entonces lo que sucede es que nuestra aplicación sufre un RESTART provocando asi un pequeño "cierre" de la misma.

**Imagen de un fallo con SOLO LivesProbe**

![ejemplo](/capturas/curso2/Line.PNG)

* **ReadynessProbe:** Esto se dedica a estar comprobando todo el rato que nuestra aplicación estea Ready, en caso de que se actualice o algo suceda en la aplicacción esta no la resetea si no que lanza otra como si fuera una copia y mientras no esta ready esta copia la version anterior sigue funcionando y es cuando la copia esta lista que se hace las llamadas sobre la copia, porque originalmente la aplicacción sigue corriendo.

**Imagen de un fallo con SOLO ReadynessProbe**

![ejemplo](/capturas/curso2/READ.PNG)

**Por tanto si definimos un LivessProbe y un ReadynessProbe en nuestro fichero yml de nuestro contenedor de esta manera.(los initalSeconds y periods son para que se tenga un breve tiempo de espera como si fuera una pantalla de carga)**

![ejemplo](/capturas/curso2/Vida.PNG)

**Y gracias a esto nuestra aplicación no presentara ningún timeDown.**

![ejemplo](/capturas/curso2/CeroTimeDown.PNG)

Por ultimo, cada contenedor dispone de una configuración propias con sus variables de entorno y existen dos maneras de cambiar:

1. Poniendo en la consola el comando **kubectl set env + el nombre del pod o deployment+ claveVariable=valor**

![ejemplo](/capturas/curso2/PrimerCambio.PNG)

**Resultado**

![ejemplo](/capturas/curso2/CambioDeVariableDeEntorno.PNG)

2. Con un **Mapa De Configuración** que se trata de un objeto de kubernetes en el que se puede definir unas claves y unos valores que se usaran en la aplicacción y para ello necesitaremos dos cosas imprescindibles:

* Un fichero .properties donde estaran definidas nuestras duplas clave valor

![ejemplo](/capturas/curso2/Properties.PNG)

* Y definir en nuestro .yml que utilizaremos ese fichero de configuración

![ejemplo](/capturas/curso2/Config.PNG)

**El resultado es el mismo, solo que dependiendo de la aplicacción es mejor hacer el cambio de una manera u otra**

![ejemplo](/capturas/curso2/CambioDeVariableDeEntorno.PNG)

## 14/10/2022
### Inicialización y finalización del taller de modelo de persistencia y pods
El taller trataba acerca de los **Volumenes** los principales ayudantes a la hora dede almacenar datos de un contenedor, porque como se sabe cuando se borra un contenedor o incluso se reinicia la información que tenia previamente se borrar y es gracias a los volumenes podemos preservar estos datos.

En primer lugar para poder disponer de un volumen tendremos que definir un PersistenVolumen en un fichero .yml y su contenido sería algo similar a esto:

![ejemplo](/capturas/curso3/PersistentVolumen.PNG)

Sin embargo existen dos maneras de gestionar el espacio de nuestros volumenes:

* Empezando con la manera menos optima tenemos el metodo manual que insertando en el fichero .yml la cantidad máxima que dispondra nuestro POD, este le ahorrará ese espacio de memoria aunque, si se llega a llenar vaciará su contenido hasta que se pueda añadir el nuevo contenido.

* Luego disponemos de los denominado **Storage Class** que es a lo que se correspondería la imagen anterior, este resulta el método más empleado porque su almacenamiento es DINAMICO es decir no debemos definirle un máximo simplemente seguirá guardando información siempre que la máquina tenga espacio.
**En consola podemos ver si disponemos de un storage class si escribimos en la consola **kubectl get storageclass** **

![ejemplo](/capturas/curso3/storageclass.PNG)

** Con el comando kubectl get pvc podremos obtener la información sobre los volumenes, capacidades, nodos de accesos y que tipo de Storageclass tiene nuestro servicio**

![ejemplo](/capturas/curso3/getPvc.PNG)

Tambien es importante conocer los siguientes terminos sobre el volumen:

1. **VolumeMount:** que es donde se mapea nuestro sistema de almacenamiento en línea PERO dentro del propio sistema de archivos local.
  
 **En un fichero .yml de un POD podemos definir un VolumeMount y se haría de esta manera**
 
 ![ejemplo](/capturas/curso3/VolumenMount.PNG)
 
2. **PersistentVolumeClaim:** O tambien conocido como PVC es el llamado al reclamo de espacio que se le hace a un PersistentVolumen o un StorageClass.

**Esquema simple sobre como funciona la persistencia de volumen**

![ejemplo](/capturas/curso3/Esquema.PNG)

Kubernetes tambien dispone de los llamados **Kubernetes secrets** que se emplean para insertar o guardar cierta información que no queremos que se vea de cara al publico como por ejemplo la contraseña y usuario en una base de datos.


Sin embargo debemos andarnos con mucho ojo cuando guardamos nuestros secretos, porque Kubernetes normalmente guarda todo en en base de 64 y eso no es un método de incriptación, y esto resulta peligroso por lo siguiente:

1. Si ejecutamos en nuestra consola el comando **kubectl get secrets + nombre del secreto (refieriendose a password, user) -o yaml** (ojo con get secrets se obtiene SOLO el nombre de los secretos), podremos obtener la siguiente información.

![ejemplo](/capturas/curso3/SecretOfuscado.PNG)

2. Con lo obtenido del comando anterior podremos realizar un comando echo del valor que nos devolvió anterior mente y podremos obtener el valor del secreto.

![ejemplo](/capturas/curso3/EchoDeSecreto.PNG)

Pero esto se podría intentar solucionar o bien buscando una manera de cambiar que no estea en base de 64(existen programas que ya te cambian esto) o un "apaño" es definirlo en un fichero .yml y al estar definido todos los secretos seran puestos **cada uno de ellos en un fichero aparte** y obviamente el contenido de ese fichero es el valor del secreto.

**Definición de un secreto en un fichero .yml**

![ejemplo](/capturas/curso3/InsertarVolumenYSecretos.PNG)

Finalmente en el talle hablo de los siguientes conceptos de kubernetes que son importantes (cada uno de los siguientes conceptos deben ser definidos en nuestro fichero .yml como viene a ser costumbre y despues de la definición de cada uno le acompañará su respectiva imagen de definición en el fichero):

* **Afinity:** La afinidad es lo que nos ayuda a definir que PODS qieremos que corran juntos, es decir al mismo tiempo como si se tratase de un programa multi hilo, la afinidad se define através de agrupaciones de valores de las labels que le asignamos a nuestro servicio, es decir podriamos escribirlo en consola con el comando **kubectl label nodes +nombre del pod CLAVE=VALOR**, pero podemos definir los grupos en el fichero .yml y luego en los ficheros de los PODS poner la estiqueta correspondiente.

**En este ejemplo estamos definiendo una afinidad sobre las labels "color" cuyo valor sea "blue"**

![ejemplo](/capturas/curso3/AfinidadPNG.PNG)

* **Antiafinity:** Es la afinidad inversa, es decir la empleamos cuando queremos que dos PODS no corran simultaneamente nunca, bien porque el POD consume muchos recursos físicos o bien porque se pisan el uno con el otro.

**En este ejemplo estamos definiendo una antiafinidad sobre las labels "app" cuyo valor sea "myboot"**

![ejemplo](/capturas/curso3/AntiAfinidad.PNG)

* **JOB:** Es el nombre con el que se le denomina aquellos PODS que simplemente ejecutan una acción y despues de eso el POD se muere, un ejemplo de esto seria como insertar un nuevo usuario en nuestra base de datos de usuarios.

**En este ejemplo simplemente estamos definiendo un JOB que es el "Hello DevNation" y solo se ejecutará una vez.**

![ejemplo](/capturas/curso3/ELJOB.PNG)

* **CronJOB:** Podríamos decir que el CronJOB es la contraparte de un JOB porque mientras el JOB solo lanza la acción una vez en CronJOB ejecuta periodicamente un JOB.
 
 **El JOB es el mismo que el del ejemplo anterior solo que aquí al estar en en ConJOB se ejecutará periodicamente, en schedule definimos cada cuanto tiempo se debe de estar lanzando el JOB en este caso se lanzaría cada 1 minuto.**
 
 ![ejemplo](/capturas/curso3/ConJob.PNG)
 
 **NOTA: NOSOTROS SI HACEMOS EN CONSOLA UN kubectl get job ESTE NOS DEVOLVERÁ CON JOBS COMO LOS CRONJOBS, por tanto es importante definirlos con un nombre apropiado.**
 
 * **Daemonset:** Una manera breve de explicar que es sería diciendo que se trata de una red de comunicación entre un grupo de nodos y un POD, es decir nosotros desde un nodo podemos mandar información a otro como si de un chat se tratase siempre y cuando **los dos nodos disponga de UN POD EN COMÚN** y si añadieramos un nuevo nodo a esta red de nodos con un solo POD en común automaticamente se añadi y con la accesibilidad a la información del POD.

* **Statefulset:** Uno de los principales problemas de los deploiments es que el nombre del host de referencía es aleatorio, sin embargo con statefulset nosotros podremos definir un nombre y "tratarlo como si de un array unidimensional se tratase".

**El name definido en este fichero .yml es el nombre que dispondrá es el definido en el campo name.**

![ejemplo](/capturas/curso3/satatefulset.PNG)

**Si nos fijamos en esta imagen los servicios disponen ya de un nombre identificador y un indice, pero tenemos que tener en cuenta a la hora de borrar el indice que estos tiene, por ejemplo si quisieramos borrar el que esta en segundo lugar su indice es 1,**

![ejemplo](/capturas/curso3/Ejemplo.PNG)


