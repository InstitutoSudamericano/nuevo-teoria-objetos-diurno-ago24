Una de las ventajas de los componentes web es que puedes crearlos pensando en que puedes usarlos en varios sitios, para ello puedes requerir que cada uno se pueda "personalizar". Por ejemplo, imagina que creas un componente para pintar un botón. Si a ese botón le pones un texto, en cualquier sitio donde uses ese componente va a mostrar el mismo texto, ¿no sería genial poder cambiar el texto dependiendo del texto que necesitemos en ese momento?

El ejemplo anterior es un ejemplo de comunicación desde el padre al hijo, pero también se puede hacer al revés, por ejemplo, para hacer una acción en el componente padre cuando ocurra algo en el hijo como pulsar un botón por ejemplo.

Dentro de la comunicación entre componentes en Angular, hay varios tipos dependiendo de lo que necesitemos.

## Comunicación mediante Propiedades

Una forma común de comunicación entre componentes es mediante el uso de propiedades. Puedes pasar datos de un componente padre a un componente hijo a través de propiedades de entrada. Para ello, sigue estos pasos:

- En el componente hijo, declara una propiedad de entrada utilizando la anotación `@Input()`. Por ejemplo:

![](https://miro.medium.com/v2/resize:fit:875/1*zRLiJuHgbMmEt0AOM7_Lzg.png)

- En el componente padre, en el template donde se utiliza el componente hijo, enlaza la propiedad de entrada con una expresión. Por ejemplo:

![](https://miro.medium.com/v2/resize:fit:875/1*A35bmU-RhCUvcFJ423L08Q.png)

Los corchetes en las propiedades `input` de un componente se utilizan para establecer una comunicación unidireccional entre componentes padre e hijo, permitiendo que el componente padre pase valores al componente hijo y actualice las propiedades de este en consecuencia. OJO: la sintaxis para realizar un “property binding” desde el HTML se debe hacer entre corchetes [] con una expresión TypeScript, es decir, podemos todo lo que vaya dentro de las comillas dobles es código TS, como invocar una función, una variable o un dato primitivo.

~~~
Resumen: Comunicación entre Componentes

En Front-End:

1. **Propiedades (Props)**: Permite pasar datos de un componente padre a uno hijo. Es sencillo y explícito, pero solo permite comunicación unidireccional.
2. **Eventos**: Componentes hijos pueden emitir eventos que los padres escuchan y manejan, permitiendo comunicación bidireccional.
3. **Contexto o Proveedores de Estado (Context API, Redux, Vuex)**: Permiten compartir estado global entre componentes, facilitando la gestión de estado en aplicaciones grandes.

#### En Microservicios:

1. **API REST**: Los microservicios se comunican mediante llamadas HTTP, es simple pero puede ser lento por la latencia de la red.
2. **Mensajería (Message Queues)**: Utiliza colas de mensajes como RabbitMQ o Kafka para comunicación asíncrona, mejorando la resiliencia y desacoplando servicios.
3. **gRPC**: Un framework RPC que utiliza HTTP/2, proporcionando alta performance y soporte para múltiples lenguajes.

#### Patrones y Prácticas Comunes:

1. **Pub/Sub (Publicación/Suscripción)**: Los componentes publican eventos a los que otros se suscriben, ofreciendo alta escalabilidad.
2. **Mediator**: Un componente intermediario maneja la comunicación, centralizando la lógica pero potencialmente creando un cuello de botella.

#### Herramientas y Tecnologías:

- **React Context, Redux, MobX** para React.
- **Vuex, Pinia** para Vue.js.
- **Angular Services** para Angular.
- **Kafka, RabbitMQ, AWS SQS** para mensajería entre microservicios.
- **GraphQL** para consultas de datos flexibles y eficientes.

#### Consideraciones Finales:

La elección del método de comunicación depende del caso de uso, tamaño y complejidad de la aplicación, y las preferencias del equipo. Es esencial balancear la simplicidad con la necesidad de escalabilidad y rendimiento.
~~~
LINK DEL VIDEO:
https://youtu.be/LiUXxM4jjvs
