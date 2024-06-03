# Deploy en Prisma con Railway

### Nathaly Caballero: https://www.youtube.com/watch?v=--3lhKQxzRo

### David Correa: https://youtu.be/xjgjxeX1VOg

## 1. Introducción

Railway es una plataforma en la nube que permite desplegar aplicaciones de manera sencilla. Junto con Prisma, proporciona una forma eficiente de gestionar y desplegar aplicaciones que interactúan con bases de datos. Este tutorial describe cómo realizar el deploy de una aplicación Prisma en Railway, utilizando una instancia de PostgreSQL y un repositorio de GitHub.

> **Reflexión**: ¿Cómo pueden servicios como Railway y herramientas como Prisma simplificar y agilizar el proceso de despliegue y gestión de bases de datos en aplicaciones modernas?

## 2. Preparativos Iniciales

### Crear una Instancia de PostgreSQL en Railway

1. **Registrar e Iniciar Sesión en Railway**:

   - Ir a [Railway](https://railway.app/) y registrarse o iniciar sesión.

2. **Crear un Nuevo Proyecto**:

   - En el dashboard de Railway, hacer clic en "New Project".
   - Seleccionar "Provision PostgreSQL" para crear una nueva base de datos PostgreSQL.

3. **Obtener URL de Conexión**:
   - Una vez creada la instancia, obtener la URL de conexión desde la sección de configuración de la base de datos. Esta URL se usará en el archivo `.env` de Prisma.

> **Reflexión**: La provisión de servicios gestionados como bases de datos en Railway simplifica la infraestructura necesaria para el despliegue de aplicaciones. ¿Cómo afecta esto a la productividad de los desarrolladores y la rapidez del ciclo de desarrollo?

### Configuración de Prisma

1. **Configurar el Archivo `.env`**:

   - Crear un archivo `.env` en el proyecto y añadir la URL de conexión de PostgreSQL:

   ```env
   DATABASE_URL=postgresql://user:password@host:port/database
   ```

2. **Definir el Esquema de Prisma**:

   - Editar el archivo `schema.prisma` para definir los modelos y la configuración de la base de datos:

   ```prisma
   datasource db {
     provider = "postgresql"
     url      = env("DATABASE_URL")
   }

   generator client {
     provider = "prisma-client-js"
   }

   model User {
     id    Int     @id @default(autoincrement())
     email String  @unique
     name  String?
   }
   ```

3. **Migraciones y Generación del Cliente Prisma**:
   - Ejecutar las migraciones para sincronizar el esquema con la base de datos:
   ```bash
   npx prisma migrate dev --name init
   ```
   - Generar el cliente Prisma:
   ```bash
   npx prisma generate
   ```

> **Reflexión**: La capacidad de Prisma para gestionar esquemas y generar clientes tipados mejora la integración con bases de datos. ¿Cómo puede esto influir en la consistencia y la eficiencia del desarrollo de aplicaciones?

## 3. Despliegue en Railway

### Conectar el Proyecto a un Repositorio de GitHub

1. **Subir el Código a GitHub**:

   - Crear un repositorio en GitHub y subir el código del proyecto.

2. **Conectar Railway a GitHub**:

   - En Railway, ir a la sección de "Deployments".
   - Seleccionar "GitHub" y conectar el proyecto de Railway al repositorio de GitHub.

3. **Configurar Variables de Entorno**:

   - En el dashboard de Railway, ir a la configuración del proyecto y añadir las variables de entorno necesarias (`DATABASE_URL`).

4. **Desplegar la Aplicación**:
   - Railway automáticamente detectará los cambios en el repositorio y desplegará la aplicación. Asegurarse de que el archivo `Dockerfile` o la configuración de `railway.json` estén correctamente configurados para el despliegue.

### Configuración del `main.ts` y `package.json`

En el archivo `main.ts` se realiza un configuración en el puerto:

```typescript
await app.listen(process.env.PORT || 3000);
```

También se realiza una configuración personalizada de los scripts del `package.json`:

```json
{
  "scripts": {
    "postinstall": "npx prisma generate && npm run build",
    "start:prod": "node dist/src/main"
  }
}
```

> **Reflexión**: La integración continua y el despliegue automatizado a través de GitHub y Railway facilitan el mantenimiento y la actualización de aplicaciones en producción. ¿Cómo puede esto impactar la confiabilidad y la rapidez de respuesta a cambios y mejoras?

## Resumen

| Aspecto                             | Detalles                                                                                             |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Crear Instancia PostgreSQL**      | Provisionar una base de datos PostgreSQL en Railway.                                                 |
| **Configurar Prisma**               | Configuración del archivo `.env`, definición de esquemas en `schema.prisma` y generación de cliente. |
| **Conectar a GitHub**               | Subir el código a GitHub y conectar Railway al repositorio para despliegue automático.               |
| **Configurar Variables de Entorno** | Añadir variables de entorno en Railway para conectar la base de datos.                               |
| **Desplegar la Aplicación**         | Railway despliega automáticamente al detectar cambios en el repositorio de GitHub.                   |

Railway y Prisma proporcionan una solución potente y sencilla para el despliegue y gestión de aplicaciones. Desde la configuración inicial hasta el despliegue automático, esta combinación mejora significativamente la eficiencia y seguridad del ciclo de desarrollo.

## Referencias

- Deploy a new GitHub repository. (s. f.). Railway. https://railway.app/new/github
- Pratama, P. P. (2023, 17 septiembre). Getting Started with Prisma ORM in Nest.js: A Comprehensive Guide. Medium. https://medium.com/google-developer-indonesia/getting-started-with-prisma-orm-in-nest-js-a-comprehensive-guide-787bdb65c02e
- Kale, V., & Akshay. (2024, 22 mayo). Mastering Prisma ORM in Node.js: A Comprehensive Guide. Mindbowser. https://www.mindbowser.com/prisma-orm-nodejs-development-guide/
- Railway. (s. f.). Railway. https://railway.app/

### Pull Request

![](PullRequest.png)
