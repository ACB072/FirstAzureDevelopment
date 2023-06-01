# FirstAzureDevelopment
>
> ## Antonio Miralles Gutiérrez
>
> ## Mohamed Amri
> 
> ## Miguel Aparicio

## Tema 1: Azure CDN (Content Delivery Network) - Antonio Miralles Gutiérrez
## Preguntas:
**- ¿Qué es Azure CDN y cuál es su propósito en el despliegue de aplicaciones web?**
	
	Azure Content Delivery Network es una red distribuida de servidores que puede proporcionar contenido web a los usuarios. Este tipo de red guarda el contenido en caché  de los servidores perimetrales en ubicaciones POP que estan cerca de los usuarios finales.
	
	Azure CDN ofrece a los desarrolladores una solución global para la entrega rápida de contenido con alto ancho de banda a los usuarios mediante el almacenamiento en caché del contenido en nodos físicos estratégicamente situados en todo el mundo. Azure CDN también puede acelerar el contenido dinámico, que no se puede almacenar en caché, mediante varias optimizaciones de red con POP de CDN. Por ejemplo, la optimización de rutas para omitir el protocolo de puerta de enlace de borde (BGP).
	Entre las ventajas de usar Azure CDN para entregar los recursos de un sitio web se incluyen:
	
	- Mayor rendimiento y experiencia para los usuarios finales, especialmente cuando se utilizan aplicaciones en las que los usuarios finales necesitan varias solicitudes de recorridos de ida y vuelta para cargar contenidos.
	- Gran escalado para mejorar la administración de cargas instantáneas pesadas, por ejemplo, al comienzo de un evento de lanzamiento de un producto.
	- Distribución de las solicitudes de usuario y entrega del contenido directamente desde los servidores perimetrales, de forma que se envía menos tráfico al servidor de origen.

**- ¿Cuáles son los beneficios de utilizar Azure CDN en términos de rendimiento y escalabilidad?**

	Azure CDN realiza un metodo sencillo y eficaz de compresion de archivos para mejorar la velocidad de transferencia y aumentar el rendimiento de la carga de páginas web, ya que se reduce el tamaño del archivo antes de enviarlo desde el servidor, reduciendo los costes de ancho de banda y proporciona una mayor capacidad de respuesta para los usuarios

**- ¿Cómo se configura y se utiliza Azure CDN para acelerar la entrega de contenido estático y dinámico en una aplicación web?**

	La funcionalidad estándar de la red de entrega de contenido (CDN) incluye la posibilidad de almacenar en caché los archivos más cerca de los usuarios finales para acelerar la entrega de archivos estáticos. Pero con las aplicaciones web dinámicas, no es posible almacenar en caché ese contenido en ubicaciones perimetrales, porque el servidor genera el contenido en respuesta al comportamiento del usuario. Acelerar la entrega de este tipo de contenido es más complejo que el almacenamiento en caché perimetral tradicional y requiere una solución integral en la que se ajusten con precisión todos los elementos de toda la ruta de datos, desde el comienzo hasta la entrega. Con la optimización de sitios dinámicos (DSA) de Azure CDN, el rendimiento de las páginas web con contenido dinámico se ha mejorado de un modo contrastable.

Para configurar un punto de conexión de CDN para la optimización de DSA mediante Azure Portal:

	1- En la página Perfil de CDN, seleccione Punto de conexión.
	Aparecerá el panel Agregar un punto de conexión.
	
	2- En Optimized for (Optimizado para), seleccione Aceleración de sitios dinámicos.
	
	3- En Ruta de acceso de sondeo, escriba una ruta de acceso válida a un archivo.
	
	4- La ruta de acceso de sondeo es una característica específica de DSA y se necesita una ruta de acceso válida para la creación. DSA usa un pequeño archivo de ruta de acceso de sondeo en el servidor de origen para optimizar las configuraciones de enrutamiento de red para la red CDN. Para el archivo de ruta de acceso de sondeo, puede descargar y cargar el archivo de ejemplo en su sitio, o usar un recurso existente en el origen que tenga un tamaño de unos 10 KB.
	
	5- Escriba las demás opciones de punto de conexión necesarias (para más información, consulte Crear un nuevo punto de conexión de CDN) y luego haga clic en Agregar.
	
	6- Una vez creado el punto de conexión de CDN, las optimizaciones de DSA se aplican a todos los archivos que coincidan con determinados criterios.
