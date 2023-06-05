## Tema 3: Implement user authentication and authorization - Mohamed A.
###  Preguntas:
  - ¿Qué es la Plataforma de Identidad de Microsoft y cómo se utiliza para la autenticación de usuarios?
            
         La Plataforma de Identidad de Microsoft es un conjunto de herramientas y servicios que te ayuda a controlar quién tiene acceso a tus aplicaciones y servicios en la nube de Microsoft Azure. 
        Cuando un usuario intenta acceder a una aplicación o servicio protegido, se le solicitará que proporcione sus credenciales de Microsoft, como su dirección de correo electrónico y contraseña. Estas credenciales son verificadas por la plataforma de identidad para asegurarse de que el usuario es quien dice ser. Si las credenciales son válidas, el usuario obtiene acceso a la aplicación o servicio. La plataforma de identidad también puede ofrecer opciones adicionales de autenticación, como el uso de autenticación de dos factores para una mayor seguridad.

  - ¿Cuál es el flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft?

        El flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft se llama "flujo de autorización de código". En este flujo, cuando un usuario intenta acceder a una aplicación protegida, se le redirige a la página de inicio de sesión de Microsoft. Allí, el usuario ingresa sus credenciales de Microsoft (como su dirección de correo electrónico y contraseña). Después de verificar las credenciales, se genera un código de autorización y se envía de vuelta a la aplicación. Luego, la aplicación intercambia este código por un token de acceso, que permite al usuario acceder a los recursos protegidos dentro de la aplicación. Este flujo de autenticación garantiza que solo los usuarios autorizados puedan acceder a las aplicaciones en Azure.

  - ¿Cómo se obtienen y se utilizan los tokens de acceso para autorizar solicitudes a recursos protegidos?
            
        Los tokens de acceso se obtienen mediante la autenticación exitosa del usuario y se utilizan para autorizar las solicitudes a los recursos protegidos. Estos tokens aseguran que solo los usuarios autenticados y autorizados puedan acceder a los recursos en Azure.

### Identificar y explicar (comprobar si es posible) de la batería de Preguntas 3 preguntas por cada integrante relacionadas con Azure Autenticación y Autorización:
- QUESTION 18 page 157:

You provide an Azure API Management managed web service to clients. The back-end web service implements HTTP Strict Transport Security (HSTS).
Every request to the backend service must include a valid HTTP authorization header. You need to configure the Azure API Management instance with an authentication policy. Which two policies can you use? Each correct answer presents a complete solution. NOTE: Each correct selection is worth one point.

A. Basic Authentication

B. Digest Authentication

C. Certificate Authentication

D. OAuth Client Credential Grant

Correct Answer: CD 


Explicación:

      La pregunta plantea la necesidad de configurar una política de autenticación en una instancia de Azure API Management que consume un servicio web backend que implementa HTTP Strict Transport Security (HSTS) y requiere un encabezado de autorización HTTP válido en cada solicitud. Las dos opciones correctas para configurar la política de autenticación son:
      C. Autenticación mediante certificado: Permite la autenticación basada en certificados para verificar la identidad del cliente.
      D. Concesión de credenciales de cliente OAuth: Permite la autenticación mediante OAuth, utilizando un token de acceso válido y un secreto de cliente para verificar la identidad del cliente.
      Estas dos políticas proporcionan una solución completa para autenticar las solicitudes al servicio backend a través de Azure API Management.
- QUESTION 26 page 166:

Your company is developing an Azure API hosted in Azure.
You need to implement authentication for the Azure API to access other Azure resources. You have the following requirements:
All API calls must be authenticated.
Callers to the API must not send credentials to the API.
Which authentication mechanism should you use?

A. Basic

B. Anonymous

C. Managed identity 

D. Client certificate

Correct Answer: C 

Explicación:

    La pregunta plantea la necesidad de implementar autenticación para un API de Azure que accede a otros recursos de Azure. Los requisitos son que todas las llamadas al API deben estar autenticadas y los llamadores al API no deben enviar credenciales al API.

    La opción correcta es C. Managed identity.


- QUESTION 2 page 223

You need to insert code at line LE03 of LoginEvent.cs to ensure that all authentication events are processed correctly.

![image](/screen1.png)

 Correct Answer: 

 ![image](/screen2.png)

Explicación:

    Recuadro 1: id
    id es un identificador único para el evento.

    Recuadro 2: eventType
    eventType es uno de los tipos de eventos registrados para esta fuente de eventos.

    Recuadro 3: dataVersion
    dataVersion es la versión de esquema del objeto de datos. El editor define la versión de esquema.

    Los eventos de autenticación se utilizan para monitorear el inicio y cierre de sesión de los usuarios. Todos los eventos de autenticación deben ser procesados por el servicio de políticas. Los cierres de sesión deben ser procesados lo más rápido posible.
