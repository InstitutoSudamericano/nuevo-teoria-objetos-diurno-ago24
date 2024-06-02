# Express y Fastify

## Express

Express.js, a veces también llamado ***Express***, es un framework de backend de Node.js minimalista, rápido que proporciona características y herramientas robustas para desarrollar aplicaciones de backend escalables. Te ofrece el sistema de enrutamiento y características simplificadas para ampliar el framework con componentes y partes más potentes en función de los casos de uso de tu aplicación.

## Fastify

Fastify es un marco web o framework popular de código abierto para crear aplicaciones web y API eficientes de alto rendimiento con Node. Está diseñado para ser liviano y modular, con un enfoque en la velocidad.

###  Express vs Fastify

Fastify se enfoca en una API declarativa, lo que significa que utiliza un enfoque más estructurado y basado en configuración para definir rutas y manejar solicitudes.

Por otro lado Express sigue un enfoque más tradicional de programación funcional, donde se define la lógica de manejo de solicitudes utilizando funciones y middleware. Esto ofrece una mayor flexibilidad pero puede llevar a una estructura de código menos predecible en proyectos grandes.

A continuación se mostrara una tabla comparativa en diferentes aspectos:

<table>
	<tr>
		<th>Framework</th>
		<th>Rendimiento</th>
		<th>Middleware</th>
		<th>optimiza código</th>
		<th>Mayor ecosistema</th>
	</tr>
	<tr>
		<th>Express</th>
		<th></th>
		<th>x</th>
		<th></th>
		<th>x</th>
	</tr>
	<tr>
		<th>Fastify</th>
		<th>x</th>
		<th></th>
		<th>x</th>
		<th></th>
	</tr>
</table>

---

## NestJS
NestJS es un marco de trabajo agnóstico a la plataforma, lo que significa que puede trabajar con cualquier marco de servidor HTTP basado en Node. Además, se puede configurar NestJS para utilizar Express o Fastify para una aplicación, proporcionando opciones para generar un proyecto NestJS, como el uso de Nest CLI o la clonación de un proyecto de inicio.

#### Relación con Express y Fastify
NestJS proporciona una capa de abstracción sobre Express y Fastify, permitiendo a los desarrolladores trabajar con cualquier librería disponible en NodeJS que un proyecto necesite, y ofrece opciones para configurar la aplicación para utilizar Express o Fastify como servidor subyacente. Además, se han mencionado consideraciones sobre rendimiento y escalabilidad al utilizar Express y Fastify en el contexto de NestJS.


### Reflexión
Express y fastify son dos herramientas poderosas para el desarrollo de aplicaciones web en JS. Express es Flexible y madura, mientras que fastify es como un velocista agil y eficiente.

### Analogía 
Según lo que vimos en la materia podemos decir que Nestjs seria como un stack de tecnologías en si, ya que este es un framework que a su vez abarca otros.


### Resumen
En resumen, mientras Express es un framework minimalista y ampliamente utilizado, Fastify se destaca por su velocidad y rendimiento, y NestJS ofrece un marco completo para el desarrollo de aplicaciones eficientes y escalables, con la opción de utilizar Express y Fastify como parte de su arquitectura.


--- 
### Referencias

Rojas, L. G. (2023, 12 mayo). _Asignar rutas en Fastify - Domina Node: Desarrollo de servicios_ [Vídeo]. LinkedIn. [https://es.linkedin.com/learning/domina-node-desarrollo-de-servicios/asignar-rutas-en-fastify#:~:text=Fastify%20es%20un%20marco%20web,un%20enfoque%20en%20la%20velocidad](https://es.linkedin.com/learning/domina-node-desarrollo-de-servicios/asignar-rutas-en-fastify#:~:text=Fastify%20es%20un%20marco%20web,un%20enfoque%20en%20la%20velocidad)

Kinsta. (2022, 19 diciembre). _¿Qué es Express.js? Todo lo que Debes Saber_. Kinsta®. [https://kinsta.com/es/base-de-conocimiento/que-es-express/](https://kinsta.com/es/base-de-conocimiento/que-es-express/)

