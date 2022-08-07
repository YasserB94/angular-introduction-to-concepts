# Introduction to Angular Concepts
This readme are my notes troughout [this](https://angular.io/guide/architecture) Angular guide.

## What is Angular ? 
- A platform and framework for building single-page client applications.
- Uses HTML and TypeScript
- Is written in TypeScript
- Implements core and optional functionality as a set of TypeScript libraries that can be imported.

## Fundamental Concepts
- The basic building blocks of the Angular framework are **Angular components**.
- Angular components are organized into **ngModules**
- ngModules collect related code into functional sets
- An Application always has at least a **root module**
    - Components **define views**
        - Sets of screen elements that Angular can choose among and modify.
            - The modification happens according to change by logic or change of data
    - Components **use services**
        - Services provide specific functionality, not directly related to views.
        - Service providers can be **injected into components as dependencies**
        - This behaviour makes code modular, reusable and efficient
- Modules, components and services are **classes that use decorators**
    - Decorators **mark their type** and provide metadata that informs Angular on how to use them
        - The **metadata** for a component class **associates** it with a **template** that **defines a view**
        - A **template combines HTML** with  Angular **directives** and **binding markup** that allow angular to modify the HTML before rendering it.
        - **The metadata for a service provides the information** Angular needs to **make it available to components** trough **dependency injection**
- An application's **components** typically **define many views**, arranged hierarchically
- Angular provides the **Router Service** to help us **navigate paths among views**
    - The router provides in-browser navigation

## Angular Modules
- Angular **NgModules differ from** and complement **Javascript modules**
-  An NgModule **declares** a compilation **context** **for a set of components** that is **dedicated to:**
    - An application domain,
    - A workflow,
    - or a closely releated set of capabilities
- Can **associate its components with related code** such as:
    - Services,
    - Form functional units
    - ...
- **Every Angular application has a _root module_** named AppModule
    - Provides a bootstrap mechanism that launches the application
    - Typically an application contains many functional modules
- NgModules **can import** functionality **from other NgModules**
- NgModules **can export functionality** to be **used by other NgModules**
    - Example:
        - To use the router service we can import the Router NgModule
        - ```import { RouterModule } from '@angular/router';```
- **Organizing code** into **distinct** functional **modules** helps:
    - **Manage** development of complex applications
    - Design **reusability**
- In adition **organising** NgModules **enables lazy-loading**
    - Loading modules on demand
    - Minimize startup code.

## Components
- There is always **at least one** component: the **root** component
    - Connects the component hiearchy with the DOM.
- **Each** component **defines a class**
    - That contains:
        - Application Data
        - Application Logic
    - That Is associated with a HTML template
        - Defines the view to be displayed in the target environment
- **Decorated by @Component()**
    - The decorator identifies the class below it as a component
    - Provides the template and related component-specific metadata
### Decorators
- **Decorators** are functions that **modify** JavaScript **classes**.
    - These **attach** specific **metadata** to classes
    - This metadata **tells** the **system how the class should work**

## Templates, Directives and Data binding
- A **Template combines HTML** with **Angular markup**
    - Modifies elements before they are displayed
- Template **directives provide** program **logic**
- **Binding markup** connects the application data and the DOM
    - Two kinds of Data binding:
        - **Event** Binding:
            - **Respond** to user **input** by updating data
        - **Property** binding
            - **Alter values** computed by the application
- **Directives** are evaluated and **resolved before** a view is **display**ed
    - Angular supports **two-way data binding**
        - **Changes** in the DOM are **reflected** in the view
- **Pipes** are funcitons that **transform data for display**
    - To improve user experience
    - For example: ```<p>{{ price | currency }}</p>```

## Services and Dependency Injection

