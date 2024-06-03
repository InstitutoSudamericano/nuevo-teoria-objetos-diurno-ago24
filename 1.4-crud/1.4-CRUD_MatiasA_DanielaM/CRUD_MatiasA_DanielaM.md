### Integrantes: Matias Aguilera, Daniela Muñoz

Teoría sobre la Arquitectura de Prisma.io
Teoría
La arquitectura de Prisma.io se basa en un conjunto de componentes que trabajan juntos para simplificar y agilizar el desarrollo de aplicaciones modernas. Los componentes principales incluyen:

Prisma Client: Es una biblioteca de base de datos auto-generada que proporciona una interfaz de programación de aplicaciones (API) para interactuar con la base de datos. Prisma Client simplifica las consultas a la base de datos y maneja la conexión y la transacción de manera transparente.
Prisma Schema: Define el modelo de datos de la aplicación y la configuración de la base de datos. Utilizando un lenguaje específico de dominio (DSL), Prisma Schema permite especificar entidades, relaciones, validaciones y otras configuraciones relacionadas con la base de datos.
Prisma Migrate: Proporciona una forma declarativa de gestionar los cambios en el esquema de la base de datos. Con Prisma Migrate, los desarrolladores pueden crear y aplicar migraciones de esquema de manera controlada y reproducible.
Prisma Studio: Es una interfaz de usuario gráfica que permite explorar y administrar los datos de la base de datos. Prisma Studio facilita la visualización de los datos y la ejecución de consultas ad-hoc para el desarrollo y la depuración de la aplicación.
Reflexión
La arquitectura de Prisma.io ofrece varias ventajas significativas. Simplifica el desarrollo al proporcionar una capa de abstracción sobre la base de datos, lo que permite a los desarrolladores centrarse en la lógica de la aplicación en lugar de en los detalles de la base de datos. Además, al utilizar un enfoque declarativo para la gestión de esquemas y migraciones, Prisma.io mejora la seguridad y la consistencia de la base de datos.

Sin embargo, también presenta desafíos, especialmente en entornos de alta concurrencia o en aplicaciones que requieren un control fino sobre el rendimiento de la base de datos. En estos casos, es importante tener en cuenta las limitaciones y considerar estrategias adicionales para optimizar el rendimiento.

Analogía
Podemos comparar la arquitectura de Prisma.io con una fábrica moderna. Prisma Schema sería el plano de la fábrica, que define la estructura y los procesos de producción. Prisma Migrate sería el equipo de ingenieros encargados de construir y mantener la fábrica, asegurando que los cambios se realicen de manera ordenada y sin interrupciones en la producción. Prisma Client sería el personal de la fábrica que interactúa directamente con las máquinas y los materiales, ejecutando las órdenes de producción y gestionando los recursos de manera eficiente. Prisma Studio sería la sala de control desde la cual se supervisa y gestiona todo el proceso de producción, permitiendo ajustes en tiempo real y facilitando la toma de decisiones informadas.

Resumen
En resumen, la arquitectura de Prisma.io proporciona una forma moderna y eficiente de trabajar con bases de datos en aplicaciones web. Con componentes como Prisma Client, Prisma Schema, Prisma Migrate y Prisma Studio, los desarrolladores pueden construir y mantener aplicaciones robustas y escalables de manera más sencilla y segura.    
### Referencias: 
Burk, N., & Schickling, J. (). Practical Prisma. Manning Publications.

### Link Youtube

Daniela Muñoz
https://youtu.be/77AEVVIcqAQ

Matias Aguilera
https://youtu.be/Z-ivBBAcRzk