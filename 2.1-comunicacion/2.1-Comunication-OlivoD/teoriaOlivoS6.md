# Comunicación entre componentes en Angular

Video de Youtube: https://www.youtube.com/watch?v=vxkys-UtiRo

La comunicación entre componentes en Angular es un aspecto fundamental para el desarrollo de aplicaciones web eficientes y mantenibles. Existen varias técnicas y métodos para lograr esta comunicación, dependiendo de la relación entre los componentes y la naturaleza de los datos que necesitan compartir. A continuación, desglosaré los diferentes métodos que se utilizan en Angular para la comunicación de componentes.

## 1. Comunicación entre Componentes Padre e Hijo

### 1.1. Decorador `@Input`
El decorador `@Input` se utiliza para pasar datos desde un componente padre a un componente hijo. El componente padre define una propiedad y la enlaza a un atributo del componente hijo.

```typescript
// Componente hijo (child.component.ts)
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-child',
  template: `<p>{{ childProperty }}</p>`
})
export class ChildComponent {
  @Input() childProperty: string;
}

// Componente padre (parent.component.ts)
import { Component } from '@angular/core';

@Component({
  selector: 'app-parent',
  template: `<app-child [childProperty]="parentProperty"></app-child>`
})
export class ParentComponent {
  parentProperty = 'Hello from parent!';
}
```

### 1.2. Decorador `@Output` y `EventEmitter`
El decorador `@Output` junto con la clase `EventEmitter` se utilizan para enviar datos desde un componente hijo a un componente padre. El componente hijo emite un evento que el componente padre escucha.

```typescript
// Componente hijo (child.component.ts)
import { Component, Output, EventEmitter } from '@angular/core';

@Component({
  selector: 'app-child',
  template: `<button (click)="sendData()">Click me</button>`
})
export class ChildComponent {
  @Output() notify: EventEmitter<string> = new EventEmitter<string>();

  sendData() {
    this.notify.emit('Data from child');
  }
}

// Componente padre (parent.component.ts)
import { Component } from '@angular/core';

@Component({
  selector: 'app-parent',
  template: `<app-child (notify)="onNotify($event)"></app-child>`
})
export class ParentComponent {
  onNotify(message: string) {
    console.log(message);
  }
}
```

## 2. Comunicación entre Componentes Hermanos

### 2.1. Servicio de Intercambio de Datos
Para comunicar componentes hermanos, se suele utilizar un servicio que actúa como intermediario. Este servicio contiene propiedades y métodos para almacenar y transferir datos entre los componentes.

```typescript
// Servicio (data.service.ts)
import { Injectable } from '@angular/core';
import { BehaviorSubject } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class DataService {
  private dataSource = new BehaviorSubject<string>('default data');
  currentData = this.dataSource.asObservable();

  changeData(data: string) {
    this.dataSource.next(data);
  }
}

// Componente A (component-a.component.ts)
import { Component } from '@angular/core';
import { DataService } from './data.service';

@Component({
  selector: 'app-component-a',
  template: `<button (click)="sendData()">Send Data to B</button>`
})
export class ComponentA {
  constructor(private dataService: DataService) {}

  sendData() {
    this.dataService.changeData('Data from Component A');
  }
}

// Componente B (component-b.component.ts)
import { Component, OnInit } from '@angular/core';
import { DataService } from './data.service';

@Component({
  selector: 'app-component-b',
  template: `<p>{{ data }}</p>`
})
export class ComponentB implements OnInit {
  data: string;

  constructor(private dataService: DataService) {}

  ngOnInit() {
    this.dataService.currentData.subscribe(data => this.data = data);
  }
}
```

## 3. Comunicación mediante `@ViewChild` y `@ContentChild`

### 3.1. Decorador `@ViewChild`
`@ViewChild` se utiliza para acceder a un componente hijo, directiva o plantilla desde el componente padre.

```typescript
// Componente hijo (child.component.ts)
import { Component } from '@angular/core';

@Component({
  selector: 'app-child',
  template: `<p>Hello from Child</p>`
})
export class ChildComponent {
  sayHello() {
    return 'Hello from Child Component!';
  }
}

// Componente padre (parent.component.ts)
import { Component, AfterViewInit, ViewChild } from '@angular/core';
import { ChildComponent } from './child.component';

@Component({
  selector: 'app-parent',
  template: `<app-child></app-child>`
})
export class ParentComponent implements AfterViewInit {
  @ViewChild(ChildComponent) childComponent: ChildComponent;

  ngAfterViewInit() {
    console.log(this.childComponent.sayHello());
  }
}
```

### 3.2. Decorador `@ContentChild`
`@ContentChild` se utiliza para acceder a elementos hijos que se proyectan en un componente a través de `ng-content`.

```typescript
// Componente (container.component.ts)
import { Component, ContentChild, AfterContentInit } from '@angular/core';

@Component({
  selector: 'app-container',
  template: `<ng-content></ng-content>`
})
export class ContainerComponent implements AfterContentInit {
  @ContentChild('projectedContent') content;

  ngAfterContentInit() {
    console.log(this.content.nativeElement.textContent);
  }
}

// Uso del componente (app.component.html)
<app-container>
  <p #projectedContent>Hello from projected content!</p>
</app-container>
```

## 4. Comunicación Global mediante Servicios y Observables

En aplicaciones más complejas, es común utilizar servicios junto con observables para gestionar el estado global de la aplicación y facilitar la comunicación entre componentes que no tienen una relación directa.

```typescript
// Servicio global (global.service.ts)
import { Injectable } from '@angular/core';
import { Subject } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class GlobalService {
  private subject = new Subject<any>();

  sendMessage(message: string) {
    this.subject.next(message);
  }

  getMessage() {
    return this.subject.asObservable();
  }
}

// Componente emisor (sender.component.ts)
import { Component } from '@angular/core';
import { GlobalService } from './global.service';

@Component({
  selector: 'app-sender',
  template: `<button (click)="sendMessage()">Send Global Message</button>`
})
export class SenderComponent {
  constructor(private globalService: GlobalService) {}

  sendMessage() {
    this.globalService.sendMessage('Global message from Sender Component');
  }
}

// Componente receptor (receiver.component.ts)
import { Component, OnInit } from '@angular/core';
import { GlobalService } from './global.service';

@Component({
  selector: 'app-receiver',
  template: `<p>{{ message }}</p>`
})
export class ReceiverComponent implements OnInit {
  message: string;

  constructor(private globalService: GlobalService) {}

  ngOnInit() {
    this.globalService.getMessage().subscribe(message => this.message = message);
  }
}
```

## Conclusión

La comunicación entre componentes en Angular es esencial para construir aplicaciones interactivas y dinámicas. Dependiendo del contexto, se pueden utilizar diferentes técnicas como `@Input` y `@Output` para la comunicación entre componentes padre e hijo, servicios compartidos para componentes hermanos, `@ViewChild` y `@ContentChild` para acceso directo a componentes hijos, y servicios globales con observables para manejar estados y datos a nivel de aplicación. Comprender y aplicar estos métodos correctamente es crucial para el desarrollo de aplicaciones Angular robustas y escalables.