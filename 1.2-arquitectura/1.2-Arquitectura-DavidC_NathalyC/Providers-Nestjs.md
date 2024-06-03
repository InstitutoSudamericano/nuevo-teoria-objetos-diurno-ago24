# Providers en NestJS

### Nathaly Caballero: https://www.youtube.com/watch?v=RbcGEfU27fY

### David Correa: https://youtu.be/YYHKMym-r_w

## 1. Introducción

En NestJS, los providers son una parte fundamental del sistema de inyección de dependencias del framework. Un tipo común de provider es el servicio (service), que encapsula la lógica de negocio y se utiliza para interactuar con otros componentes de la aplicación.

> **Reflexión**: ¿Cómo facilita la inyección de dependencias la separación de preocupaciones y la modularidad en una aplicación NestJS en comparación con otros frameworks?

## 2. Definición de Providers

Los providers en NestJS son objetos que pueden ser inyectados como dependencias. Un provider se define con el decorador `@Injectable()`, lo que permite a NestJS gestionarlo y resolver sus dependencias. Los servicios son un tipo específico de provider que se utilizan para organizar y encapsular la lógica de negocio.

**Ejemplo de un servicio básico:**

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class CatsService {
  private readonly cats = [];

  findAll(): any[] {
    return this.cats;
  }

  create(cat): void {
    this.cats.push(cat);
  }
}
```

> **Reflexión**: La creación de servicios reutilizables y modulares permite una mejor organización del código. ¿De qué manera puede esto mejorar la mantenibilidad y escalabilidad de una aplicación?

## 3. Inyección de Dependencias

La inyección de dependencias en NestJS permite que los servicios sean utilizados por otros componentes, como controladores. Los servicios se pueden inyectar a través del constructor de una clase, lo que permite acceder a su funcionalidad de manera consistente.

**Ejemplo de inyección de dependencias en un controlador:**

```typescript
import { Controller, Get, Post, Body } from '@nestjs/common';
import { CatsService } from './cats.service';

@Controller('cats')
export class CatsController {
  constructor(private readonly catsService: CatsService) {}

  @Get()
  findAll(): any[] {
    return this.catsService.findAll();
  }

  @Post()
  create(@Body() cat): void {
    this.catsService.create(cat);
  }
}
```

> **Reflexión**: La inyección de dependencias permite una mejor gestión de la lógica de negocio y promueve el desacoplamiento de componentes. ¿Cómo contribuye esto a la prueba y mantenimiento del código?

## 4. Ciclo de Vida de los Providers

Los providers en NestJS tienen un ciclo de vida gestionado por el contenedor de inyección de dependencias. Esto incluye la creación, configuración, y destrucción de los providers. NestJS ofrece varios ámbitos para los providers, como singleton y scope por solicitud, que determinan cómo y cuándo se instancian.

> **Reflexión**: Comprender el ciclo de vida de los providers puede ayudar a optimizar el rendimiento y la eficiencia de una aplicación. ¿Cómo puede afectar esto a la gestión de recursos y la respuesta de la aplicación?

## 5. Providers Personalizados

Además de los servicios, NestJS permite la creación de otros tipos de providers personalizados, como factories, clases y valores. Estos permiten una mayor flexibilidad y control sobre cómo se configuran e inyectan las dependencias.

**Ejemplo de un factory provider:**

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
class ConfigService {
  get(key: string): string {
    return process.env[key];
  }
}

const configServiceProvider = {
  provide: ConfigService,
  useFactory: () => {
    const configService = new ConfigService();
    // Configurar el servicio si es necesario
    return configService;
  },
};

@Module({
  providers: [configServiceProvider],
})
export class AppModule {}
```

> **Reflexión**: La capacidad de definir providers personalizados permite una mayor flexibilidad en la configuración de la aplicación. ¿Cómo puede esto beneficiar la arquitectura y el diseño del software?

## Resumen

| Aspecto                        | Detalles                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------ |
| **Definición de Providers**    | Objetos que pueden ser inyectados como dependencias, definidos con `@Injectable()`.              |
| **Inyección de Dependencias**  | Permite a los servicios ser utilizados por otros componentes, promoviendo el desacoplamiento.    |
| **Ciclo de Vida de Providers** | Gestión de creación, configuración y destrucción por el contenedor de inyección de dependencias. |
| **Providers Personalizados**   | Permiten una mayor flexibilidad y control sobre la configuración de dependencias.                |

NestJS, con su sistema de providers y servicios, facilita una arquitectura modular y bien organizada, promoviendo la reutilización de código y la separación de preocupaciones. La inyección de dependencias, junto con la capacidad de definir providers personalizados, contribuye a la creación de aplicaciones escalables y mantenibles.

## Referencias

- Alvarez, A. (2022). Manual de Nest [Libro digital]. https://desarrolloweb.com/articulos/variables-entorno-configuracion-nest
- Singh, C. (2023, 8 diciembre). Building Scalable and Maintainable Server-Side Applications with NestJS. Medium. https://medium.com/@chandrashekharsingh25/building-scalable-and-maintainable-server-side-applications-with-nestjs-e079fa03ddae
- NestJS - A progressive Node.js framework. (s. f.-b). NestJS - A Progressive Node.js Framework. https://nestjs.com/

### Pull Request

![](PullRequest.png)
