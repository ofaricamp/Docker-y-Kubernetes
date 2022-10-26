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

![ejemplo](/capturas/Curso3/PersistentVolume.png)

Sin embargo existen dos maneras de gestionar el espacio de nuestros volumenes:

* Empezando con la manera menos optima tenemos el metodo manual que insertando en el fichero .yml la cantidad máxima que dispondra nuestro POD, este le ahorrará ese espacio de memoria aunque, si se llega a llenar vaciará su contenido hasta que se pueda añadir el nuevo contenido.

* Luego disponemos de los denominado **Storage Class** que es a lo que se correspondería la imagen anterior, este resulta el método más empleado porque su almacenamiento es DINAMICO es decir no debemos definirle un máximo simplemente seguirá guardando información siempre que la máquina tenga espacio.
**En consola podemos ver si disponemos de un storage class si escribimos en la consola **kubectl get storageclass** **

![ejemplo](/capturas/Curso3/storageclass.PNG)

** Con el comando kubectl get pvc podremos obtener la información sobre los volumenes, capacidades, nodos de accesos y que tipo de Storageclass tiene nuestro servicio**

![ejemplo](/capturas/Curso3/getPvc.PNG)

Tambien es importante conocer los siguientes terminos sobre el volumen:

1. **VolumeMount:** que es donde se mapea nuestro sistema de almacenamiento en línea PERO dentro del propio sistema de archivos local.
  
 **En un fichero .yml de un POD podemos definir un VolumeMount y se haría de esta manera**
 
 ![ejemplo](/capturas/Curso3/VolumenMount.PNG)
 
2. **PersistentVolumeClaim:** O tambien conocido como PVC es el llamado al reclamo de espacio que se le hace a un PersistentVolumen o un StorageClass.

**Esquema simple sobre como funciona la persistencia de volumen**

![ejemplo](/capturas/Curso3/Esquema.png)

Kubernetes tambien dispone de los llamados **Kubernetes secrets** que se emplean para insertar o guardar cierta información que no queremos que se vea de cara al publico como por ejemplo la contraseña y usuario en una base de datos.

Sin embargo debemos andarnos con mucho ojo cuando guardamos nuestros secretos, porque Kubernetes normalmente guarda todo en en base de 64 y eso no es un método de incriptación, y esto resulta peligroso por lo siguiente:

1. Si ejecutamos en nuestra consola el comando **kubectl get secrets + nombre del secreto (refieriendose a password, user) -o yaml** (ojo con get secrets se obtiene SOLO el nombre de los secretos), podremos obtener la siguiente información.

![ejemplo](/capturas/Curso3/SecretOfuscado.PNG)

2. Con lo obtenido del comando anterior podremos realizar un comando echo del valor que nos devolvió anterior mente y podremos obtener el valor del secreto.

![ejemplo](/capturas/Curso3/EchoDeSecreto.PNG)

Pero esto se podría intentar solucionar o bien buscando una manera de cambiar que no estea en base de 64(existen programas que ya te cambian esto) o un "apaño" es definirlo en un fichero .yml y al estar definido todos los secretos seran puestos **cada uno de ellos en un fichero aparte** y obviamente el contenido de ese fichero es el valor del secreto.

**Definición de un secreto en un fichero .yml**

![ejemplo](/capturas/Curso3/InsertarVolumenYSecretos.PNG)

Finalmente en el talle hablo de los siguientes conceptos de kubernetes que son importantes (cada uno de los siguientes conceptos deben ser definidos en nuestro fichero .yml como viene a ser costumbre y despues de la definición de cada uno le acompañará su respectiva imagen de definición en el fichero):

* **Afinity:** La afinidad es lo que nos ayuda a definir que PODS qieremos que corran juntos, es decir al mismo tiempo como si se tratase de un programa multi hilo, la afinidad se define através de agrupaciones de valores de las labels que le asignamos a nuestro servicio, es decir podriamos escribirlo en consola con el comando **kubectl label nodes +nombre del pod CLAVE=VALOR**, pero podemos definir los grupos en el fichero .yml y luego en los ficheros de los PODS poner la estiqueta correspondiente.

**En este ejemplo estamos definiendo una afinidad sobre las labels "color" cuyo valor sea "blue"**

![ejemplo](/capturas/Curso3/AfinidadPNG.PNG)

* **Antiafinity:** Es la afinidad inversa, es decir la empleamos cuando queremos que dos PODS no corran simultaneamente nunca, bien porque el POD consume muchos recursos físicos o bien porque se pisan el uno con el otro.

**En este ejemplo estamos definiendo una antiafinidad sobre las labels "app" cuyo valor sea "myboot"**

![ejemplo](/capturas/Curso3/Antiafinidad.PNG)

* **JOB:** Es el nombre con el que se le denomina aquellos PODS que simplemente ejecutan una acción y despues de eso el POD se muere, un ejemplo de esto seria como insertar un nuevo usuario en nuestra base de datos de usuarios.

**En este ejemplo simplemente estamos definiendo un JOB que es el "Hello DevNation" y solo se ejecutará una vez.**

![ejemplo](/capturas/Curso3/ELJOB.PNG)

* **CronJOB:** Podríamos decir que el CronJOB es la contraparte de un JOB porque mientras el JOB solo lanza la acción una vez en CronJOB ejecuta periodicamente un JOB.
 
 **El JOB es el mismo que el del ejemplo anterior solo que aquí al estar en en ConJOB se ejecutará periodicamente, en schedule definimos cada cuanto tiempo se debe de estar lanzando el JOB en este caso se lanzaría cada 1 minuto.**
 
 ![ejemplo](/capturas/Curso3/ConJob.PNG)
 
 **NOTA: NOSOTROS SI HACEMOS EN CONSOLA UN kubectl get job ESTE NOS DEVOLVERÁ CON JOBS COMO LOS CRONJOBS, por tanto es importante definirlos con un nombre apropiado.**
 
 * **Daemonset:** Una manera breve de explicar que es sería diciendo que se trata de una red de comunicación entre un grupo de nodos y un POD, es decir nosotros desde un nodo podemos mandar información a otro como si de un chat se tratase siempre y cuando **los dos nodos disponga de UN POD EN COMÚN** y si añadieramos un nuevo nodo a esta red de nodos con un solo POD en común automaticamente se añadi y con la accesibilidad a la información del POD.

* **Statefulset:** Uno de los principales problemas de los deploiments es que el nombre del host de referencía es aleatorio, sin embargo con statefulset nosotros podremos definir un nombre y "tratarlo como si de un array unidimensional se tratase".

**El name definido en este fichero .yml es el nombre que dispondrá es el definido en el campo name.**

![ejemplo](/capturas/Curso3/satatefulset.PNG)

**Si nos fijamos en esta imagen los servicios disponen ya de un nombre identificador y un indice, pero tenemos que tener en cuenta a la hora de borrar el indice que estos tiene, por ejemplo si quisieramos borrar el que esta en segundo lugar su indice es 1,**

![ejemplo](/capturas/Curso3/Ejemplo.png)

## 15/10/2022
### Inicio y finalización del taller Kind: Kubernetes en Docker
En este taller aprendí que es kind, que es una herramienta horientada hacia el testing donde podemos en un contenedor de DOCKER correr los nodos y contenedores de Kubernetes. Tambien nos permite crear clusters y contruir imágenes, pero ojo está escrita en GO pero no es necesario disponer de un gran conocimiento como tal, pero lo más importante es que se trata de una herramienta multiplataforma.

**Para poder hacernos una idea de super sencilla de GO simplemente vamos a crear un "hello world" en GO, la siguiente imagen es el código en GO**

![ejemplo](/capturas/curso4/HolaMundoGo.PNG)

**Para ejecutar y compilar seria estos dos comandos que tenemos aquí, IMPORTANTE mi programa se llama hello luego se tendría que cambiar al que se se use luego**

![ejemplo](/capturas/curso4/CompilacionYEjecucionGO.PNG)

**Finalmente lanzamos el programa**

![ejemplo](/capturas/curso4/Resultado.PNG)

**Un detalle importante en la instalación de GO es seguir los pasos que te pone en la propia página, para poder evitar problemas**

Una vez echo el "hello world" de GO, se empieza con la descarga de KIND y hay unos puntos que me gustaría resaltar:

* El método que se enseñaba en el taller que era con **KIND GO111MODULE="on" go get sigs.k8s.io/kind@v0.4.0** está **OBSOLETO** en su lugar debemos usar **go install sigs.k8s.io/kind@v0.4.0**
* En caso de que no dispusieramos aun de GO instalado se puede descargar con la siguiente serie de comandos:
  1. **curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.16.0/kind-linux-amd64**
  2. **chmod +x ./kind**
  3. **sudo mv ./kind /usr/local/bin/kind**

Una vez que se tiene instalado KIND para practicar se realizaron ejercicio sencillos como la creación de un cluster, su borrado, ver sus logs y agregarle una imagen a nuestro cluster:

* Para poder crear un cluster tendremos que escribir en nuestra consola el comando **sudo kind create cluster** una vez se acaben los procesos de creación nos saldra algo similar a la imagen, aunque el comando tambien se puede escribir **sudo kind create cluester --name nombre** la diferencía entre uno y otro se explica más adelante.

![ejemplo](/capturas/curso4/CreacionDeUnNuevoCluster.PNG)

**Si lanzamos un docker logs podremos ver los logs que se lanzan y en caso de que algún problema ocurriera es aquí donde nos informarian (ojo tambien podríamos redirigir el log a un fichero de texto con el comando less pero tenemos que poner el nombre de la aplicación)**

![ejemplo](/capturas/curso4/logs.PNG)

**Ejemplo de LOG en un fichero de texto creado con el comando less**

![ejemplo](/capturas/curso4/logEnLess.PNG)

Como dije hay dos maneras de lanzar el comando y la diferencía es que en uno se nos creará un cluester con el nombre predeterminado que les asigna KIND mientras que en el otro dispondra de un nombre identificardor puesto por nosotros, si hacemos un **docker ps** podremos ver los nombres de los clusters y en la siguiente imagen hice un cluster con cada uno de los comando para que se pueda ver la diferencía.

![ejemplo](/capturas/curso4/NewName.PNG)

* Para borrar un cluster es tan sencillo como ejecutar un **sudo kind delete cluster --name nombreDelCluster**

![ejemplo](/capturas/curso4/Delete.PNG)

* Finalmente es que una de las ventajas de KIND es que podemos añadirle nosotros una imagen externa con docker, con el comando **kind load** podremos insertale una imagen que tengamos nosotros externamente y así si el cluster no la tiene se la descargar.

![ejemplo](/capturas/curso4/imagenExterna.PNG)

## 18/10/2022
### Inicio del curso de Introducción a Docker
**Nota: Para poder seguir avanzando el los cursos de Kubernetes es necesario tener como mínimo tener visto hasta el Curso de Docker para desarroladores, tambien importante tener en cuenta que algunos de los conceptos o ideas que dispone Docker puede ser algo ya visto en Kubernetes, pero porque suelen ir muy de la mano**

En este curso aprendí en primer lugar que es docker:

**DOCKER:** Es un software que realiza una vitualización a nivel de sistema operativo gracias a lo llamado "contenedores", lo que lo diferencía con respecto a otras herramienta es su práctico método de "aislamiento" de un sistema o servicio para poder ser empleado en nuestra máquina.

Lo se se consigue gracias a esto es que al realizar una compartición de recursos con docker, esta consuma los recursos únicamente necesarios, porque estará previamente cargado en memoria los recursos necesarios, **es importante tener en cuenta que este aislamiento de recursos es a nivel de KERNEL**.

Los principales recursos para lograr este aislamiento son:

* **Cgroups:** Son una serie de controles de jerarquia que nos permite definir la manera en la que nuestra máquina va asignar sus recursos a un conjunto de procesos, esto es gracias a asignación de valores de prioridad.

**Por ejemplo: Si disponemos de un apache y este tiene 9 procesos y solo 1 servicio, suponiendo que todos tengan la misma prioridad,
al ejecutarse todos al servicio le corresponde un 10% de la CPU.**

* **Namespaces:** Es donde podemos almacenar uno o más identificadores únicos, pero ojo un mismo identificador puede estar definido en otros NameSpaces.

**Por ejemplo Si dos empleados de empresas distintas empiezan a trabajar pueden coincidir y tener el mismo número de identificación,todo
porque un identificador es del nameSpace de la empresa X y el otro es el de la empresa Y.**

Claramente nosotros a un contenedor Docker le podemos definir a partir de unos limitadores cuanto debe consumir de nuestra máquina y que ella pude acceder a toda la indormación que dispone el contenedor, pero normalmente el contenedor no puede acceder a todo de lo que dispone la máquina, sobra decir que al tratarse de un servicio que utiliza clouds la portabilidad de los contenedores resulta cómoda.

En Docker es importante tener mentalizados bien una serie de conceptos básicos que son:

* **Docker Engine:** Es la aplicacción cliente-servidor y esta compuesto por 3 elementos:

1. **Demonio Docker:** Es quien está a la escucha para poder ejecutar esos contenedores sobre nuestra máquina (se ejecuta en segundo plano).
2.  **Rest API:** s imprescindible para realizar el desarrolo de otro sofware, porque es quien se encarga de que podamos comunicarnos con el Deminio Docker.
3.  **La interfaz de línea de comandos (CLI):** A groso modo es el comando "docker" puesto que es lo que nos permite usar el servicio.

**Esto sigue el un esquema de funcionamiento que es que la CLI llama al Rest API pidiendole una orden y la Rest API le manda esa tarea al Demonio Docker y es el Demonio quien le manda la orden al CLI**

![ejemplo](/capturas/CursosDocker/Curso1/Esquema.png)

* **Docker Registry:** Como resumen breve es el servicio que nos permite almanecar imágenes(este concepto será explicado más adelante), estas imágenes pueden ser privadas o públicas da igual.

## 19/10/2022
### Finalización del Curso de Introducción de Docker

Siguiendo con lo explicado anteriormente, pero antes de todo resaltaré que los apartados de ** volumns. persistentVolumns y que es un DOCKERFILE como se lanza y etc,... simplemente los menciono aquí, porque YA ESTAN EXPLICADOS EN KUBERNETES**.

Docker está compuesto principalmente por dos elementos que son fundamentales que son la **Imagen** y **Contenedor**

* **Imagen:** Es una "platilla" de solo lectura que dispone de unos parámetros preparados para poder ejecutarse, pero ojo todas basadas en sistemas Linux, debemos tener en cuenta que todo lo que hagamos gira entorno a la imagen o imagenes que dispongamos.

* **Contenedor:**  Es una instancia de la imagen, por así decirlo es como si fuera un directorio padre y dentro tiene subdirectorios, esto actua como una máquina virtual es decir podemos ejecutarlos,reiniciarlos.

Docker al igual que Kubernetes dispone de unos comandos propios:

**Docker tiene docker start+ id del contenedor y docker stop + id del contenedor** que como indican sus nombres da inicio y para el servicio respectivamente y si nos fijamos en la imagen podemos ver como el contenedor de Ubuntu pasa a Exited con el stop mientras que con el start pasa a UP.
**Nota: en los comando no tenemos porque poner el ID completo sirve con poner los 3 primeros caracteres del mismo**

![ejemplo](/capturas/IntroduccionDocker/startYStop.png)

**Dockert images devuelve una lista de las imagenes que tenemos creadas mientras que el comando docker history + id de la imagen nos devuelve un historial de cambios.**

![ejemplo](/capturas/IntroduccionDocker/imagesYHistory.png)

Con el comando **docker inspect + id de la imagen** podremos obtener toda la información que esta tiene y si nos fijamos la estructura es similar a los ficheros .yml que tratamos en Kubernetes anteriormente.

![ejemplo](/capturas/IntroduccionDocker/inspect.png)

Con el comando **docker search + nombre de la imagen** obtendremos una lista de todas las imagenes con ese nombre y si hacemos un **docker pull + nombre de la imagen** podremos descargala sin problemas.

![ejemplo](/capturas/IntroduccionDocker/dockerPullUbuntu.png)

Con **docker rmi + id de la imagen** borraremos esa imagen de nuestra máquina.

![ejemplo](/capturas/IntroduccionDocker/dockerRmi.png)

**Pero cuidado con el borrado porque NO PODREMOS BORRAR UN CONTENEDOR QUE NO ESTEA APAGADO** en la siguiente imagen intento eliminar el hello-world, pero no puedo al estar lanzado por tanto con el comando **docker ps** obtengo la informacion de los contenedores que estan encendidos y despues usando **docker rm + id del contenedor** lo apagaremos y entonces ya podremos usar el comand rmi.

![ejemplo](/capturas/IntroduccionDocker/rmiDocker.png)

Con **docker run -it + nombre de la imagen** nos ejecutará la imagen en cuestion y ojo en caso de que no la tengamos descargada nos la descarga y una vez la tengamos la lanzará.

![ejemplo](/capturas/IntroduccionDocker/runHelloWorld.png)

Simplemente por enseñar lo curioso que resulta docker yo si lanzo el comando **run docker -ir ubuntu** lanzará una consola funcional de linux en la que como se ve en la imagen puedo hacer un **ls y un apt update SIN NINGUN PROBLEMA**.

![ejemplo](/capturas/IntroduccionDocker/runUbuntu.png)

El siguiente comando es un comando **docker run** pero con una variante que es que le asignaremos al contenedor un puerto de nuestro ordenador luego lanzaremos un contenedor de ejemplo con el valor de 5000 y veremos que pasa.
**El programa es de python y me equivoco a proposito usando un puerto que tengo ocupado para que se aprecie que pasa cuando lo hacemos con un puerto que no está disponible**

![ejemplo](/capturas/IntroduccionDocker/puerto.png)

**Ahora si abrimos nuestro navegador u ponemos localhost:82(que es el puerto que le acabé asignando) miraremos que lo lanza PERFECTAMENTE**

![ejemplo](/capturas/IntroduccionDocker/holaMundoPy.png)

Con **docker network ls** obtendremos la lista de todos los networks que tenemos en nuestra máquina y si nos fijamos hay 3 tipos de drivers:
1. bridge: Es el que docker pone por defecto y emplea una interfaz fuente.
2. hots: se emplea para enlazar distintos contenedores dentro de un host.
3. none: sirve para aislar a un contenedor que no disponga de red.

Como aclaración sobre las Redes Bridge estas se emplean para aislar los segmentos de red y los contenedores solo se pueden comunicar con otros de la red UNICAMENTE,
claramente podremos añadir y quitar contenedores que disponga la red, es importante saber que los containers de esta red cuando salen van
A LA PRIMERA RED QUE ENCUENTRE DISPONIBLE.

Tambien solo se nombró a nivel teórico puesto que resultaría algo mas avanzado acerca de los Links de las Redes Bridge que es lo que nos permite vincular varios contenedores sin necesidad de exponer más puertos, que usa variable de entornos para almacenar datos, transmite información de manera segura entre contenedores y que para usarlos es **imprescindible el uso de nombres identificadosres(como cuando en kubernetes poniamos nuestro propio nombre para identificar un Container pues en docker no iba a ser menos)**

![ejemplo](/capturas/IntroduccionDocker/networksDocker.png)

Pero ojo nosotros podemos definir nuestro propio network con **docker create -d + tipo de driver + nombre del network**.

![ejemplo](/capturas/IntroduccionDocker/createNetwork.png)

Ahora con **docker network inspect + nombre del network** nos devolverá la información del network.

![ejemplo](/capturas/IntroduccionDocker/networkInspect.png)

De los Volumens solo resaltaré que si lanzamos un **docker volume inspect + id del servicio** podemos ver como ciertamente la estructura de su contenido es muy similar a la ya vista en Kubernetes.

![ejemplo](/capturas/IntroduccionDocker/InspectVolumen.png)

Como nota final me gustaría resalta que realmente los comandos básicos de docker siguen una extructura muy similar, simplemente tenemos que saber bien que queremos obtener o que queremos cambiar en nuestro contenedor y que se puede apreciar como Docker y Kubernetes resultan tener cosas similares entre ellos.

## 20/10/2022
### Inicio del Curso de Docker Para Desarroladores (es un Curso de 6 horas a si que da para rato)
La primera parte del curso es de introducción de docker, la miré entera porque al ser con profesores distintos podrían cambiar matices o que se enfoquen más en otras cosas y honestamente la hora y media que dura esta introducción de Docker esta mejor explicada, en esencial explica lo mismo que el anterior solo que remarka mucho sobre un tema importante de Docker que es el porqué se usa.

Docker tiene el dicho de **RUN, BUILD AND SHIP, ANY APP ANYWHERE** y este dicho incluye los 3 grandes beneficios de Docker que son:

* **Portabilidad:** Un contenedor es ejecutado por el Docker Engine, un demonio que es fácilmente instalable en todas las distribuciones Linux y 
también en Windows(aunque personalmente es más cómodo intalarte una consola de ubuntu y usarla que la de propio windows, simplemente porque la de Ubuntu reculta mucho más cómoda y práctica con respecto a la de Windows), un contenedor ejecuta una imagen de docker, que es una representación del sistema de ficheros que el contenedor va a utilizar para su ejecución. Una vez que hemos generado una imagen de Docker independientemente del sistema operativo que dispongamos.

* **Inmutabilidad:** Una aplicación la componen tanto el código fuente como las librerias del sistema operativo y del lenguaje de programación necesarias para la 
ejecución de dicho código, por tanto el código siempre ejecutará con las misma versión del código fuente y sus dependencias.

* **Ligereza:** Los contenedores comparten entre ellos el sistema operativo de la máquina, peor cada uno dispone de sus propios procesos, dicheros, espacio y usuarios(como se explicó con los Cgroups y namespaces), gracias a esto es lo que hace que su ejecución resulte más ligera que otros métodos disponibles.

Luego me gustó mucho que al final del curso el profesor dió su opinión profesional acerca de Docker y concluyó citando "Ignorar Docker será una desventaja
competitiva para cualquier compañía" dando a entender que es probable que el sistema de contenedores de Docker acabe siendo algo fundamental para cualquier trabajo puesto que resulta una muy útil herramienta.

## 22/10/2022
### Contunuación del curso de Docker para Desarroladores
Un tema a tratar cuando se habla de Docker son los microservicios, pero antes de hablar de ellos hay que definir que es una **Arquitectura SOA(Service Oriented Architecture):**

Es un componente que ofrece un servicio a distintos componentes para que todos consuman de ese Servicio (aunque se suele decir que SOA ofrece un contrato de una 
API REST versioonada, es decir que sea más sencillo actualizar nuestro servicio gracias a que si se pasa a una version 3.0 los servicios que usen la 1.0 puedan
aun usarla hasta que se actualicen y ya no se emplee la 1.0) y consiste en hacer los siguiente puntos:

* Minimiza al máximo las dependencias de un componente, es decir hacer el menor número de llamadas posible a otro, en algunos caso no se puede seguir este objetivo
pero siempre hay que tratarlo.

* Abstraer su implementación, es decir que nos sea indiferente en que lenguaje fue escrito o en que sistema operativo se está, claramente como en todo habrá lenguajes o sistemas operativos que hagan que la tarea resulte mucho más sencilla.

* Maximizar su reutilización, que cuando hagamos un componente se pueda reutilizar el mayor número de veces posible, resultará contradictorio puesto que antes se comentó de minimizar las dependencias, pero imaginemos que tenemos que hacer un programa y necesitamos de manera óptima 3 componentes y 2 de ellos ya estan en un contenedor cada uno,por tanto solo deberémos hacer un componente siendo una optimización de tiempo increible.

* Nuestros servicios debe tener un ciclo de vida TOTALMENTE INDEPENDIENTE, es decir que si tenemos que cambiar o actualizar un componente SOLO actualizamos o cambiamos
ese componente y no el resto de componente que está relacionados con el, porque actualizar un solo componente es más comodo que actuañizar un componente entero.

* Evitar que el componente se pueda caer y afectar a los clientes finales, es decir que los fallos no afecten negativamente a nuestros cliente.

* Realizar tests de los componentes continuamente y de manera automático para poder tener un servicio fuerte a prueba de muchos errores o problemas que puedan suceder en su ciclo de vida

Microservicios consta de los siguientes puntos:

1. El microservicio sigue los principio en la arquitectura SOA, podemos decir que es una evolución de la misma. Busca reducir al máximo el tamaño de nuestro componente, un ejemplo que se puede ser que un microservicio puede ser simplemente UNA SOLA FUNCIÓN

2. Que el de desarrollo del componente se pueda realizar en un par de semanas.

3. Que necesite un equipo de desarrolladores pequeño, entres 3 y 6 personas como mucho.

4. El servicio debe ser totalmente independiente, es decir que no dependa de otro servicio para poder realizar su función.

5. Hacer que el despliegue sea sencillo, por ejemplo que uno de nuestros microservicios lance una sentencia mysql unicamente, pues sencillamente pongamos la llamada en
el lugar correspondiente.

6. Hacer que los microservicios se puedan reutilizar al máximo, usando el ejemplo anterior sería hacer que la consulta sirva para cualquier programa que realice esa
consulta, teniendo un servicio que abarca mucho más.

En conclusión los microservicios es la arquitectura SOA llevada al extremo y hacer todo lo más dividido y pequeño posible.

A lo largo del curso tambien se trataron temas sobre el como usar el comando **docker build**, pero en una práctica realizada en Kubernetes ya se empleó dicho comando así como los comandos de **inspect, ps, image,etc...**, pero si DEBO resaltar 2 detalles muy importantes teóricos de los que se hablaron.

* La imagen siguiente corresponde a los pasos que suceden cuando deseamos transforma nuestra aplicación en una aplicación de microservicios.

![ejemplo](/capturas/IntroduccionDocker/Dockerizar.png)

La manera de teórica de hacerlo consta de **3 pasos fundamentales** que son:

1. **Dockerizar nuestro host o servicio**, consiste en hacer lo que corre en una máquina virtual estea dentro de un componente, con esto hace que la instalación de un servicio sea igual, es decir instala todo lo necesario para que corrar, para eso debemos empaquetarlo con una imagen de docker y en vez de hacer un script hacer un "Docker Run" y ya está instalada y corriendo. El principal objetivo de esto es el ayudarnos a instalar un servicio o aplicación de una manera más sencilla omitiendo los posibles problemas que puedan ocurrir como de que 2 personas tienen un sistema operativo diferente cada una y cada uno tiene que instalarlo de una manera diferente al otro, algunas pudiendo ser más complicadas que otras.

2. Una vez Dockeizado nuestro host, lo tendremos todo en un contenedor, por tanto el siguiente paso es **identificar que compone esencialmente el servicio**, en caso del esquema el host se comopone de **Systemd, Ngninx, Python y de Node.js**, una vez identificados procedemos al ultimo paso.

3. **Dividir lo identificado anteriormente en microservicios**, como ultimo paso separaremos ñp ua identificado en **un container para cada uno**, es decir uno para Systemd, uno para Nginx, uno para Python y uno para Node.js, así tendremos el host en 4 contenedores que se pueden actualizar individualmente siendo algo mucho más comodo y práctico, aun sumandole que se pueda llegar a reutilizar cada contenedor en un proyecto diferente.

En la parte práctica de comandos comunes en Docker, estan todos practicamente vistos, tambien mencionan como en el anterior la página de DockerHub, que simplemente es como una "nube" donde podemos subir nuestros contenedores e imágenes, pero para practicar mejor recomienda el que antes de usarlo se comprenda como funciona Docker y en que consiste el mismo, puesto que da comodidad para el programador, pero es mejor que la dea y sepanos que clase de comodidad nos da.

## 26/10/2022
### Finalización del curso de Docker para desarrolladores
Honestamente a efecto práctico en el curso no se aprendió algo distinto a lo enseñado anteriormente bien en el curso de docker para principiantes y en conceptos ya obtenidos en Kubernetes, tales como los **Volum, persitencía de datos y etc...**, pero lo que si resalta algo más es que a diferencia de Kubernetes, Docker dispone de una herramienta llamada Docker Hub que es altamente utilizada (claramente dispone de una version de pago como algunos IDES de programación), permitiendonos hacer cosas de manera más cómoda, por ejemplo dandole solo a un botón poder hacer el comando **docker build con toda la información necesario**.

A pesar de el curso ser útil, en mi opinión es muchisimo mejor empezar por la parte de kubernetes antes (no solo porque lo nombran), si no porque esta más "actualizado" digamos y en mi opinión mejor estructurado.

**El siguiente enlace corresponde al directorio de GitHub empleado para toda practica sobre este curso y me gustaría detallar algo MUY IMPORTANTE, en la carpeta que pone "auto-build" su versión esta OBSOLETA PORQUE YA NO LE DAN SOPORTE A LA VERSION 2.7, a si que si se quiere realizar la prueba bien debemos cambiar la version a las 3.1 o incluso con la 3.0, simplemente por una que al menos tenga soporte**
![linkDeReferencia]( https://github.com/OpenWebinarsNet/docker-for-devs)

Finalmente cabe mencionar que en cuanto a los Networks que porporciona Docker son **Los mismos que en Kubernetes** hasta usan el network Bridge como de predeterminado, lo que si añade a mayores es el concepto teórico acerca de comando "docker-compose" que es como si fuera el comando docker salvo que este se puede encargar de varios contenedores al mismo tiempo, pero ojo **aunque sirva para un solo contenedor no se usa docker-compose si se sabe que trataras con ÚNICAMENTE un contenedor para eso se tiene el comando Docker que se encarga de gestionar un contenedor como se enseñó anteriormente**.
