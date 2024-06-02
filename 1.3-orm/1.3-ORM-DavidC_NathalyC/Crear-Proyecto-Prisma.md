# Creación de un Proyecto en Prisma

### Nathaly Caballero: https://www.youtube.com/watch?v=zy3OmUqNDlw

### David Correa: https://youtu.be/I-tJgsMR-fY

## 1. Introducción

Prisma es un ORM (Object-Relational Mapping) moderno para Node.js y TypeScript, diseñado para facilitar la interacción con bases de datos. Proporciona una capa de abstracción que simplifica las consultas y mutaciones de datos, mejorando la productividad y reduciendo errores comunes.

> **Reflexión**: ¿Cómo puede un ORM como Prisma mejorar la eficiencia en el desarrollo y mantenimiento de aplicaciones en comparación con la escritura manual de consultas SQL?

## 2. Instalación y Configuración Inicial

Para comenzar con Prisma, primero es necesario crear un proyecto Node.js y luego instalar las dependencias necesarias.

**Pasos para la instalación:**

1. Crear un proyecto Node.js:

   ```bash
   mkdir my-prisma-project
   cd my-prisma-project
   npm init -y
   ```

2. Instalar Prisma y sus dependencias:

   ```bash
   npm install @prisma/client
   npm install prisma --save-dev
   ```

3. Inicializar Prisma:
   ```bash
   npx prisma init
   ```

Este comando crea un archivo `prisma/schema.prisma` y una carpeta `.env` donde se puede configurar la conexión a la base de datos.

> **Reflexión**: La inicialización de Prisma proporciona una estructura organizada para la gestión de esquemas de base de datos. ¿De qué manera esta estructura puede influir en la claridad y mantenibilidad del código?

## 3. Definición del Esquema

El archivo `schema.prisma` es donde se define el modelo de datos. Este archivo permite describir las tablas y sus relaciones en una base de datos utilizando el DSL (Domain Specific Language) de Prisma.

**Ejemplo de esquema:**

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
  posts Post[]
}

model Post {
  id        Int      @id @default(autoincrement())
  title     String
  content   String?
  authorId  Int
  author    User     @relation(fields: [authorId], references: [id])
}
```

> **Reflexión**: La definición clara de modelos y relaciones en Prisma facilita la comprensión del esquema de la base de datos. ¿Cómo puede esto mejorar la colaboración entre desarrolladores y otros equipos técnicos?

## 4. Migraciones de Base de Datos

Prisma proporciona una manera fácil de gestionar y aplicar migraciones de base de datos. Las migraciones reflejan los cambios en el esquema y permiten mantener sincronizada la base de datos con el modelo de datos definido.

**Pasos para crear y aplicar migraciones:**

1. Crear una migración:

   ```bash
   npx prisma migrate dev --name init
   ```

2. Aplicar migraciones:
   ```bash
   npx prisma migrate deploy
   ```

> **Reflexión**: Las migraciones gestionadas por Prisma aseguran que los cambios en el esquema de la base de datos sean consistentes y reproducibles. ¿Cómo puede esto afectar el proceso de desarrollo y despliegue?

## 5. Generación del Cliente Prisma

Después de definir el esquema y aplicar las migraciones, Prisma genera un cliente que se utiliza para interactuar con la base de datos en el código de la aplicación.

**Generar el cliente Prisma:**

```bash
npx prisma generate
```

Este comando crea un cliente que permite realizar consultas y mutaciones de manera segura y tipada en TypeScript.

**Ejemplo de uso del cliente:**

```typescript
import { PrismaClient } from '@prisma/client';
const prisma = new PrismaClient();

async function main() {
  const allUsers = await prisma.user.findMany();
  console.log(allUsers);
}

main()
  .catch((e) => console.error(e))
  .finally(async () => {
    await prisma.$disconnect();
  });
```

> **Reflexión**: La generación automática de un cliente tipado facilita las interacciones con la base de datos y reduce errores. ¿De qué manera puede esto influir en la calidad del código y la productividad del desarrollador?

## Resumen

| Aspecto                           | Detalles                                                                                     |
| --------------------------------- | -------------------------------------------------------------------------------------------- |
| **Instalación y Configuración**   | Creación de proyecto Node.js, instalación de dependencias y configuración inicial de Prisma. |
| **Definición del Esquema**        | Uso de `schema.prisma` para definir modelos y relaciones de la base de datos.                |
| **Migraciones de Base de Datos**  | Gestión de cambios en el esquema mediante comandos de migración.                             |
| **Generación del Cliente Prisma** | Generación automática de un cliente para interactuar con la base de datos de forma tipada.   |

Prisma simplifica el desarrollo de aplicaciones al proporcionar herramientas poderosas para la gestión de bases de datos. Desde la instalación y configuración inicial hasta la definición de esquemas y generación de clientes, Prisma facilita un flujo de trabajo eficiente y seguro.

## Referencias

- Prisma | Simplify working and interacting with databases. (s. f.). Prisma. https://www.prisma.io/
- Kale, V., & Akshay. (2024, 22 mayo). Mastering Prisma ORM in Node.js: A Comprehensive Guide. Mindbowser. https://www.mindbowser.com/prisma-orm-nodejs-development-guide/
- Prisma Best Practices for Node.js Developers: A Comprehensive Guide. (s. f.). https://codeit.mk/home/blog/Prisma-Best-Practices-for-Node.js-Developers--A-Comprehensive-Guide

### Pull Request

![](PullRequest.png)
