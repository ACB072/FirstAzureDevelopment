Tema 2: Implement Azure Function

- Preguntas:

  - ¿Qué son las Azure Functions y para qué se utilizan?

    Azure Functions es un servicio proporcionado por Microsoft Azure que se utiliza para desarrollar y ejecutar rápidamente pequeños fragmentos de código llamados "funciones" en respuesta a eventos o desencadenadores específicos (triggers). 

    Las Azure Functions se basan en el concepto de "computación sin servidor", lo que significa que no es necesario aprovisionar ni administrar servidores físicos o virtuales. En cambio, las funciones se ejecutan de forma automática y dinámica a medida que se desencadenan eventos definidos, como cambios en los datos de un almacenamiento en la nube, una solicitud HTTP o una actualización en una cola de mensajes.

    Las Azure Functions se utilizan en una amplia variedad de escenarios, incluyendo procesamiento de eventos en tiempo real, Integraciones y automatizaciones, desarrollo de aplicaciones móviles y web o procesamiento por lotes y Big Data.

    

  - ¿Cuáles son los desencadenadores (triggers) más comunes en Azure Functions?

    Los triggers más comunes son HTTP Trigger, Timer Trigger, Queue Trigger y Blob Trigger, y aunque son particularmente populares debido a su versatilidad, la elección del desencadenador dependerá de los requisitos y necesidades específicas de tu aplicación o proyecto.

    

  - ¿Cómo se configura y se despliega una Azure Function?

​				Creción de una cuenta de Azure Function:

​					-Ve al Portal de Azure y accede con tus credenciales.

​					-Haz clic en "Crear un recurso" en la esquina superior izquierda y busca "Azure Function".

​					-Selecciona "Func App" en los resultados de búsqueda y haz clic en "Crear".

​					-Completa la información requerida, como el nombre de la función, suscripción, grupo de recursos, etc.

​					-Selecciona el tiempo de ejecución, por ejemplo, Azure Functions v3 (.NET Core) o Azure Functions v4 (.NET 6), y el plan de hospedaje.

​					-Haz clic en "Revisar y crear" y, finalmente, en "Crear" para crear la cuenta de Azure Function.

​				Configuración de la función:

​					-Una vez que se haya creado la cuenta de Azure Function, navega hasta ella en el Portal de Azure.

​					-En la sección de Configuración, puedes establecer variables de aplicación, configuraciones de conexión y otras configuraciones específicas de 					la función.

​					-Puedes utilizar la configuración para ajustar el comportamiento de tu función, como cadenas de conexión a bases de datos, configuración de 					tiempo de espera, configuraciones personalizadas, etc.

​				Desarrollo de la función:

​					-Para desarrollar la función, puedes usar el Azure Portal, Visual Studio Code con la extensión de Azure Functions, o cualquier otra 						herramienta compatible.

​					-Crea un nuevo proyecto de función o abre un proyecto existente en tu entorno de desarrollo preferido.

​					-Define tus funciones y lógica de negocio dentro de archivos separados para cada función.

​					-Puedes usar el lenguaje de programación que prefieras, ya sea C#, JavaScript, Python, etc., dependiendo de las opciones de tiempo de 					ejecución que hayas seleccionado al crear la cuenta de Azure Function.

​				Implementación y despliegue de la función:

​					-Antes de implementar, asegúrate de tener las herramientas adecuadas instaladas, como Azure CLI o el SDK de Azure Functions para Visual 					Studio.

​					-Utiliza las herramientas para compilar y empaquetar tu función en un archivo de implementación.

​					-Puedes implementar tu función directamente desde el IDE o utilizar la línea de comandos con los comandos específicos de tu herramienta.

​					-Durante el proceso de implementación, se creará una instancia de la función en tu cuenta de Azure Function y se desplegará el código de tu 					función en ella.

- Identificar y explicar (comprobar si es posible) de la batería de Preguntas 3 preguntas por cada integrante relacionadas con Azure solutions:

  - Pregunta 20 pág 45:

    - La pregunta plantea que se ha desarrollado una aplicación de Azure Function con desencadenador HTTP para procesar datos de blobs de Azure Storage. Sin embargo, la aplicación agota el tiempo después de cuatro minutos que dura la azure function y se necesita asegurar que se puedan procesar los datos antes de que la aplicación agote ese tiempo.

      La solución que plantea la pregunta es configurar la aplicación para usar un plan de hospedaje de App Service y habilitar la opción de "Always On".
  
      La respuesta correcta es la B, No, debido a que no cumple con el objetivo de evitar que la aplicación agote el tiempo. En cambio, se sugiere pasar el desencadenador HTTP a una cola de Azure Service Bus para que sea procesada por una función de desencadenador de cola y retornar una respuesta HTTP de éxito inmediata.
  
  - Pregunta 1 pág 11:
  
    - La pregunta es: ¿Qué debes hacer para corregir el error en la función de la aplicación RequestUserApproval?
  
      La respuesta correcta es: C. Actualizar la función para que sea persistente utilizando Durable Functions para procesar la carga de la solicitud.
  
      El error que se menciona dice que es por excedencia de tiempo de espera de 00:10:00 para la función RequestUserApproval. Para solucionar esto, se debe actualizar la función para que sea persistente y pueda manejar operaciones asíncronas utilizando Durable Functions. Esto permitirá procesar la carga de la solicitud sin superar el límite de tiempo.
  
  - Pregunta 1pág 18:
  
    - La pregunta contiene una serie de imágenes que corresponden a tozos de código, y dicho código debe asegurar que los test de validación se ejecuten y se activen conforme a los requerimientos. Plantea que cuál opciones de las imágenes conseguiría dicho fin.
  
      La respuesta correcta debido a que es la que asegura que funcione acorde a los requerimientos es: 
  
      var event = getEvent();
  
      if (event.eventType === '**RepositoryUpdated**') 
  
      && event.data.target.**service** === 'contentanalysisservice'
  
      && event.**imageCollection**.contains('contosoimages'))
  
      {
  
      ​	startValidationTesting();
  
      }
