

# **Callbacks**
### 1. **Flexibility**

Callbacks provide a high degree of **flexibility** in how functions are executed, especially when dealing with asynchronous or event-driven tasks. Since a callback is a function passed as an argument, the same function can be written to accept different callbacks, making it adaptable to various scenarios.

#### Key Benefits of Flexibility:

- **Customizable behavior**: You can customize how a function behaves based on the callback you pass, allowing the same function to perform different actions depending on the situation.
- **Modular code**: You can separate concerns in your code by writing reusable functions that do a general task and leave the specifics (defined by callbacks) to be handled elsewhere.


### 2. **Asynchronous Operations**

A core use case of callbacks is in handling **asynchronous operations**. In programming, especially in environments like Node.js, many operations are non-blocking. Callbacks allow the system to continue executing other tasks while waiting for an operation to complete (e.g., a network request or reading a file), and when the operation finishes, the callback is invoked with the result.

#### Benefits for Asynchronous Operations:

- **Non-blocking**: The program does not stop or wait for an operation to finish (e.g., an API call or file read); instead, the callback is executed once the operation completes.
- **Concurrency**: While one task is waiting for an event (like a file read or API response), other tasks can be processed concurrently, improving performance.

### 3. **Event-Driven Programming**

**Event-driven programming** is a paradigm in which the flow of the program is determined by events such as user interactions, system signals, or sensor outputs. Callbacks are essential in this model because they allow you to specify what should happen when a particular event occurs.

#### How Callbacks Work in Event-Driven Programming:

- **Registering event handlers**: Callbacks can be attached to specific events (e.g., a button click, a key press, or data reception over the network), so when the event occurs, the callback function is executed automatically.
- **Decoupling logic**: The logic that handles events (callbacks) can be separated from the event detection mechanism, making the code cleaner and more maintainable.



# Callback Functions and Asynchronous Programming

**Callback Registration** refers to the process of associating or "registering" a callback function with a particular event or operation.

This means that when the event occurs or the operation completes, the registered callback will be automatically executed. Callback registration is a key concept in **event-driven programming** and **asynchronous operations**, enabling a system to handle various tasks without blocking the main flow of execution.


# Directory Services

**Directory Services** are specialized network services used to store, organize, and provide access to information about various network resources such as users, devices, applications, and services.


1. **User Authentication**: Directory services authenticate users by verifying their credentials (username, password, etc.).
2. **Policy Enforcement in Directory Services**:  refers to the application of rules and controls that dictate how users, devices, and applications interact with the resources in a directory service.


# LDAP: Lightweight Directory Access Protocol

A directory tells you where in the network something is located
LDAP extracts information in a usable format from active Directory - Which contains attributes behind every user account on the network. 

LDAP organized a tree like hierarchy with multiple levels to narrow down the search results.

Root Directory --> Countries --> Organizations --> Organizational Units --> Individuals

