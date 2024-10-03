

# What is UML ?

UML (Unified Modeling Language) is a standardized modeling language used in software engineering for visualizing, specifying, constructing, and documenting the components of a software system.


# Why UML ?

The UML enables system builders to create “blueprints” that capture their visions in  a standard , easy-to-understand way and communicate them to others.



# Basic Building Blocks of UML

The Vocabulary of UML encompasses three kinds of building blocks. They are,

1. Things 
2. Relationships
3. Diagrams


**"Things “**  form the vocabulary(Nouns) of a system and they are the abstractions of a particular model,
**“ Relationships “** tie the things together, **“ Diagrams “** group related things  together.


### 1. **Things**

Things are the primary elements used to model various aspects of a system. They can be classified into the following types:

- **Structural Things**: Represent static parts of the model.
    
    - **Class**: Represents a blueprint for objects (with attributes and operations).
    - **Interface**: Specifies a contract of methods that a class or component must implement.
    - **Collaboration**: Defines an interaction between elements.
    - **Use Case**: Describes a function that the system performs for an actor.
    - **Component**: Represents a modular part of the system that encapsulates behavior.
    - **Node**: A physical element in a system (like hardware or software execution environments).
    - **Object**: An instance of a class showing specific values at a moment in time.
- **Behavioral Things**: Represent the dynamic aspects of the system.
    
    - **Interaction**: Defines the behavior among elements.
    - **State Machine**: Describes the states an object or system can be in and transitions between them.
- **Grouping Things**: Used to organize elements within a model.
    
    - **Package**: A way to group related elements (such as classes, interfaces, and other packages).
- **An-notational Things**: Provide comments or notes in a model.
    
    - **Note**: A comment that explains or clarifies part of a diagram.


### 2. **Relationships**

Relationships describe how things connect and interact with each other. These are crucial for defining the interaction and structure of the system.

- **Association**: Represents a relationship between two elements (e.g., a relationship between two classes).
- **Dependency**: Shows that one element depends on another.
- **Generalization**: Defines an inheritance relationship (e.g., a subclass inherits from a parent class).
- **Realization**: Specifies that one element fulfills the contract of another (common between interfaces and implementing classes).
- **Aggregation/Composition**: Special types of associations representing whole-part relationships. Composition indicates stronger ownership than aggregation.

### 3. **Diagrams**

Diagrams provide visual representations of the model. UML includes 14 types of diagrams, which are divided into two main categories:

- **Structure Diagrams**: Show the static aspects of the system.
    
    - **Class Diagram**
    - **Object Diagram**
    - **Component Diagram**
    - **Deployment Diagram**
    - **Package Diagram**
    - **Composite Structure Diagram**
- **Behavior Diagrams**: Capture the dynamic behavior of the system.
    
    - **Use Case Diagram**
    - **Sequence Diagram**
    - **Activity Diagram**
    - **State Machine Diagram**
    - **Communication Diagram**
    - **Interaction Overview Diagram**
    - **Timing Diagram**


