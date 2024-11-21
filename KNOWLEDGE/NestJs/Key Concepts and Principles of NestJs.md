 
# 1. Application

- We can create an HTTP Server application using the `NestFactory Create` , request endpoints and effectively create APIs and web servers.
- We can also create micro service Application using `NestFactory create microservice`

- We can also create standalone applications using `NestFactory create` application context.
- And a standalone application is just an application that doesn't have network listener, But they need a Root Module.

*Note:- Microservices are very similar to HTTP Servers except they can use different transport protocols* such as TCP or NATs, and they can communicate via a internal network

# 2. Modules 

In terms of the Implementation, a module is a class that is annotated  with a class that is annotated with a module decorator.

Modules are the building blocks of  a Nest Application.
So you can picture a Nest app as a graph made of modules, and at he top you always have a root module and that module can user other modules.
And those modules can themselves use other modules an so on.

- Modules are an effective way to organize components by a closely related set of capabilities.

- It is a good practice to have a folder per module, containing the module's components.

- Modules are **Singletons,** therefore a module can be imported by multiple other modules.

- **A module is defined by annotating a class with the `@Module` decorator.**
- **The decorator provides metadata that Nest uses to  organize the application structure.**

## Module  Decorator Properties

- **providers:** 
	- Array of provider to be available within the module via dependency injection.

- **controllers:** 
	- Array of controllers to be instantiated within the module.

- **exports:** 
	- Array of providers to export to other modules.

- **imports:** 
	- list of modules required by this module. Any exported provider by these modules will now be available in our module via dependency injection.


**Example :**
you could have a application with a product module, an order module that uses a cart and payment module, and they could all be using a shared configuration module.


**Note :**
*It's important to mention that while developing NSG applications you should try to treat your modules in an isolated way as much as you can.*
# 3. Decorators

Decorator is a special kind of function, and it can be attached to methods, classes, properties, and it modifies their behavior, and it can even add metadata.

Think of decorators of wearing accessories or suits that give you extra power.

- Decorators are typescripts feature that allows annotation of classes or class members such as methods or properties in order to add extra functionality.

**Note :**
*To create the application module graph you define relationship between modules by passing an object property to the module decorators, and you define the related modules in the import property*


# 4. Controller

Controller are classes that are annotated with the controller decorator.
So let's say that they are wearing a blue jacket.
A controller is simply in charge of receiving incoming requests and returning a response.

The main role of the controller is to receive request and return response and Anything else is delegated to other classes. 

- Controllers are Responsible for handling incoming **requests** and returning **responses** to the client.
- Bound to a specific **path** (for example, "/tasks" for the task resource).
- Contain **handlers**, which handle **endpoints** and **request methods** (GET, POST, DELETE etcetera)
- Can take advantage of **dependency injection** to consume providers within the same module.

## **Defining a controller**

Controller are defined by decorating a class with the `@Controller` decorator.

The decorator accepts a string, which is the **path** to be handler by the controller.

```javascript
@Controller('/tasks')
export class TaskController {
	// ...
}
```


## **Defining a Handler**

Handler are simply methods within the controller class, decorated with decorators such as `@Get`, `@Post`, `@Delete` etcetera.

```javascript
@Controller('/tasks')
export class TasksController{
	@Get()
	getAllTasks(){
		// do stuff
		return ...;
	}
	
	@Post()
	createTask(){
		// do stuff
		return ...;
	}
}
```


# 5. Providers

Most of the code that we will be writing in NetsJs is within providers.

So a provider is simply a class that can be injected in other classes as dependency

So we can think of providers as freelance worker and NestJs is an agency that places those freelance workers wherever they are needed.

 - Providers can be injected into constructors if decorated as an `@Injectable`, via **dependency injection**. 
- Can be a plan value, a class, sync/async factory etc.
- Providers must be provided to a module for them to be usable.
- Can be exported from a module - and then be available to other modules that import it.

## **What is Service ?**

- Services are defined as providers. **Not all providers are services.** 
- Common concept within software development and are not exclusive NestJS, Javascript or back-end development.
- Singleton when wrapped with `@Injectable()` and provided to a module . That means, the same instance  will be shared across the application - acting as a single source of truth.
- The main source of business logic. For example, a service will be called from a controller to validate data, create an item in the database and return a response.

```javascript
import { Module } from '@nestjs/common';
import { UsersService } from './users.service';
import { UsersController } from './users.controller';

@Module({ 
		controllers: [UsersController],
		providers: [UsersService], 
		
}) 
	
export class UsersModule {}
```


# Dependency Injection in NestJs

Any component within the `NestJS` ecosystem can inject a provider that is decorated with the `@Injectable`

We define the dependencies in the constructor of the class. `NestJS` will take care of the injection for us, and it will then be available as a class property.

```javascript
import {TaskService} from './tasks.service'

@Controller('/tasks')
export class taskController{
	constructor(private taskService: taskService) {}

	@Get()
	async getAllTasks(){
	return await this.taskService.getAllTasks();
	}
}
```

**Resources :**
[NestJs Concept Explained in 9 Minutes](https://www.youtube.com/watch?v=IdsBwplQAMw)

