**UML** is a standardized graphics language in software engineering used for visualization, specification, design and documentation of of systems (programs, databases, etc.). It offers standard ways of notation and supports [[Object-Oriented Programming (OOP)]] way of analysis. Its main goal is to help visualize, specify structures and behaviour of the systems. It help with decomposition of systems It allows for business processes, specific commands of a programming language, relations between class in OOP. UML diagrams are divided into three groups (ERD is not part of UML):
- **Structure** diagram
- **Behaviour** diagram 
- **Interaction** diagram
## Structure Diagram
Structure diagram describes a system and what it is made of. It represents the **static aspects** of a system. It highlights parts and components, that must be part of the modelled system. They are commonly used in documentation to describe a [[Software (SW)]] **system architecture**. Diagram components for example describes how software systems are divided into components and shows the relation between them.
### Class Diagram
A class diagram describes **classes** and **static relations** between them. It describes a system's static structure and highlights data structures. Each class is made up of its **name**, **a list of attributes** and **a list of methods**. Attributes and methods have their state visibility (+ public, - private, \# protected), attributes, types, input parameters and output types. Class diagram is described in a model space.
#### Multiplicity
Multiplicity of relations sets how many instances of one class can be tied with an instance of another class. This is described as:

| 0    | 0...1       | 1           | 0...*        | 1...*       |
| ---- | ----------- | ----------- | ------------ | ----------- |
| None | None or one | Exactly one | None or many | One or many |
#### Association
Association describes the basic class relationship between two entities. They can exist independent of each other. We can draw this as a simple full line. We can add a name to and multiplicity. Associations are binary (unary is also a gate as binary but reflexively). Other then binary associations are not recommended and can be replaced by another entity.
#### Generalization
It describes a relations of generalization or specialization between two classes. The derived class shared attributes, behaviour, relations and restrictions of the general class. Derived class can also be modified. We can represent this with an empty arrow at the of the line pointing at the general class.
#### Aggregation
Represents a free relation between a whole and a component, where the whole uses the function of the component. We can use an empty diamond at the whole side to represent this. 
#### Composition
Similar to aggregation, but the relation is stronger. The component does not have purpose without the whole and cannot exist. If the whole disappears then so does all his components. This is represented with a full diamond on the whole side.
#### Dependency
Is a weaker form of relation that signifies that one class is dependent on another. This relation can be expanded with a stereotype, that better specifies the relation. Dependency is drawn as a dashed line with a arrow at the end and stereotype is enclosed in `<<>>`. Some common stereotypes can be `<<use>>`, `<<create>>`, `<<send>>`, `<<call>>`, `<<trace>>`, `<<refine>>`. etc.
#### Realization
Describes a relation between a class and an interface. It signifies that the class implements the interface. The interface is drawn as a class with only methods and a sign `<<interface>>` above its head. Classes the implement this interface are connected to as with generalization but the line is dashed.
### Object Diagram
Object diagram is closely tied to the Class diagram and can highlight object and relations between them at a certain time. These relation are **dynamic** meaning they appear as if a they are a froze slice of a moment in the system. These diagrams are made in the same way Class diagrams are made, but only use the name of a class and the name of the instance of the class to represent it. For example `Karel:Osoba` or `123:Account`.
### Component Diagram
Component diagram shows how larger components of a system relations between each of them. These components can be physical, businesse, logic, etc.
### Group Diagram
Group diagram allows to group together semantically relevant elements and encapsulate a name space. For example classes that handle communication can be all grouped into one package.

## Behaviour Diagram
Behaviour diagrams describe how a certain system behaves or how the system works. These diagrams are a **dynamic**  aspects of the system. The highlight what can happen in a model space. They are commonly used to describe functionality of a [[Software (SW)]] system. Use-Case diagrams can for example show how a user in a certain role and the actions they have at their disposal.
### Use-Case Diagram
Diagram describes possible participants in the system as roles and what actions or functions they can do with the system. Some development strategies such as Use-Case driven development can use these as a basis for a system. The diagram is made of:
- **System Borders**
- **Participants** (Roles)
- **Use-Cases**
- **Interactions**
#### Association
Association in this sense refers to a role being connected to a use-case. Each role has to be connected to at least one use-case.
#### Generalization of Roles
Just line in Class diagram, a role can be generalized meaning there exists a general role and a specific role, with the specific role inheriting all of the use-cases of the general role.
#### Generalization of Use-Cases
Use-cases can be generalized as well, this time highlighting that specific use-cases have a common general use-case such as phone order and internet order have the same general use-case of place order.
#### Extend of Use-Cases
A relation between two use-cases that expands the functionality of a given use-case. The extended functionality does not have to take place.
#### Include of Use-Case
A relation between two use-cases that expand the functionality of a given use-case. This included functionality is mandatory.
#### Use-Case Details
A table that can serve to add details or make a use-case more specific with conditions and event flow.
### Activity Diagram
Activity diagram represents [[Object-Oriented Programming (OOP)|Object-Oriented]] **design diagram**. It allows to model:
- Scenarios of use-cases
- Algorithm details and operations
- Model businesse transactions
These diagrams are made of:
- **Nodes**
	- **Action nodes** - model activity
	- **Control nodes** - model decisions, conditions, start node, end node, etc.
	- **Object nodes** - model objects and their activities
- **Edges**
	- **Control edges** - model transitions between nodes
	- **Object edges** - model paths of objects between node
There diagram allow to model:
- Dataflows
- Decisions
- Branching and Unification
- Iterations
- Parallel flows
### State Diagram
State diagrams allow the modelling of a life cycle of one reactive object. It is a special case of [[Study Materials/Automata/Types/Automata]]. They can also model dynamic behaviour of classes, systems, sub-systems, etc. They are comprised of:
- **States**
- **Transitions (Edges)**
- **Events** can be condition in which a state changes. They can be part of the state.
#### Reactive Object
React on outside events and its life cycle can be modelled as a series of states, transitions and events. The behaviour of such object is dependent on its current state.
## Interaction Diagram
They a subset of Behaviour diagrams that model/describe interaction between individual components of a system including the users. They highlight control and data flow in model space. They can for example sequence diagrams that show how messages outside and inside the system are sent.
### Sequence Diagram
Sequence diagram show time oriented sequence of messages being sent between objects. This can be also described as the chronology of sent messages. They are more clear then Communication diagrams. They are comprised of:
- **Life Lines** that represent the time axis of a specific object.
- **Horizontal Lines** the represent messages sent between objects.
These diagrams can be extended with conditions, visible states, etc.
### Communication Diagrams
Communication diagrams highlight relations between objects and are commonly used for quick visualization of communication between objects. They are less clear from sequence diagrams. The object are connected through lines that signify entity relations. Messages between these objects are signified as arrows pointing at the direction of the messages and are usually labelled with number to keep track of which messages caused which and in which order.