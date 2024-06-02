# Decorador "@injectable()"

by: Calle Alex, Tinoco Luis

youtube: "<https://youtu.be/IPMr4YlENRw>"

youtube-Luis: "<https://youtu.be/DVZZJ7PLFTA>"

En NestJS, los decoradores se utilizan para definir componentes, servicios, controladores, etc. y permiten modularizar las aplicaciones aplicando conceptos de orientación a objetos y programación funcional y reactiva. Además, los decoradores en NestJS permiten la inyección de dependencias, la definición de rutas y la generación automática de la documentación en Swagger (OpenAPI).

Los decoradores en NestJS son una parte fundamental de la arquitectura del framework, permitiendo la definición de componentes, servicios, controladores, etc., y facilitando la inyección de dependencias, la definición de rutas y la generación automática de la documentación en Swagger (OpenAPI).

En NestJS, el decorador ***@Injectable()*** se utiliza para marcar una clase como un proveedor de servicios que puede ser inyectado en otros componentes a través de la inyección de dependencias que ofrece NestJS. Este decorador permite que el servicio se pueda enviar al constructor de los controladores, lo que facilita la gestión de dependencias en la aplicación.

## Reflexion

El decorador @Injectable en NestJS es fundamental para la creación de servicios que puedan ser inyectados en controladores u otros servicios. Este decorador se utiliza para marcar una clase como un servicio que puede ser gestionado por el contenedor de inversión de control (IoC) de Nest. Todos los servicios deben tener este decorador antes de la declaración de la clase que lo implementa, lo que permite el uso de la inyección de dependencias que proporciona NestJS

## Analogia

El decorador @Injectable de NestJS puede ser comparado con un maestro constructor en el mundo real. Al igual que un maestro constructor organiza y coordina diferentes especialistas para construir una casa, el decorador @Injectable organiza y coordina las dependencias de una clase en el ecosistema de NestJS.

Cuando usamos @Injectable en una clase, estamos indicando que esa clase es elegible para ser inyectada como una dependencia en otras clases. Esto es similar a cómo el maestro constructor asegura que cada especialista, como los carpinteros, electricistas y fontaneros, esté disponible y listo para ser utilizado en la construcción de una casa.

Además, al igual que un maestro constructor se asegura de que cada especialista cumpla con los estándares de calidad y funcionalidad, el decorador @Injectable en NestJS garantiza que las dependencias de una clase estén disponibles y funcionen correctamente en el contexto de la aplicación.

## Resumen

En resumen, el decorador @Injectable() en NestJS permite que una clase sea marcada como un proveedor de servicios que puede ser inyectado en otros componentes a través de la inyección de dependencias que ofrece NestJS. Esto facilita la gestión de dependencias en la aplicación y permite modularizar las aplicaciones aplicando conceptos de orientación a objetos y programación funcional y reactiva.

Tambien podemos decir que el decorador @Injectable actúa como el maestro constructor del ecosistema de NestJS, organizando y coordinando las dependencias para garantizar un funcionamiento armonioso de la aplicación.
