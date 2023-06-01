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

## Tema 6: Troubleshoot solutions by using Application Insights - Antonio Miralles Gutiérrez
## Preguntas:
**- ¿Qué es Azure Application Insights y cómo se utiliza para el monitoreo de aplicaciones?**

	Application Insights es una extensión de Azure Monitor y proporciona características de APM. Las herramientas de APM son útiles para supervisar aplicaciones de desarrollo, pruebas y producción de las siguientes maneras:
	
	- De manera proactiva comprende cómo funciona una aplicación.
	- De manera reactiva revisa los datos de ejecución de la aplicación para determinar la causa de un incidente.
	
	La manera más fácil de empezar a consumir Application Insights es mediante Azure Portal y las experiencias visuales integradas. Los usuarios avanzados pueden consultar los datos subyacentes directamente para crear visualizaciones personalizadas mediante paneles y libros de Azure Monitor.
	
	Considere la posibilidad de empezar con el mapa de aplicación para obtener una vista general. Use la experiencia de búsqueda para restringir rápidamente la telemetría y los datos por tipo y fecha y hora. También puede buscar en los datos (por ejemplo, con seguimientos de registro) y filtrar por una operación correlacionada determinada de interés.
	
	Hay dos vistas que son especialmente útiles:
	
	Vista de rendimiento: obtenga información detallada sobre el rendimiento de la aplicación o la API y las dependencias de bajada. También puede encontrar un ejemplo representativo para explorar de un extremo a otro.
	Vista de error: comprenda qué componentes o acciones generan errores, y errores y excepciones de prioridad. Las vistas integradas son útiles para realizar un seguimiento del estado de la aplicación de forma proactiva y para el análisis reactivo de la causa principal.
	Cree alertas de Azure Monitor para indicar posibles problemas si las partes de la aplicación o los componentes se desvían de la línea de base establecida.

**- ¿Cuáles son las principales características y beneficios de Application Insights?**

**Configuración de Application Insights para las aplicaciones de could service**

    En Visual Studio Explorador de soluciones, en Roles de servicio> en la nube, abra las propiedades de cada rol.
    En Configuración, active la casilla Enviar datos de diagnóstico a Application Insights y, a continuación, seleccione la instancia de Application Insights que creó antes.
    En el caso de los roles web, esta opción proporciona supervisión del rendimiento, alertas, diagnósticos y análisis de uso. Para otros roles, puede buscar y supervisar Azure Diagnostics, como los contadores de reinicio y rendimiento.

**Diagnóstico de errores en Application Insights**

    Application Insights incluye una experiencia de administración del rendimiento de aplicaciones curada para ayudar a diagnosticar errores en las aplicaciones supervisadas. Para ver los errores en la Azure Portal, vaya a la instancia de Application Insights y, a continuación, seleccione Errores en Investigar.
    Verá las tendencias de tasa de errores de las solicitudes, cuántos de ellos producen errores y cuántos usuarios se ven afectados. En la tablade operaciones con error 1 se muestran las solicitudes con errores agrupadas por la dirección URL de la solicitud. En la vista general2, verá los tres primeros códigos de respuesta, los tres tipos de excepción principales y los tres tipos de dependencia con errores principales.
    
    Para revisar ejemplos representativos de cada uno de estos subconjuntos de operaciones, seleccione el vínculo correspondiente. Por ejemplo, para diagnosticar excepciones, puede seleccionar el recuento de una excepción determinada que se va a presentar con la pestaña Detalles de transacción de un extremo a otro .
    La siguiente información de los detalles de la transacción de un extremo a otro es útil para solucionar problemas:
    
    Marca de tiempo de la solicitud
        -El código de respuesta
        -Tiempo de respuesta
        -Mensaje de excepción
        -Tipo de excepción
        -Pila de llamadas
        
**Diagnóstico de problemas de rendimiento en Application Insights**
    Para diagnosticar problemas de rendimiento del rol web, podemos comprobar los siguientes datos en la página Rendimiento de la instancia de Application Insights:

    El rol web solicita el tiempo de respuesta
    CPU, memoria, E/S de disco, E/S de red de instancia de rol web
    En la pestaña Operaciones , la tabla1 de operaciones con errores muestra el nombre de la operación de solicitud, la duración y el resumen del recuento de solicitudes. Seleccione una operación y actualizará el gráfico de métricas2 para mostrar el volumen de solicitudes y el gráfico de métricas de duración.

    La pestaña Roles muestra los datos de métricas más relacionados con el servidor de Cloud Service, como cpu, memoria disponible, las solicitudes controladas por cada instancia, etc.

**Alerta en Application Insights**

    La alerta permite a los usuarios establecer reglas personalizadas para supervisar el estado de la instancia del rol de servicio en la nube. Cuando se produce el evento supervisado, los usuarios pueden recibir una notificación por correo electrónico.

  1-Las reglas contienen principalmente dos partes importantes: condiciones y acciones. Para crear una alerta, siga estos pasos:

  2-En el Azure Portal, vaya a la instancia de Application Insights y seleccione Alerta en la sección Supervisión. En esta página, puede ver todas las alertas desencadenadas. Expanda + Crear y, a continuación, seleccione Regla de alertas.

  3-Configure las condiciones. La condición consta de tres puntos: Signal, Dimension y Alert Logic. Para más información, consulte Tipos de alertas de Azure Monitor.

  4-Establezca la acción cuando se desencadene la regla de alerta. Puede crear un nuevo grupo de acciones y agregarlo a esta regla de alertas o usar un grupo de acciones existente.

    En la página Detalles , seleccione la suscripción y el grupo de recursos en los que guardar la regla de alerta y establezca su nombre y nivel de gravedad.

**- ¿Cómo se configura y se utiliza Application Insights para el diagnóstico y solución de problemas en una aplicación?**

    Cuando Application Insights está habilitado en Cloud Service, la configuración de diagnóstico debe habilitarse al mismo tiempo. Algunos datos y registros de métricas recopilados por la configuración de diagnóstico se enviarán a Application Insights.

    Para el rol web, hay nueve métricas que tienen datos que se recopilarán automáticamente incluso si el contador de rendimiento está deshabilitado en la configuración de diagnóstico. Los datos de estas nueve métricas se guardan en la tabla performanceCounter de Application Insights. Otras métricas, como \Process(w3wp)\% Processor Time, se guardarán en la tabla customMetrics cuando el contador de rendimiento esté habilitado.

    Para el rol de trabajo, si el contador de rendimiento está deshabilitado en la configuración diagnóstico, no habrá datos de métricas de rendimiento recopilados y guardados automáticamente en Application Insights.

    Para ambos, los datos de métricas de HeartBeatState siempre se guardan automáticamente en Application Insights. Esta métrica se usa para identificar si la instancia sigue en buen estado en el nivel de servidor. Se desencadenará cada 15 minutos y se guardará en la tabla customMetrics . Los demás datos de métricas de rendimiento deben habilitarse manualmente en el contador de rendimiento en configuración de diagnóstico.
