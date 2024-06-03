SERVICIOS DE NEST

Los servicios son una pieza esencial de las aplicaciones realizadas con el framework NestJS. Están pensados para **proporcionar una capa de acceso a los datos** que necesitan las aplicaciones para funcionar. Mediante los servicios podemos liberar de código a los controladores y conseguir desacoplar éstos de las tecnologías de almacenamiento de datos que estemos utilizando.
 
  # Qué son providers
  
  **Los providers están preparados para ser inyectados** en los controladores de la aplicación, y otras clases si fuera necesario, a través del sistema de inyección de dependencias que proporciona Nest. Gracias a la inyección de dependencias es muy sencillo crear y proporcionar instancias de las clases a los controladores, delegando al propio Nest ese trabajo de instanciar las clases.
  
~~~
Todos los providers que pensamos usar dentro de los módulos se tienen que declarar mediante el decorador @Module(). Esto no es un problema porque generalmente esta tarea se realizará automáticamente por el CLI al generar las clases inyectables.
~~~
## Servicios en Nest

Ahora que tenemos claro qué son los providers y sabemos que los servicios son clases incluidas dentro del conjunto de providers, vamos a profundizar un poco en el concepto de servicio.

Un servicio tiene la responsabilidad de **gestionar el trabajo con los datos de la aplicación**, de modo que realiza las operaciones para obtener esos datos, modificarlos, etc. Es decir, un servicio tiene que ofrecer los métodos adecuados para que los controladores puedan realizar las operaciones necesarias para controlar los datos que necesiten usar.

Aparte de descargar de responsabilidad a los controladores y reducir el acoplamiento con las tecnologías de datos, gracias a los servicios podemos:

- Aislar la lógica de negocio en una clase aparte
- Reutilizar fácilmente el código de trabajo con los datos a lo largo de varios controladores


LINK DEL VIDEO:
https://youtu.be/agKd1KcSJUI