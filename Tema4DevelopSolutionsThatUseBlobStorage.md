Tema 4: Develop solutions that use blob storage

- Preguntas:

  - ¿Qué es Azure Blob storage y cómo se utiliza para almacenar datos no estructurados?

    Azure Blob storage es un servicio de almacenamiento en la nube ofrecido por Microsoft Azure. Se utiliza para almacenar grandes cantidades de datos no estructurados, es decir, cualquier archivo que no precise de un esquema o una estructura rígida ( como puede ser JSON). Esto permite guardar y acceder a datos de cualquier tipo sin la necesidad de definir una estructura de tabla o esquema previo.

  - ¿Cuáles son los tipos de blobs que se pueden almacenar en Azure Blob storage?

    Blobs de bloque (archivos de texto, videos, imagenes, documentos, etc), Blobs de página (discos virtuales), Blobs de apéndice, Blobs en frío (para almacenar datos que se visitan con baja frecuencia) y Blobs en caliente (para almacenar datos que se visitan con alta frecuencia)

  - ¿Cómo se accede y se administra el almacenamiento de blobs en Azure?

​				Portal de Azure:

​					-El Portal de Azure proporciona una interfaz gráfica para administrar y acceder al almacenamiento de blobs.

​					-Puedes crear y configurar cuentas de almacenamiento, contenedores de blobs y establecer permisos de acceso a través del portal.

​					-Además, puedes ver, descargar y cargar blobs, así como realizar operaciones básicas de administración.

​				Azure Storage Explorer:

​					-Azure Storage Explorer es una aplicación de escritorio que te permite administrar y trabajar con el almacenamiento de blobs y otros servicios 					de almacenamiento de Azure de forma fácil e intuitiva.

​					-Puedes explorar tus cuentas de almacenamiento, navegar por los contenedores de blobs, ver, descargar, cargar y eliminar blobs, y 					administrar las propiedades y permisos de los blobs.

​				Azure CLI:

​					-Azure CLI (Command-Line Interface) es una herramienta de línea de comandos que te permite interactuar con Azure y administrar recursos, 					incluido el almacenamiento de blobs.

​					-Puedes usar comandos específicos de Azure CLI para crear y configurar cuentas de almacenamiento, contenedores de blobs, y realizar 					operaciones como subir, descargar y eliminar blobs.

​					-La Azure CLI ofrece una interfaz de línea de comandos poderosa y flexible para automatizar tareas y operaciones de administración.

​				SDK y API de Azure:

​					-Los SDK de Azure y las API proporcionan bibliotecas de desarrollo y conjuntos de funciones para interactuar con el almacenamiento de blobs 					en Azure.

​					-Puedes utilizar los SDK y las API en tu aplicación para realizar operaciones como subir, descargar, eliminar y administrar blobs.

​					-Los SDK están disponibles para varios lenguajes de programación, como .NET, Java, Python, Node.js, entre otros.

- Identificar y explicar (comprobar si es posible) de la batería de Preguntas 3 preguntas por cada integrante relacionadas con Azure solutions:

  - Pregunta 30 pág 55:

    - El caso que se plantea es que estás creando una aplicación que utiliza Azure Blob storage, que es un servicio en la nube para almacenar grandes cantidades de datos no estructurados, como imágenes, videos o documentos. Has configurado Azure Blob storage para incluir "change feeds", que son registros de los cambios que ocurren en tus datos.

      Ahora necesitas crear una copia de tu cuenta de almacenamiento en otra región. Esto implica duplicar todos tus datos y configuraciones en otro servidor en una ubicación geográfica diferente. La razón para esto podría ser tener recursos para proteger tus datos en caso de problemas en una región específica.
  
      Para copiar los datos de tu cuenta de almacenamiento actual a la nueva cuenta en la otra región, se realizará una transferencia directa entre los servidores de almacenamiento, sin tener que descargar los datos a tu propia máquina y volver a subirlos. Esto permite una transferencia más rápida y eficiente de los datos. Pregunta que en que orden se deben realizar la lista de acciones que plantea en la imagen.
  
      El orden lógico para copiar los datos es: copiar una nueva plantilla de copia, exportar una plantilla de administración de recursos, modificar en esa plantilla el nombre de la cuenta de almacenamiento y la región, hacer un deploy para que se genere la cuenta de almacenamiento en la nueva región y usar el comando AZ Copy para compiarlo todo. De esta manera nos hemos ahorrado descargarlo todo en local y tener que subirlo de nuevo.
  
  - Pregunta 34 pág 60:
  
    - En esta pregunta te están presentando un escenario en el cual estás desarrollando una oferta de software como servicio (SaaS) para gestionar fotografías. Los usuarios cargan fotos a un servicio web que luego almacena las fotos en Azure Storage Blob storage. El tipo de cuenta de almacenamiento utilizado es General-purpose V2.
  
      Cuando se cargan las fotos, deben ser procesadas para crear y guardar una versión compatible con dispositivos móviles de la imagen. El proceso para generar una versión compatible con dispositivos móviles de la imagen debe iniciarse en menos de un minuto.
  
      La pregunta te pide que diseñes el proceso que inicia el procesamiento de las fotos. La solución propuesta es crear una aplicación de Azure Function que utilice el modelo de hospedaje de Consumo y que se active cuando se cargue un blob en el almacenamiento.
  
      La respuesta correcta es A: Sí. Esta solución cumple con el objetivo establecido, ya que utilizando Azure Functions en el modelo de hospedaje de Consumo, los recursos se agregan dinámicamente según sea necesario por las funciones. Esto significa que el proceso de procesamiento de las fotos se iniciará de manera automática cuando se cargue un blob en el almacenamiento, y comenzará en menos de un minuto, tal como se requiere.
  
  - Pregunta 1 pág 70:
  
    -  La pregunta nos pide configurar las opciones de "Tipo de cuenta", "Replicación" y "Nivel de almacenamiento" para la cuenta de almacenamiento de Azure del sitio web corporativo. La respuesta correcta es Storage V2, ya que es un tipo de cuenta de almacenamiento muy versatil para almacenar blobs, archivos, colas y tablas; Geo-redundant Storage, que proporciona una mayor disponibilidad y protección de los datos en caso de fallas o desastres; y por último Cool paraminimizar los costos de almacenamiento de datos.
  

