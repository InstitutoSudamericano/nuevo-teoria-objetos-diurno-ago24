## Servicios en NestJs

**Video de Youtube**: https://youtu.be/m1VTh2u2zVQ 

Los servicios son una parte esencial de las aplicaciones desarrolladas con NestJS. Están diseñados para manejar la lógica de negocio y proporcionar acceso a los datos necesarios para que las aplicaciones funcionen correctamente. 

#### ¿Qué son los Providers?

Los providers son un concepto clave en NestJS, abarcando clases como servicios, repositorios y factorías. Estos providers son inyectables en controladores y otras clases mediante el sistema de inyección de dependencias de Nest, facilitando la creación y provisión de instancias de clases dentro de la aplicación.

#### Construcción de un Servicio

Para construir un servicio en NestJS, podemos utilizar el CLI de Nest. Sigue estos pasos:

1. **Generar la Clase del Servicio:**

   Utilizamos el siguiente comando para generar la clase del servicio:

   ```bash
   nest g s nombre-del-servicio
   ```

   Este comando creará dos archivos dentro de la carpeta `src`:
   - `nombre-del-servicio/nombre-del-servicio.service.ts`: Contiene la clase del servicio.
   - `nombre-del-servicio/nombre-del-servicio.service.spec.ts`: Contiene las pruebas unitarias asociadas al servicio.

2. **Modificación Automática del `app.module.ts`:**

   El CLI de Nest automáticamente actualizará el archivo `app.module.ts` para importar y declarar el servicio como un provider. Verifica que el servicio esté añadido al array `providers` dentro del decorador `@Module`.

   ```typescript
   import { Module } from '@nestjs/common';
   import { nombre-del-servicioService } from './nombre-del-servicio.service';
   
   @Module({
     imports: [],
     controllers: [],
     providers: [nombre-del-servicioService], 
     // Asegúrarse de añadir el servicio aquí
   })
   export class AppModule {}
   ```

#### Inyección de Dependencias en Controladores

Los servicios se inyectan en los controladores utilizando el sistema de inyección de dependencias de Nest. Para utilizar un servicio dentro de un controlador, sigue estos pasos:

1. **Importar el Servicio en el Controlador:**

   Asegúrate de importar el servicio necesario en el controlador donde planeas utilizarlo.

   ```typescript
   import { Controller } from '@nestjs/common';
   import { nombre-del-servicioService } from './nombre-del-servicio.service';

   @Controller('ruta')
   export class NombreDelControladorController {
     constructor(private readonly nombreDelServicioService: nombre-del-servicioService) {}
   }
   ```

2. **Utilizar el Servicio en Métodos del Controlador:**

   Puedes acceder a los métodos del servicio dentro del controlador a través de la instancia del servicio (`nombreDelServicioService`). Por ejemplo:

   ```typescript
   @Get()
   async findAll(): Promise<any[]> {
     return this.nombreDelServicioService.findAll();
   }
   ```

### Conclusión

En conclusión el concepto de servicios en NestJS y su importancia en la arquitectura de las aplicaciones. Hemos aprendido cómo construir y utilizar servicios utilizando el CLI de Nest, así como cómo inyectar dependencias en controladores para acceder a la funcionalidad proporcionada por los servicios. Los servicios son fundamentales para mantener un código limpio, modular y fácilmente mantenible en aplicaciones NestJS.

### Bibliografía

Servicios en NestJS. (s/f). Desarrolloweb.com. Recuperado el 22 de abril de 2024, de https://desarrolloweb.com/articulos/servicios-nest



