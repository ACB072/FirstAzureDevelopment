Tema 2: Implement Azure Function

- Preguntas:

  - ¿Qué son las Azure Functions y para qué se utilizan?

    Azure Functions es un servicio proporcionado por Microsoft Azure que se utiliza para desarrollar y ejecutar rápidamente pequeños fragmentos de código llamados "funciones" en respuesta a eventos o desencadenadores específicos (triggers). 

    Las Azure Functions se basan en el concepto de "computación sin servidor", lo que significa que no es necesario aprovisionar ni administrar servidores físicos o virtuales. En cambio, las funciones se ejecutan de forma automática y dinámica a medida que se desencadenan eventos definidos, como cambios en los datos de un almacenamiento en la nube, una solicitud HTTP o una actualización en una cola de mensajes.

    Las Azure Functions se utilizan en una amplia variedad de escenarios, incluyendo procesamiento de eventos en tiempo real, Integraciones y automatizaciones, desarrollo de aplicaciones móviles y web o procesamiento por lotes y Big Data.

    

  - ¿Cuáles son los desencadenadores (triggers) más comunes en Azure Functions?

    Los triggers más comunes son HTTP Trigger, Timer Trigger, Queue Trigger y Blob Trigger, y aunque son particularmente populares debido a su versatilidad, la elección del desencadenador dependerá de los requisitos y necesidades específicas de tu aplicación o proyecto.

    

  - ¿Cómo se configura y se despliega una Azure Function?

Creción de una cuenta de Azure Function:

-Ve al Portal de Azure y accede con tus credenciales.

-Haz clic en "Crear un recurso" en la esquina superior izquierda y busca "Azure Function".

-Selecciona "Func App" en los resultados de búsqueda y haz clic en "Crear".

-Completa la información requerida, como el nombre de la función, suscripción, grupo de recursos, etc.

-Selecciona el tiempo de ejecución, por ejemplo, Azure Functions v3 (.NET Core) o Azure Functions v4 (.NET 6), y el plan de hospedaje.

-Haz clic en "Revisar y crear" y, finalmente, en "Crear" para crear la cuenta de Azure Function.

Configuración de la función:

-Una vez que se haya creado la cuenta de Azure Function, navega hasta ella en el Portal de Azure.

-En la sección de Configuración, puedes establecer variables de aplicación, configuraciones de conexión y otras configuraciones específicas de la función.

-Puedes utilizar la configuración para ajustar el comportamiento de tu función, como cadenas de conexión a bases de datos, configuración de tiempo de espera, configuraciones personalizadas, etc.

Desarrollo de la función:

-Para desarrollar la función, puedes usar el Azure Portal, Visual Studio Code con la extensión de Azure Functions, o cualquier otra herramienta compatible.

-Crea un nuevo proyecto de función o abre un proyecto existente en tu entorno de desarrollo preferido.

-Define tus funciones y lógica de negocio dentro de archivos separados para cada función.

-Puedes usar el lenguaje de programación que prefieras, ya sea C#, JavaScript, Python, etc., dependiendo de las opciones de tiempo de ejecución que hayas seleccionado al crear la cuenta de Azure Function.

Implementación y despliegue de la función:

-Antes de implementar, asegúrate de tener las herramientas adecuadas instaladas, como Azure CLI o el SDK de Azure Functions para Visual Studio.

-Utiliza las herramientas para compilar y empaquetar tu función en un archivo de implementación.

-Puedes implementar tu función directamente desde el IDE o utilizar la línea de comandos con los comandos específicos de tu herramienta.

-Durante el proceso de implementación, se creará una instancia de la función en tu cuenta de Azure Function y se desplegará el código de tu función en ella.

- Identificar y explicar (comprobar si es posible) de la batería de Preguntas 3 preguntas por cada integrante relacionadas con Azure solutions:

  - Pregunta pág :

  - Pregunta pág :

  - Pregunta pág :
