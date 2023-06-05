## Tema 5:  Implement Azure App Service Web Apps - Mohamed A.

### Preguntas
  - ¿Cuáles son las características principales de Azure App Service?	
        
        Azure App Service es una plataforma de alojamiento en la nube que permite a los desarrolladores desplegar y gestionar aplicaciones web de manera sencilla. Proporciona características como escalabilidad automática, integración con otros servicios de Azure y soporte multiplataforma, lo que facilita la creación y el despliegue de aplicaciones web altamente escalables y robustas. Con App Service, los desarrolladores pueden centrarse en la lógica de su aplicación sin preocuparse por la infraestructura subyacente, lo que les permite ahorrar tiempo y esfuerzo en la gestión de servidores y recursos.
  - ¿Cómo se configura y escala una aplicación web en Azure App Service?	
        
        Para configurar y escalar una aplicación web en Azure App Service, primero debes crear una instancia de App Service en el portal de Azure. Luego, puedes subir tu código fuente o utilizar una plantilla predefinida para configurar tu aplicación. Puedes establecer la configuración de la aplicación, como las variables de entorno y las conexiones a bases de datos. Para escalar, puedes utilizar la opción de escala automática para ajustar automáticamente la capacidad de la aplicación según la carga de tráfico, o puedes optar por la escala manual y ajustar la cantidad de instancias según tus necesidades. Con estas configuraciones y escalabilidad flexibles, puedes asegurarte de que tu aplicación web en Azure App Service pueda satisfacer la demanda de los usuarios de manera eficiente.
  - ¿Qué es un plan de App Service y cómo se relaciona con las aplicaciones web?	

        Un plan de App Service en Azure es una opción de suscripción que determina los recursos y características disponibles para alojar y ejecutar aplicaciones web en Azure App Service. Un plan de App Service define la cantidad de potencia de procesamiento, memoria y almacenamiento asignada a tus aplicaciones web. Puedes seleccionar diferentes niveles de planes, como Free, Shared, Basic, Standard y Premium, dependiendo de tus necesidades y presupuesto. Cada plan de App Service puede alojar una o más aplicaciones web, lo que te permite agrupar y gestionar varias aplicaciones juntas, compartiendo los mismos recursos y configuraciones. Al elegir el plan de App Service adecuado, puedes asegurarte de que tus aplicaciones web tengan los recursos necesarios para funcionar de manera eficiente y escalable en Azure.

### Identificar y explicar (comprobar si es posible) de la batería de Preguntas 3 preguntas por cada integrante relacionadas con Azure App Service:
- QUESTION 1 page 191

You are developing and deploying several ASP.NET web applications to Azure App Service. You plan to save session state information and HTML output.

You must use a storage mechanism with the following requirements:

- Share session state across all ASP.NET web applications.
- Support controlled, concurrent access to the same session state data for multiple readers and a single writer.
- Save full HTTP responses for concurrent requests.

You need to store the information.

Proposed Solution: Deploy and configure Azure Cache for Redis. Update the web applications.

Does the solution meet the goal?

A. Yes 

B. No

Correct Answer: A

Explicación:
   
    La solución propuesta cumple con los requisitos establecidos. Azure Cache for Redis proporciona un almacenamiento en caché de alto rendimiento y escalable que puede compartirse entre múltiples aplicaciones web. Permite el acceso concurrente controlado para lecturas y una sola escritura en los datos de estado de sesión. Además, puede guardar respuestas HTTP completas para solicitudes concurrentes, lo que satisface todos los requisitos mencionados en la pregunta.

- QUESTION 3 page 194

You plan to deploy a web app to App Service on Linux. You create an App Service plan. You create and push a custom Docker image that contains the web app to Azure Container Registry.
You need to access the console logs generated from inside the container in real-time.
How should you complete the Azure CLI command? To answer, select the appropriate options in the answer area.

Explicación:

      Recuadro 1: config
      Para configurar el registro de eventos para una aplicación web, utiliza el comando: az webapp log config

      Recuadro 2: --docker-container-logging
      La sintaxis incluye:
      az webapp log config [--docker-container-logging {filesystem, off}]

      Recuadro 3: webapp
      Para descargar el historial de registros de una aplicación web como un archivo zip, utiliza el comando: az webapp log download

      Recuadro 4: download


- QUESTION 8 page 199

You are developing an Azure App Service hosted ASP.NET Core web app to deliver video-on-demand streaming media. You enable an Azure Content Delivery Network (CDN) Standard for the web endpoint. Customer videos are downloaded from the web app by using the following example URL: http:// www.contoso.com/content.mp4?quality=1
All media content must expire from the cache after one hour. Customer videos with varying quality must be delivered to the closest regional point of presence (POP) node.
You need to configure Azure CDN caching rules.
Which options should you use? To answer, select the appropriate options in the answer area.

Explicación:
      
      Recuadro 1: Override
      Sobrescribir: Ignora la duración de caché proporcionada por el origen; en su lugar, utiliza la duración de caché proporcionada. Esto no sobrescribirá cache-control: no-cache.
      Establecer si falta: Respeta las cabeceras de directiva de caché proporcionadas por el origen, si existen; de lo contrario, utiliza la duración de caché proporcionada.

      Recuadro 2: 1 hora
      Todo el contenido multimedia debe expirar en la caché después de una hora.

      Recuadro 3: Cachear cada URL única
      Cachear cada URL única: En este modo, cada solicitud con una URL única, incluyendo la cadena de consulta, se trata como un recurso único con su propia caché. Por ejemplo, la respuesta del servidor de origen para una solicitud de ejemplo.ashx?q=test1 se almacena en la ubicación de caché y se devuelve para cachés posteriores con la misma cadena de consulta. Una solicitud de ejemplo.ashx?q=test2 se almacena en caché como un recurso separado con su propia configuración de tiempo de vida.