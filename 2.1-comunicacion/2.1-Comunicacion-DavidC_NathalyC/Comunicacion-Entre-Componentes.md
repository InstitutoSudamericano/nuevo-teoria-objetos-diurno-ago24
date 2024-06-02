# Comunicación entre Componentes con Angular

### Nathaly Caballero: https://www.youtube.com/watch?v=--3lhKQxzRo

### David Correa: https://youtu.be/W6D3axbJipU

## 1. Introducción

Angular es un framework popular para construir aplicaciones web dinámicas y escalables. Una de sus características más importantes es la capacidad de facilitar la comunicación entre componentes. En Angular, los componentes son las unidades básicas de la aplicación, y la comunicación entre ellos es esencial para la construcción de aplicaciones complejas y funcionales. Los decoradores `@Input` y `@Output` juegan un papel crucial en este proceso.

> **Reflexión**: ¿Cómo pueden los decoradores `@Input` y `@Output` en Angular mejorar la modularidad y la reusabilidad de los componentes en una aplicación web?

## 2. Decorador @Input

El decorador `@Input` permite que un componente hijo reciba datos de su componente padre. Esto es esencial para la creación de componentes reutilizables que pueden ser configurados desde fuera.

### Uso del Decorador @Input

Para usar `@Input`, se declara una propiedad en el componente hijo y se adorna con `@Input`. Luego, el componente padre puede pasar datos a esta propiedad.

**Ejemplo:**

1. **Componente Hijo (child.component.ts)**:

   ```typescript
   import { Component, Input } from '@angular/core';

   @Component({
     selector: 'app-child',
     template: '<p>{{ data }}</p>',
   })
   export class ChildComponent {
     @Input() data: string;
   }
   ```

2. **Componente Padre (parent.component.ts)**:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-parent',
     template: '<app-child [data]="parentData"></app-child>',
   })
   export class ParentComponent {
     parentData = 'Hello from Parent';
   }
   ```

> **Reflexión**: La capacidad de pasar datos desde el componente padre al componente hijo usando `@Input` promueve la encapsulación y la reusabilidad de los componentes. ¿Cómo puede esto influir en la estructura y mantenimiento del código en una aplicación Angular?

## 3. Decorador @Output

El decorador `@Output` permite que un componente hijo emita eventos que pueden ser escuchados por su componente padre. Esto es útil para la comunicación de eventos o acciones del componente hijo hacia el padre.

### Uso del Decorador @Output

Para usar `@Output`, se declara un `EventEmitter` en el componente hijo y se adorna con `@Output`. El componente padre puede entonces escuchar estos eventos y reaccionar en consecuencia.

**Ejemplo:**

1. **Componente Hijo (child.component.ts)**:

   ```typescript
   import { Component, Output, EventEmitter } from '@angular/core';

   @Component({
     selector: 'app-child',
     template: '<button (click)="sendData()">Send Data</button>',
   })
   export class ChildComponent {
     @Output() dataEmitter = new EventEmitter<string>();

     sendData() {
       this.dataEmitter.emit('Hello from Child');
     }
   }
   ```

2. **Componente Padre (parent.component.ts)**:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-parent',
     template: '<app-child (dataEmitter)="receiveData($event)"></app-child>',
   })
   export class ParentComponent {
     receiveData(data: string) {
       console.log(data); // Output: Hello from Child
     }
   }
   ```

> **Reflexión**: Permitir que los componentes hijos emitan eventos que los padres pueden escuchar mejora la comunicación y coordinación entre componentes. ¿Cómo puede esto facilitar la implementación de funcionalidades complejas en una aplicación Angular?

## 4. Comunicación Bidireccional

La combinación de `@Input` y `@Output` permite una comunicación bidireccional entre componentes. Esto es útil para escenarios donde tanto el componente padre como el hijo necesitan intercambiar datos y eventos de manera dinámica.

**Ejemplo:**

1. **Componente Hijo (child.component.ts)**:

   ```typescript
   import { Component, Input, Output, EventEmitter } from '@angular/core';

   @Component({
     selector: 'app-child',
     template: `
       <input
         [(ngModel)]="data"
         (ngModelChange)="onDataChange()"
       />
     `,
   })
   export class ChildComponent {
     @Input() data: string;
     @Output() dataChange = new EventEmitter<string>();

     onDataChange() {
       this.dataChange.emit(this.data);
     }
   }
   ```

2. **Componente Padre (parent.component.ts)**:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-parent',
     template: '<app-child [(data)]="parentData"></app-child>',
   })
   export class ParentComponent {
     parentData = 'Initial Data';
   }
   ```

> **Reflexión**: La comunicación bidireccional entre componentes usando `@Input` y `@Output` permite una sincronización eficiente de datos y eventos. ¿Cómo puede esto mejorar la interactividad y la experiencia del usuario en una aplicación Angular?

## Resumen

| Aspecto                        | Detalles                                                                                            |
| ------------------------------ | --------------------------------------------------------------------------------------------------- |
| **@Input**                     | Permite que un componente hijo reciba datos de su componente padre.                                 |
| **@Output**                    | Permite que un componente hijo emita eventos que pueden ser escuchados por el componente padre.     |
| **Comunicación Bidireccional** | Combinación de `@Input` y `@Output` para intercambio dinámico de datos y eventos entre componentes. |

Los decoradores `@Input` y `@Output` son herramientas poderosas en Angular para facilitar la comunicación entre componentes. Al promover la encapsulación y la coordinación de eventos, estos decoradores mejoran la modularidad y reusabilidad del código, permitiendo la construcción de aplicaciones web dinámicas y mantenibles.

## Referencias

- Amazon.com. (s. f.). https://www.amazon.com/Mastering-Angular-Comprehensive-Guide-development/dp/B0CMQVHB4P
- Amazon.in. (s. f.). https://www.amazon.in/Angular-Practice-applications-tomorrow-framework-ebook/dp/B01N9S0CZN
- Horvatić, P. (2024, 18 enero). Guidelines for creating performant Angular applications and their efficient maintenance. Medium. https://medium.com/@patrik.horva90/guidelines-for-creating-performant-angular-applications-and-their-efficient-maintenance-6c7537bd56cf

### Pull Request

![](PullRequest.png)
