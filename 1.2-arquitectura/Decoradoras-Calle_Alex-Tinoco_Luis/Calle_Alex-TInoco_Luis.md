# Documentación de Decoradores en NestJS

by: Calle Alex, Tinoco Luis

youtube-Alex: <https://youtu.be/tLvGcSs5dvI>

## 1. `@Controller('cats')`

- **Descripción**: Este decorador se utiliza para definir una clase como un controlador en NestJS.
- **Parámetros**:
  - `'cats'`: Este es un parámetro opcional que define el prefijo de la ruta para todas las rutas definidas en este controlador. En este caso, todas las rutas estarán bajo el prefijo `/cats`.
- **Uso**: Este decorador se aplica a la clase `CatsController` para indicar que es un controlador responsable de manejar las solicitudes relacionadas con los gatos.

## 2. `@Get()`

- **Descripción**: Este decorador se utiliza para definir un método como una ruta de tipo GET en un controlador NestJS.
- **Parámetros**:
  - `':id'`: Este parámetro opcional define que el método espera recibir un parámetro de ruta llamado `id`.
- **Uso**: Este decorador se aplica a los métodos `findAll()` y `findOne()` para indicar que son rutas de tipo GET.

## 3. `@HttpCode(418)` y `@HttpCode(204)`

- **Descripción**: Estos decoradores se utilizan para establecer el código de estado HTTP que debe devolver el método.
- **Parámetros**:
  - `418`: Código de estado HTTP 418, que significa "soy una tetera"(broma).
  - `204`: Código de estado HTTP 204, que significa "No Content".
- **Uso**: Estos decoradores se aplican a los métodos `findAll()` y `remove()` respectivamente, para establecer el código de estado HTTP adecuado.

## 4. `@Post()`

- **Descripción**: Este decorador se utiliza para definir un método como una ruta de tipo POST en un controlador NestJS.
- **Uso**: Este decorador se aplica al método `create()` para indicar que es una ruta de tipo POST.

## 5. `@Put(':id')`

- **Descripción**: Este decorador se utiliza para definir un método como una ruta de tipo PUT en un controlador NestJS.
- **Parámetros**:
  - `':id'`: Este parámetro opcional define que el método espera recibir un parámetro de ruta llamado `id`.
- **Uso**: Este decorador se aplica al método `update()` para indicar que es una ruta de tipo PUT.

## 6. `@Delete(':id')`

- **Descripción**: Este decorador se utiliza para definir un método como una ruta de tipo DELETE en un controlador NestJS.
- **Parámetros**:
  - `':id'`: Este parámetro opcional define que el método espera recibir un parámetro de ruta llamado `id`.
- **Uso**: Este decorador se aplica al método `remove()` para indicar que es una ruta de tipo DELETE.

## 7. `@Param('id')`

- **Descripción**: Este decorador se utiliza para inyectar un parámetro de ruta en un método de controlador.
- **Parámetros**:
  - `'id'`: Este parámetro define el nombre del parámetro de ruta a inyectar.
- **Uso**: Este decorador se aplica a los parámetros de los métodos `findOne()`, `update()` y `remove()` para inyectar el valor del parámetro de ruta `id`.

## 8. `@Body()`

- **Descripción**: Este decorador se utiliza para inyectar el cuerpo de una solicitud HTTP en un método de controlador..
- **Uso**: Este decorador se aplica al parámetro `CreateCatsDto` del método `create()` para inyectar el cuerpo de la solicitud HTTP.

Estos decoradores de NestJS permiten definir la estructura y el comportamiento de un controlador de manera concisa y expresiva, facilitando la construcción de aplicaciones web con API RESTful.
