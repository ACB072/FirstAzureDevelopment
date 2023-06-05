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



### Preguntas de la bateria:
### QUESTION 4 - Pagina 195
You develop and deploy an ASP.NET web app to Azure App Service. You use Application Insights
telemetry to monitor the app.
You must test the app to ensure that the app is available and responsive from various points around the
world and at regular intervals. If the app is not responding, you must send an alert to support staff.
You need to configure a test for the web app.
Which two test types can you use? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.
A. integration
B. multi-step web
C. URL ping
D. unit
E. load

    La respuesta seria B y C, dado que existen 3 tipos de de test de avalabilidad.
    - URL ping test: Que utiliza una peticion avanzada HTTP para validar que un punto final esta respondiendo, midiendo el rendimiento asociado con la respuesta. Se puede crear a traves de el portal de azure dentro de un recurso de Application Insights.
    - Multi-step web test: Este tipo de test ha sido descatalogado en las ultimas versiones de Azure, pero servia para monitorear una secuencia URL grabada y las interacciones dentro de la web a traves de varios pequeños tests. Depende principalmente de archivos de prueba en Visual Studio.
    - Custom Track Availability Tests: Este tipo de test se recomienda a manera de sustitución del Multi-step web test, ayuda a monitorear una pagina web y ademas es mas comodo a la hora de crear los tests, ya que envia directamente la informacion de disponibilidad de una aplicación.

### QUESTION 6 - Pagina 197
You are developing an ASP.NET Core Web API web service. The web service uses Azure Application
Insights for all telemetry and dependency tracking. The web service reads and writes data to a database
other than Microsoft SQL Server.
You need to ensure that dependency tracking works for calls to the third-party database.
Which two dependency telemetry properties should you use? Each correct answer presents part of the
solution.
NOTE: Each correct selection is worth one point.
A. Telemetry.Context.Cloud.RoleInstance
B. Telemetry.Id
C. Telemetry.Name
D. Telemetry.Context.Operation.Id
E. Telemetry.Context.Session.Id

    La respuesta seria B y D, ya que cada elemento de telemetría de solicitud tiene su propia identificación que lo identifica de manera única y global. Y todos los elementos de telemetría (como seguimientos y excepciones) que están asociados con la solicitud deben establecer la operación_parentId al valor de la identificación de la solicitud

### QUESTION 14 - Pagina 207
DRAG DROP
You develop an ASP.NET Core MVC application. You configure the application to track webpages and
custom events.
You need to identify trends in application usage.
Which Azure Application Insights Usage Analysis features should you use? To answer, drag the appropriate
features to the correct requirements. Each feature may be used once, more than once, or not at all. You
may need to drag the split bar between panes or scroll to view content.

	Las respuestas serian:
	1- Users: Con lo que podremos conocer quien entra y sale de nuestra aplicación y  qué páginas les interesan más, dónde se encuentran sus usuarios y qué navegadores y sistemas operativos usan
	
	2- Impact: Analiza cómo los tiempos de carga y otras propiedades influyen en las tasas de conversión para varias partes de la aplicación, siendo más preciso, descubre cómo cualquier dimensión de una webview, un evento personalizado o una solicitud afecta el uso de una webview diferente o un evento personalizado.
	
	3- Retención: Ayuda a analizar cuántos usuarios regresan a la aplicación y con qué frecuencia realizan tareas específicas o logran objetivos. Por ejemplo, si ejecuta un sitio de juegos, podría comparar el número de usuarios que regresan al sitio después de perder un juego con el número de los que regresan después de ganar.
	
	4- User Flows: Visualiza como los usuarios navegan entre las distintas páginas y caracteristicas de la aplicacion, como donde los usuarios suelen dar click dentro de la pagina, como salen de ellas, cual es el sitio donde los usuarios han repetido varias veces la misma acción....

