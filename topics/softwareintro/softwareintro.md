[Go to wiki](./../../README.md)

# Software Introduction

- [Software Introduction](#software-introduction)
  - [What are some considerations to have with software?](#what-are-some-considerations-to-have-with-software)
  - [What are the phases of software development?](#what-are-the-phases-of-software-development)
  - [How to assess requirements?](#how-to-assess-requirements)
  - [What is OO Analisys?](#what-is-oo-analisys)
  - [What is Domain Model?](#what-is-domain-model)
  - [How to identify conceptual classes?](#how-to-identify-conceptual-classes)
  - [How to identify associations?](#how-to-identify-associations)
  - [How to identify attributes?](#how-to-identify-attributes)
  - [What is OO Design?](#what-is-oo-design)
  - [What is Responsability-Driven Design (RDD)?](#what-is-responsability-driven-design-rdd)
  - [What is General Responsability Assignment Software Patterns (GRASP) ?](#what-is-general-responsability-assignment-software-patterns-grasp-)
    - [Information expert principle](#information-expert-principle)
    - [Creator principle](#creator-principle)
    - [Controller principle](#controller-principle)
    - [Low Coupling principle](#low-coupling-principle)
    - [High Coesion principle](#high-coesion-principle)
    - [Polymorphism principle](#polymorphism-principle)
    - [Indirection principle](#indirection-principle)
    - [Pure Fabrication principle](#pure-fabrication-principle)
    - [Protected Variations principle](#protected-variations-principle)
- [Sources](#sources)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>



## What are some considerations to have with software?


Software is intangible, unusually flexible, non-standardized. Software engineering is not recognized like an engineering like other areas like mechanic, eletric, civil, etc. Still, it is necessary to introduce methods, models and processes that lead to a consistent and efficent development of software due to its importance on a current daily basis.

![software development phases](/topics/softwareintro/images/phasessoftware.png)

[Back to top](#software-introduction)

## What are the phases of software development?

**Requirements**
Identify what the stakeholders want from the software and establish the restrictions. 

**Analisys**
*Do the right thing*.
Assessment of the requirements and explore the details. 
e.g. requiremente analisys or OO analisys.

**Design**
*Do the thing right*.
Conceptual solution that expects to accomplish the requirements.
Can lead to implementation but it is not implementation.
e.g. architecture design, use case OO design, database design.

**Implementation**
*Build the thing*.

[Back to top](#software-introduction)

## How to assess requirements?

**Vision**
Vision includes the great ideas for the project:
- The reason for the project;
- What are the problems;
- The stakeholders;
- The needs;
- The perspective for a solution.

**Use cases** can help define and communicate a use case requirements to explain the needs for the software. It describes the scenery of a problem that the software wants to solve. This can be described in text form or with the use of UML. e.g. use case diagram, system sequence diagrams

[Back to top](#software-introduction)

## What is OO Analisys?

Think in objects:
- Attributes (data);
- Relationships (with other objects);
- Behaviour.

OO analisys seeks to assess the domain objects in a domain object model. It intends to turn the requirements into an aproximate representative design.

[Back to top](#software-introduction)

## What is Domain Model?

Domain model is a an artefact of *Business Model* that is a UML representation of **conceptual classes** or real  domain objects of interest (not of software elements). This means that concepts classes like *Person* or *Car* are represented in domain model but a *ListOfCars* that only exists to store that (given that it is not a specified requirement) is not represented in Domain Model because it is purely an abstract class of the software.

Domain model serves to identify:
- Main concepts;
- Their attributes;
- Association between concepts.

[Back to top](#software-introduction)

## How to identify conceptual classes?

There are no hardlines or rules to do this. Look for classes that are along these lines:

![conceptual classes ](./images/conceptualclasses.png)

![conceptual classes examples](./images/conceptualClasses2.png)

[Back to top](#software-introduction)

## How to identify associations?

An association is a relationship between instances of objects that shows a relevant connection between them. Here are the more common associations:
- *A* is physically (or logically) part of *B*;
- *A* is physically (or logically) contained in *B*;
- *A* is a description of *B*;
- *A* is know/captured/registred by *B*;
- *A* uses or manages *B*;
- *A* is related with a transaction of *B*.

There are more possible associations but these are some of the most common. Try to look for possible associations using common sense and attending the requirements.

Example of associations between concepts:

![associations between concepts](./images/associations.png)
![associations between concepts example](./images/associations2.png)

[Back to top](#software-introduction)

## How to identify attributes?

Attributes in a domain model should be: 
- Simple
- Primitive
e.g.: 
*Common types*: boolean, date, number, string, text, time.
*Other types*: address, color, geometry, phone number, ID.

Attribute should be represented as a conceptual class *IF*:
- Attribute is made of various concepts: (e.g. Address: Street, number, country);
- Has associated operation (e.g. Parsing);
- Has other attributes;
- Is an abstraction of one or more types (e.g. Universal Product Code, EAN).

![Attributes](./images/attributes.png)

**Relationships between concepts should not be represented by attributes!**

Common mistakes:

![common mistakes relationships between concepts](./images/relationshipscommonmistakes.png)

[Back to top](#software-introduction)

## What is OO Design?

OO design is taking the requirements in account to build a design solution for the development of software. This includes using UML tools to design:

- **Static view**: 
  - *Class diagrams*.
- **Dinamic view**: *Interaction diagrams* like:
  - *Colaboration diagrams*
  - *Sequence diagrams*.

![design diagrams](./images/designdiagrams.png)

OO Design is based on **Responsability-Driven Design (RDD)**. It is a principle that helps design the software according to the responsability that should be attributed to each object.

Other principles like **GRASP**, **SOLID** and **GoF** should be used during the design and code. These are the **design patterns** that seek to **attribute responsability** in OO.

[Back to top](#software-introduction)

## What is Responsability-Driven Design (RDD)?

Responsability-Driven Design is principle that helps in the process of software design. This principle states that **objects have responsabilities** - responsabilities being and abstraction of what they do, in similarity to real life object (e.g. A person talks and walks). Responsabilities are obligations and behaviours of an object in the part they are given. It is simply thinking of objects in the same way we think of a person with responsabilities colaborating with other people colaborating with each other, with different responsabilities.

*Note*: Responsability is no the same thing as a method. It is simply an abstraction. Methods implement responsabilities. 

An object can have the responsability to:
- **To Know**: Know its private information, related objects, know how to obtain or calculate a new information.
- **To Do**: To do something, criate an object, do calculations, initiate actions in other objects, control and coordenate activities in other objects.

e.g. 
- A center of exhibitions has the responsability to create an exhibition.
- An exhibition has the responsability to know the date of exhibition.

*RDD* includes the idea of *colaboration*, that is, the idea that responsabilites are implemented through methods that act alone or colaborate with other methods or objects. 

[Back to top](#software-introduction)

## What is General Responsability Assignment Software Patterns (GRASP) ?

Grasp are patterns/principles for OO Design. They intend to aid the decision making process of responsability attribution when designing OO software.

Grasp patterns:

### Information expert principle

*Problem*: What is the general principle to that attributes responsability to objects?

*Solution*: Attribute responsability to the *information expert*

The *information expert* is the class that **contains** all the **necessary information to perform that responsability**.
Usually, the information is distributed along multiple classe, that makes interaction/colaboration necessary between various object through messages.

*Disadvantages*: The use of the *information expert* principle can **sometimes lead to high copling and low coesion** problems because of the necessary colaboration between multiple classes.

e.g. Exhibition responsability:

![Exhibition responsability](./images/exhibitionresponsability.png)

[Back to top](#software-introduction)

### Creator principle

*Problem*: Who should be responsible for creating object os a class?

*Solution*: Class *B* should have the responsability to create instances of class *A* in the following situations:

- *B* contains or aggregates objects of class *A*
- *B* registers instances of class *A*
- *B* has the data used to initialize *A*
- *B* is directly related to *A*

If more than one condition applies, the first condition should be chosen "*B* contains or aggregates objects of class *A*".

The creator pattern looks to attribute the responsability to create an object. It looks for relationships of *aggregation*, *composition* and *register*. The chosen creator should have all the necessary information to create the object. We should be aware that relationship between creator and created implies a highger coupling between those two classes. 

*Disadvantages*: Sometimes the creation of objects can be very complex. In that scenery it might be mode advantageous to delegate that responsability to other classes (e.g. *Factory*).

e.g. of Creator Pattern in a Exhibition:
Following the creator pattern, the class *Exhibition* should have the responsability to create *Organizer* because the *Exhibition* contains or aggregates *Organizer*. The class *Exhibition* should contain a method *addOrganizer(user)*.

[Back to top](#software-introduction)

### Controller principle

### Low Coupling principle

### High Coesion principle

### Polymorphism principle

### Indirection principle

### Pure Fabrication principle

### Protected Variations principle


---

# Sources
PP ESOFT 2015-2016 Requisitos, analise e design (Switch)

[Back to top](#software-introduction)

---

[Go to wiki](./../../README.md)




