## Controladores en Desarrollo Web con NestJS

**Video YouTube**:https://youtu.be/dx-FE1Z0HgU 

En este documento, exploraremos el uso de controladores en una aplicación web utilizando NestJS, un marco de trabajo para Node.js que facilita la creación de API RESTful y aplicaciones web escalables. Nos centraremos en cómo se utilizan los decoradores `@Controller`, `@Get`, `@Post`, `@Put`, `@HttpCode`, `@Param` y `@Body` para manejar solicitudes HTTP.

![imagen1](https://imgs.search.brave.com/7GJWqjyxv-KFhfLjtbxc5F8QiX_Q_On5mD3iOxoLegk/rs:fit:860:0:0/g:ce/aHR0cHM6Ly9jb2Rp/Z29lbmNhc2EuY29t/L2NvbnRlbnQvaW1h/Z2VzL3NpemUvdzIw/MDAvMjAyMi8wNy9u/RVNUanMyLkpQRw)
## Introducción a NestJS y Controladores

NestJS utiliza decoradores para definir controladores y manejar las rutas y acciones asociadas a ellas. En el siguiente ejemplo, crearemos un controlador `CatsController` para gestionar las operaciones.

```typescript
import { Controller, Get, Post, HttpCode, Param, Body, Put } from '@nestjs/common';
import { CreateCatDto } from './dto/create-cat.dto';

@Controller('cats')
export class CatsController {
    @Get()
    @HttpCode(200)
    findAll(): string {
        return 'This action returns all cats';
    }

    @Get(':id')
    findOne(@Param('id') id: string): string {
        return `This action returns cat #${id}`;
    }

    @Post()
    async create(@Body() createCatDto: CreateCatDto){
        return 'This action adds a new cat';
    }

    @Put(':id')
    async update(@Param('id') id: string, @Body() updateCatDTO: CreateCatDto){
        return `This action updates cat #${id}`;
    }
}
```

Explicación de los Decoradores y Métodos del Controlador
@Controller('cats'): Este decorador define la raíz de las rutas manejadas por este controlador como /cats.

`@Get()`: Define un manejador para las solicitudes HTTP GET en la ruta /cats. En este ejemplo, el método findAll() devuelve un mensaje que indica que se devuelven todos los gatos.

`@Get(':id')`: Define un manejador para las solicitudes HTTP GET en la ruta /cats/:id, donde :id es un parámetro dinámico. El método findOne() toma el parámetro id de la URL y devuelve un mensaje que indica que se devuelve el gato con ese ID.

`@Post()`: Define un manejador para las solicitudes HTTP POST en la ruta /cats. El método create() utiliza el decorador @Body() para extraer los datos del cuerpo de la solicitud (en este caso, un objeto createCatDto) y realizar una acción, como crear un nuevo gato.

`@Put(':id')`: Define un manejador para las solicitudes HTTP PUT en la ruta /cats/:id. El método update() toma el parámetro id de la URL y los datos del cuerpo de la solicitud (updateCatDTO) para realizar una acción, como actualizar los detalles de un gato existente.

## **Conclusiones**

Los controladores en NestJS simplifican la creación de API RESTful al organizar de manera clara las rutas y acciones asociadas. 

Los decoradores como @Get, @Post y @Put facilitan la definición de las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre recursos, mientras que @Param y @Body permiten acceder a los parámetros de la URL y los datos del cuerpo de la solicitud de manera sencilla. 

Este enfoque facilita el desarrollo de aplicaciones web robustas y mantenibles.

### Bibliografias

- Controladores en NestJS. Desarrolloweb.com. Recuperado el 15 de abril de 2024, de https://desarrolloweb.com/articulos/controladores-nest

- Documentation. Documentation | NestJS - A Progressive Node.Js Framework. Recuperado el 15 de abril de 2024, de https://docs.nestjs.com/controllers


- Servicio de las Tecnologías de la Información y las Comunicaciones-Universidad de Almería. Introducción a NestJS. Github.io. Recuperado el 15 de abril de 2024, de https://ualmtorres.github.io/SeminarioNestJS/?ref=reactivisima.com




