# Controladores en NestJS

### Nathaly Caballero: https://www.youtube.com/watch?v=HZ6KtABSfFo

### David Correa: https://youtu.be/3s2v_DlzlGU

## 1. Introducción

NestJS es un framework progresivo para construir aplicaciones del lado del servidor en Node.js, utilizando TypeScript. Un componente clave de NestJS son los controladores, que manejan las solicitudes entrantes y devuelven las respuestas al cliente.

> **Reflexión**: ¿Cómo estructuran los controladores la lógica de manejo de solicitudes en una aplicación NestJS en comparación con otros frameworks como Express.js?

## 2. Definición de Controladores

En NestJS, los controladores se definen utilizando el decorador `@Controller()`. Un controlador es una clase que agrupa métodos relacionados con la gestión de rutas específicas. Cada método de un controlador puede gestionar diferentes solicitudes HTTP como GET, POST, PUT, DELETE, utilizando decoradores como `@Get()`, `@Post()`, etc.

**Ejemplo de un controlador básico:**

```typescript
import { Controller, Get, Post } from '@nestjs/common';

@Controller('cats')
export class CatsController {
  @Get()
  findAll(): string {
    return 'This action returns all cats';
  }

  @Post()
  create(): string {
    return 'This action adds a new cat';
  }
}
```

> **Reflexión**: La organización de rutas mediante decoradores en controladores de NestJS facilita la claridad y mantenimiento del código. ¿Cómo afecta esto la escalabilidad de una aplicación?

## 3. Decoradores de Métodos

Los decoradores de métodos como `@Get()`, `@Post()`, `@Put()`, `@Delete()` son utilizados para definir las rutas HTTP y los métodos que las manejarán. Estos decoradores permiten una configuración declarativa de las rutas y sus respectivos métodos.

**Ejemplo:**

```typescript
@Controller('dogs')
export class DogsController {
  @Get(':id')
  findOne(@Param('id') id: string): string {
    return `This action returns a dog with id ${id}`;
  }
}
```

> **Reflexión**: El uso de decoradores para definir rutas y métodos hace que el código sea más legible y fácil de entender. ¿De qué manera esta claridad puede contribuir a la colaboración en equipos de desarrollo?

## 4. Inyección de Dependencias

NestJS utiliza un sistema de inyección de dependencias que permite a los controladores trabajar con otros servicios de manera eficiente. Los servicios se pueden inyectar en los controladores a través del constructor, permitiendo la separación de la lógica empresarial de la lógica de manejo de solicitudes.

**Ejemplo:**

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class CatsService {
  findAll(): string {
    return 'This action returns all cats';
  }
}

@Controller('cats')
export class CatsController {
  constructor(private readonly catsService: CatsService) {}

  @Get()
  findAll(): string {
    return this.catsService.findAll();
  }
}
```

> **Reflexión**: La inyección de dependencias promueve un código más modular y testable. ¿Cómo puede esta modularidad mejorar la mantenibilidad de una aplicación?

## 5. Manejo de Excepciones

NestJS proporciona un sistema integrado para el manejo de excepciones que permite gestionar errores de manera centralizada. Los controladores pueden utilizar filtros de excepción personalizados para manejar diferentes tipos de errores y proporcionar respuestas adecuadas al cliente.

**Ejemplo:**

```typescript
import { Controller, Get, Param, NotFoundException } from '@nestjs/common';

@Controller('cats')
export class CatsController {
  @Get(':id')
  findOne(@Param('id') id: string): string {
    if (id !== '1') {
      throw new NotFoundException('Cat not found');
    }
    return `This action returns a cat with id ${id}`;
  }
}
```

> **Reflexión**: La capacidad de manejar excepciones de manera centralizada mejora la robustez de la aplicación. ¿Cómo puede esto influir en la experiencia del usuario final?

---

## Resumen

| Aspecto                         | Detalles                                                                                  |
| ------------------------------- | ----------------------------------------------------------------------------------------- |
| **Definición de Controladores** | Uso de `@Controller()` para agrupar métodos relacionados con rutas específicas.           |
| **Decoradores de Métodos**      | Decoradores como `@Get()`, `@Post()`, `@Put()`, `@Delete()` para definir rutas y métodos. |
| **Inyección de Dependencias**   | Permite la separación de la lógica empresarial de la lógica de manejo de solicitudes.     |
| **Manejo de Excepciones**       | Sistema integrado para gestionar errores de manera centralizada.                          |

NestJS, con su enfoque modular y basado en decoradores, permite una estructura clara y eficiente para la gestión de solicitudes y respuestas en aplicaciones del lado del servidor. La capacidad de manejar dependencias y excepciones de manera efectiva contribuye a la creación de aplicaciones robustas y escalables.

## Referencias

- Alvarez, A. (2022). Manual de Nest [Libro digital]. https://desarrolloweb.com/articulos/variables-entorno-configuracion-nest
- NestJS - A progressive Node.js framework. (s. f.-b). NestJS - A Progressive Node.js Framework. https://nestjs.com/
- De las Tecnologías de la Información y las Comunicaciones - Universidad de Almería, S. (s. f.). Introducción a NestJS. https://ualmtorres.github.io/SeminarioNestJS/?ref=reactivisima.com

---

### Pull Request

![](PullRequest.png)
