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
- QUESTION 18 page 157
- QUESTION 26 page 166 
- QUESTION 2 page 223
