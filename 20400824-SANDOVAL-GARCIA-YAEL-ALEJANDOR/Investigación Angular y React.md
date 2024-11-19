# Investigación Sobre Angular y React

## Índice

- [Introducción](#introducción)
- [Angular](#angular)
  - [Versiones de Angular](#versiones-de-angular)
  - [Características](#características)
  - [Ventajas](#ventajas)
  - [Limitaciones](#limitaciones)
  - [Instalación](#instalación)
    - [Prerrequisitos](#prerrequisitos)
    - [Instalar Angular CLI](#instalar-el-cli-de-angular)
    - [Crear una nueva aplicación](#crear-una-nueva-aplicación)
    - [Ejecutar la aplicación](#ejecutar-la-aplicación)
    - [Ejemplo de una aplicación](#ejemplo-de-una-aplicación)
- [React](#react)
  - [¿Cómo funciona?](#cómo-funciona)
  - [Características](#características-1)
  - [Pros](#pros)
  - [Contras](#contras)
  - [Instalación](#instalación-1)
    - [Prerrequisitos](#prerrequisitos-1)
    - [Crear una aplicación](#crear-una-aplicación)
    - [Ejecutar la aplicación](#ejecutar-la-aplicación-1)
    - [Ejemplo](#ejemplo)
- [Conclusión](#conclusión)
- [Bibliografía](#bibliografía)

## Introducción

En el desarrollo de software, un framework es una estructura de soporte conceptual y tecnológica definida, generalmente, con artefactos o módulos de software específicos, que pueden servir como base para la organización y desarrollo de software.

Es decir, un framework es una especie de plantilla, esquema o estructura conceptual basada en tecnología que permite trabajar de una forma mucho más sencilla. De esta forma, se evitan posibles errores de programación.

Los frameworks más populares en la actualidad son:
1. Bootstrap
2. React
3. Angular
4. Vue.js
5. Ember.js

## Angular

Angular es un Framework de JavaScript de código abierto **escrito en TypeScript**. Su objetivo principal es desarrollar aplicaciones de una sola página. Google se encarga del mantenimiento y constantes actualizaciones de mejoras para este framework.

### Versiones de Angular

"Angular" es el término general para las distintas versiones que existen. **Angular se desarrolló en 2009** y, como resultado, ha ido evolucionando cada vez más.

Primero, estaba el Angular original, llamado **Angular 1 y eventualmente conocido como AngularJS**. Luego vinieron Angular 2, 3, 4, 5, 6, 7 hasta que finalmente, la versión actual, **Angular 12, lanzada el 12/05/2021**.

### Características 

* Document Object Model (DOM).
* Data Binding (Enlace de datos).
* Angular usa el Framework de prueba **Jasmine**.

### Ventajas

* Componentes personalizados.
* Permite a los usuarios mover datos sin esfuerzo desde el código JavaScript a la vista.
* Permite a los usuarios escribir servicios modulares e inyectarlos donde sea que se necesiten.
* Compatibilidad del navegador.

### Limitaciones 

* Curva de aprendizaje alta.
* Ofrece opciones limitadas que cumplan con las métricas SEO necesarias.
* Cada nueva versión puede ser problemática de actualizar y varias de ellas no son compatibles con versiones anteriores.
* Es bastante complejo en comparación con otras herramientas de front-end.

### Instalación

#### Prerrequisitos

Para instalar Angular es necesario contar:

- Node.js
- npm package manager

#### Instalar el CLI de Angular

Dentro de una terminal ejecutar el siguiente comando:

```bash
npm install -g @angular/cli
```

#### Crear una nueva aplicación

1. Ejecutar el comando CLI ng new y proporcionar un nombre para la app, puede ser "my-app" (no debe contener espacios en blanco o mayúsculas), como en este ejemplo:

```bash
ng new my-app
```

2. El comando ng new solicitará información sobre las funciones que debe incluir la aplicación inicial. Acepta los valores predeterminados presionando la tecla "Enter" o "Return".

#### Ejecutar la aplicación

Para ejcutar el servidor que contendrá la aplicación se debe seguir dos paso:

1. Navegar a la carpeta del espacio de trabajo.
2. Ejecutar ng serve --open.

```bash
cd my-app
ng serve --open
```

#### Ejemplo de una aplicación

A continuación veremos un ejemplo de código en TypeScript y HTML para crear un to-do list en Angular:

app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  todoArray = [];
  newTodo = '';

  addTodo() {
    if (this.newTodo !== '') {
      this.todoArray.push({ title: this.newTodo, completed: false });
      this.newTodo = '';
    } else {
      alert('Field required **');
    }
  }

  deleteTodo(todo) {
    this.todoArray = this.todoArray.filter(item => item !== todo);
  }
}
```

app.component.html

```html
<div>
  <h1>Todo List</h1>
  <form>
    <input type="text" [(ngModel)]="newTodo" placeholder="Enter new todo">
    <button (click)="addTodo()">Add Todo</button>
  </form>
  <ul>
    <li *ngFor="let todo of todoArray">
      {{ todo.title }} ({{ todo.completed ? 'Completed' : 'Not Completed' }})
      <button (click)="deleteTodo(todo)">Delete</button>
    </li>
  </ul>
</div>
```

## React

React.JS, **comúnmente conocido como React**, es una biblioteca de JavaScript utilizada para crear interfaces de usuario. Cada aplicación web de React está formada por **componentes reutilizables** que conforman partes de la interfaz de usuario.

### ¿Cómo funciona?

Existen tres conceptos básicos para el desarrollo web HTML, CSS y JavaScript. Sin embargo, antes de React JS estos conceptos funcionaban por separado, en diferentes archivos y carpetas, por lo que escalar y extraer diferentes partes del código para reutilizar o migrar funcionalidad era más complicado.

React incluye todo en un solo paquete, al que llaman "componente". En los componentes, la estructura HTML y JS son inseparables, y pueden combinarse con CSS. Esto permite mplementar una nueva notación que hace más eficiente el desarrollo de aplicaciones escalables: JSX, que significa JavaScript XML.

### Características

* La sintaxis que usa React es el JavaScript XML (JSX), el cual es una combinación del lenguaje HTML y el JavaScript, por lo que también se considera una extensión.
* React hace uso de los componentes para formar la interfaz de usuario, y pueden ser reutilizados en cualquier otro lugar del sitio web.
* Los componentes pasan por una serie de etapas durante su creación. Regularmente se divide en tres fases esenciales: montaje, utilización y desmontaje.
* Permite que el rendimiento de la página web no se vea afectada por las actualizaciones y que estas, a su vez, se mantengan bien reflejadas en el modelo en objetos para la representación de documentos (DOM).

### Pros

* Fácil de aprender.
* Alto nivel de flexibilidad y máxima "capacidad de respuesta".
* Biblioteca JavaScript 100% de código abierto.
* Marco muy ligero, ya que los datos del lado del usuario pueden presentarse simultáneamente en el servidor.

### Contras

* Falta de documentación oficial. La alta velocidad de desarrollo de React JS deja poco espacio para una documentación adecuada.
* No hay un patrón de desarrollo, por lo que tenemos que tomar demasiadas decisiones.
* Se necesita mucho tiempo para dominarlo.

### Instalación 

React al ser una biblioteca de código abierto, da paso incluir uno de los varios frameworks basados en React:

+ Next.js
+ Gatsby
+ Remix
+ Vite.js

#### Prerrequisitos

1. Concocimientos de HTML, CSS y JavaScript.
2. Tener instalado Node.js y npm package manager

#### Crear una aplicación

En el directorio donde se desea trabajar ejecutar el comando "npx create-react-app", seguido del nombre de la aplicación (no debe llevar espacios en blanco ni mayúsculas). Ejemplo:

```bash
npx create-react-app my-app
```

#### Ejecutar la aplicación

Para poder probar la aplicación se debe acceder al directorio del proyecto y después lanzar el siguiente comando:

```bash
cd my-app
npm start
```

#### Ejemplo

Este es un archivo generado al crear una nueva aplicación combinando React y vite.js:

main.jsx

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'
import { BrowserRouter } from 'react-router-dom'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
)
```

## Conclusión

Ambas herramientas facilitan el trabajo del desarrollador, al simplificar la estructura de una página web, y al mismo tiempo facilitar el escalar la aplicación conforme este vaya creciendo. Aunque estas herramientas se enfocan en el apartado del frontend, permiten integrar funcionalidades del backend sin mucha complicación.  

## Bibliografía

Gonçalves, M. J. (4 de Junio de 2024). ¿Qué es Angular y para qué sirve? Blog de Hiberus. https://www.hiberus.com/crecemos-contigo/que-es-angular-y-para-que-sirve/

Angular. (s. f.). https://docs.angular.lat/guide/setup-local

Coppola M. (20 de Enero de 2023). ¿Qué es React y para qué sirve?. HubSpot. https://blog.hubspot.es/website/que-es-react

Admin_Blog. (17 de Abril de 2023). React JS: Ventajas e Inconvenientes de Implementarlo en tu web. Blog Solbyte. https://www.solbyte.com/blog/react-js-ventajas-e-inconvenientes/

Kinsta. (2023, 13 octubre). Cómo Instalar React en Windows, macOS y Linux - Kinsta®. Kinsta®. https://kinsta.com/es/base-de-conocimiento/instalar-react/

Inicio rápido – React. (s. f.). https://es.react.dev/learn