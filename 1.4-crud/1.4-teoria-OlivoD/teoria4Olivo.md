# Desarrollo y producción con Prisma Migrate

Video YouTube: https://youtu.be/lE2vWSewwSE 

## Desarrollo

Cuando estás trabajando en tu aplicación en un entorno de desarrollo, Prisma Migrate sirve para gestionar los cambios en la estructura de tu base de datos.

Para generar y aplicar migraciones en desarrollo, simplemente ejecutas el siguiente comando:

```bash
npx prisma migrate dev
```

Antes de que pulses "Enter", asegúrate de estar en el entorno de desarrollo, porque este comando **no** es para producción. Si lo usas allí, puedes causar problemas.

¿Qué hace este comando?:

- Vuelve a ejecutar el historial de migración para detectar cualquier cambio en tu esquema de base de datos.
- Aplica las migraciones pendientes a tu base de datos de desarrollo.
- Si nota algún cambio en el esquema de Prisma, crea una nueva migración para ti.
- Aplica todas las migraciones que todavía no se hayan aplicado y actualiza una tabla interna para llevar el control.
- También, activa la generación de algunos archivos importantes, como Prisma Client.

Este comando puede pedirte que resetees la base de datos en ciertos casos, como cuando hay conflictos en el historial de migración o el esquema de la base de datos se aleja del estado previsto.

Pero si alguna vez necesitas empezar de nuevo en tu base de datos de desarrollo, puedes usar este otro comando:

```bash
npx prisma migrate reset
```

Recuerda, este comando **también** es exclusivo para entornos de desarrollo, ¡no lo uses en producción! Lo que hace es eliminar y recrear tu base de datos, aplicando todas las migraciones y ejecutando algunos scripts especiales.

## Personalización

A veces, las migraciones generadas por Prisma Migrate no son exactamente lo que necesitas. Por ejemplo, si quieres realizar un cambio específico en tu esquema o agregar una funcionalidad que Prisma Migrate no soporta directamente.

En esos casos, puedes usar el comando `--create-only` para crear una migración sin aplicarla:

```bash
npx prisma migrate dev --create-only
```

Después de hacer tus cambios personalizados en la migración, simplemente ejecutas nuevamente `prisma migrate dev` para aplicarla.

## Bibliografía:

Development and production. (s/f). Prisma.Io. Recuperado el 29 de abril de 2024, de https://www.prisma.io/docs/orm/prisma-migrate/workflows/development-and-production

