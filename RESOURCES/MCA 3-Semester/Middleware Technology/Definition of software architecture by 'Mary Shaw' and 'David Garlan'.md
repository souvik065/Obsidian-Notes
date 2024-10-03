

***Software Architecture is the structure of software system like blue prints in building architecture.***

### **Software Architecture Consist of :**
- Software Components
- Details (Regrading Data-Structures and Components)
- Relationship among components
- Data Flow, Control Flow, dependency

### **Elements of Software Architecture**
- Component --> Abstract unit of software instruction and internal state which provides transformation of data.
- Connectors --> Communicate, Co-Operate, Among Component.
- Configuration Topologies --> Structure of Architectural Relationships
- System Models --> Architectural Styles

- Big Complex Project Needs Architecture


# Pipes and Filters

In Pipes and Filters we have a pipe in which the input comes and the filters are the component which apply transformation and produce the output and this output could be the input for the next filter and so on generally these filters are independent of each other, This filters are usable


# Advantages 

- **Modularity:** Each filter performs a specific task, making it easy to add or remove filters as needed. 

- **Reusability:** Filters can be reused in other parts of the application or system, reducing development time and cost. 

- **Scalability:** The architecture can handle increased processing needs by adding more filters to the pipeline. 

- **Flexibility:** Filters can be combined in different ways to create different processing pipelines. 

- **Easy to understand:** The overall input and output behavior of the system is easy to understand. 

- **Concurrent execution:** Improves performance. 


# Disadvantages 

- **Overhead and complexity:** Pipes need to be reliable and efficient, and data formats need to be compatible. 

- **Deadlock analyses:** The architecture supports deadlock analyses.