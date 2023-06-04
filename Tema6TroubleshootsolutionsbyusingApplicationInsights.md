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

### Preguntas de la bateria:
### QUESTION 1 - Pagina 4

 HOTSPOT You need to configure Azure CDN for the Shipping web site. Which configuration options should you use? To answer, select the appropriate options in the answer area

    Segun los datos del caso practico, el tier de la aplicacion debe ser Standard, el perfil debe ser Akamai y la optimizacion debe ser Dynamic Site Acceleration, ya que incluye varias tecnicas que benefician la latencia y rendimiento del contenido dinamico. Algunos ejemplos para su uso serian los resultados de una busqueda, transacciones de venta, o datos a tiempo real. Ademas, permite seguir usando el cache del CDN para los datos estaticos

### QUESTION 6 - Pagina 88

DRAG DROP Your company has several websites that use a company logo image. You use Azure Content Delivery Network (CDN) to store the static image. You need to determine the correct process of how the CDN and the Point of Presence (POP) server will distribute the image and list the items in the correct order. In which order do the actions occur? To answer, move all actions from the list of actions to the answer area and arrange them in the correct order.

    La solucion consistiria en 4 pasos:
    
    Paso 1: Un usuario solicita un archivo ( mediante una URL con un nombre de dominio especial, como <endpoint name>.azureedge.net. Este nombre puede ser un nombre de host de punto final o un dominio personalizado. El DNS enruta la solicitud a la ubicación POP con mejor rendimiento, que suele ser el POP más cercano geográficamente al usuario.
    
    Paso 2: Si ningún servidor perimetral en el POP tiene el archivo en su caché, el POP solicita el archivo al servidor de origen.
    El servidor de origen puede ser una aplicación web de Azure, un servicio en la nube de Azure, una cuenta de almacenamiento de Azure o cualquier servidor web accesible.
    
    Paso 3: Un servidor perimetral en el POP almacena en caché el archivo y lo devuelve al solicitante original (Alice). El archivo permanece en caché en el servidor perimetral en el POP hasta el tiempo de vida (TTL) especificado por sus encabezados HTTP caduca. Si el servidor de origen no especificó un TTL, el TTL predeterminado es de siete días.
    
    Paso 4: Los usuarios adicionales pueden solicitar el mismo archivo usando la misma URL que usó el usuario original y pueden también se dirigirá al mismo POP.
    
    Si el TTL del archivo no ha caducado, el servidor perimetral POP devuelve el archivo directamente desde la memoria caché. Este
    El proceso da como resultado una experiencia de usuario más rápida y receptiva.


### QUESTION 8  - Pagina 199

HOTSPOT 

You are developing an Azure App Service hosted ASP.NET Core web app to deliver video-on-demand streaming media. You enable an Azure Content Delivery Network (CDN) Standard for the web endpoint. Customer videos are downloaded from the web app by using the following example URL: http:// www.contoso.com/content.mp4?quality=1 All media content must expire from the cache after one hour. Customer videos with varying quality must be delivered to the closest regional point of presence (POP) node. You need to configure Azure CDN caching rules. Which options should you use? To answer, select the appropriate options in the answer area. NOTE: Each correct selection is worth one point.

    Para asegurarnos que la pagina web escala automaticamente cuando la carga de la CPU esta alrededor del 85%,, debemos configurar la web app con el servicio Standar App Service Tier, ya que soporta el autoescalado y minimiza los costes. Mas adelante activamos el autoescalado dentro de la web app, añadimos la regla y la condicion para cuando sobrepase al 85%.



