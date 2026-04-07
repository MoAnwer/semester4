---
banner: "pixel-banner-images/ar.jpg"
banner-radius: 5
tags:
  - "#sheets"
  - software
---
## Introduction to Architectural Design

Architectural design is a crucial stage in software engineering that focuses on organizing the overall structure of a software system. It bridges the gap between requirements engineering and detailed design by identifying the main components of a system and their interrelationships. The output of this process is an architectural model, which outlines how the system is structured as a collection of communicating components.

### Agility and Architecture

While agile processes emphasize iterative development, establishing an overall system architecture early on is generally accepted as beneficial. Refactoring an established architecture is typically very costly due to its widespread impact on numerous system components.

### Architectural Abstraction

- **Architecture in the Small:** Deals with the architecture of individual programs, focusing on how a single program is decomposed into components.
- **Architecture in the Large:** Concerns the architecture of complex enterprise systems that often involve multiple interconnected systems, programs, and components distributed across various computers, potentially under different management.

### Advantages of Explicit Architecture

- **Stakeholder Communication:** Provides a clear focus for discussions among system stakeholders.
- **System Analysis:** Enables the analysis of whether the system can meet its non-functional requirements.
- **Large-Scale Reuse:** The architecture itself can be reused across multiple systems, or product-line architectures can be developed.

### [[Architectural Representations]]

- **Block Diagrams:** Simple, informal diagrams showing entities and relationships are common but can lack semantic richness, failing to specify relationship types or entity properties.
- **Architectural Models:** The required level of semantic detail in models depends on their intended use, whether for discussion or complete documentation.
- **Box and Line Diagrams:** Highly abstract, useful for stakeholder communication and project planning, but do not detail component relationships or properties.

## Architectural Design Decisions

Architectural design is a creative process that varies with system type. However, several common decisions significantly impact the system's non-functional characteristics.

Key architectural design decisions include:

- Identifying a generic application architecture that can serve as a template.
- Determining the fundamental approach to structuring the system.
- Deciding how the system will be distributed across hardware cores or processors.
- Selecting appropriate architectural patterns or styles.
- Choosing a strategy for controlling component operations.
- Defining how structural components will be decomposed into sub-components.
- Determining the best architectural organization to meet non-functional requirements.
- Establishing the method for documenting the system's architecture.

### Architecture Reuse

Systems within the same domain often share similar architectures reflecting domain-specific concepts. Application product lines are built upon a core architecture with variations. Architectural patterns or "styles" capture essential architectural concepts that can be instantiated in different ways.

### Architecture and System Characteristics

- **Performance:** Localize critical operations, minimize communication, and use larger, rather than finer-grained, components.
- **Security:** Employ a layered architecture with critical assets placed in inner layers.
- **Safety:** Isolate safety-critical features within a small number of subsystems.
- **Availability:** Incorporate redundant components and fault-tolerance mechanisms.
- **Maintainability:** Utilize [[fine-grained]], replaceable components.

## Architectural Views

Architectural models typically present only one perspective of a system. To fully describe and document an architecture, multiple views are often necessary, offering different insights into the system's structure.

Common [[architectural views]] include:

- **Logical View:** Depicts the key abstractions in the system as objects or classes.
- **Process View:** Illustrates how the system is composed of interacting processes at runtime.
- **Development View:** Shows how the software is decomposed for development purposes.
- **Physical View:** Represents the system's hardware and the distribution of software components across processors.

The **4+1 View Model** integrates these views, using use cases or scenarios (+1) to relate them.

### Representing Architectural Views

- **Unified Modeling Language (UML):** While some consider UML suitable for architectural description, its abstractions may not be ideal for high-level system descriptions.
- **Architectural Description Languages (ADLs):** Specialized languages for describing architectures exist but are not widely adopted.

## Architectural Patterns

Patterns are a mechanism for representing, sharing, and reusing knowledge. An architectural pattern is a stylized description of good design practice, tested across various environments. Patterns should include guidance on when they are and are not applicable.

### Model-View-Controller (MVC) Pattern

- **Description:** Separates presentation and interaction from system data. It comprises three logical components:
    - **Model:** Manages system data and associated operations.
    - **View:** Defines and manages how data is presented to the user.
    - **Controller:** Handles user interactions and communicates them to the View and Model.
- **When Used:** When multiple ways to view and interact with data are required, or when future interaction/presentation requirements are uncertain.
- **Advantages:** Allows data and its representation to change independently; supports presenting the same data in different ways, with changes reflected across all.
- **Disadvantages:** Can introduce extra code and complexity for simple data models and interactions.

### Layered Architecture Pattern

- **Description:** Organizes the system into layers, each providing services to the layer above it. Core services are typically in the lowest layers.
- **When Used:** For building on existing systems, when development is spread across teams responsible for different layers, or when multi-level security is required.
- **Advantages:** Supports layer replacement if interfaces are maintained; allows redundant facilities for increased dependability.
- **Disadvantages:** Clean separation between layers can be difficult; performance can be affected by multiple levels of interpretation.

A generic layered architecture typically includes:

- User interface
- User interface management
- Authentication and authorization
- Core business logic/application functionality
- System utilities
- System support (OS, database, etc.)

### Repository Architecture Pattern

- **Description:** All system data is managed in a central repository accessible by all components. Components interact solely through the repository.
- **When Used:** For systems with large volumes of data to be stored long-term, or in data-driven systems where data inclusion triggers actions.
- **Advantages:** Components can be independent; changes propagate to all components; data management is consistent.
- **Disadvantages:** The repository is a single point of failure; may lead to inefficiencies in communication; distributing the repository can be challenging.

### Client-Server Architecture Pattern

- **Description:** A distributed system model where functionality is organized into services delivered by servers, accessed by clients via a network.
- **When Used:** For accessing shared databases from multiple locations, or when system load is variable.
- **Advantages:** Servers can be distributed; general functionality can be widely available.
- **Disadvantages:** Each server is a single point of failure; performance can be unpredictable; management can be complex if servers are managed by different organizations.

### Pipe and Filter Architecture Pattern

- **Description:** Data processing is organized into discrete components (filters) that perform specific data transformations. Data flows sequentially through these components (pipes).
- **When Used:** Primarily in data processing applications (batch and transaction-based) where input is processed in stages.
- **Advantages:** Easy to understand, supports transformation reuse, straightforward evolution by adding filters, can be sequential or concurrent.
- **Disadvantages:** Requires agreement on data transfer formats between filters; can lead to overhead due to parsing/unparsing; incompatible data structures can prevent reuse.

## Application Architectures

Application systems are designed to meet specific organizational needs. Due to commonalities in business, application systems often share common architectures. A generic application architecture serves as a configurable template.

### Use of Application Architectures

- As a starting point for architectural design.
- As a design checklist.
- To organize development team work.
- To assess components for reuse.
- As a vocabulary for discussing application types.

### Examples of Application Types

- **Data Processing Applications:** Batch-driven, processing data without user intervention during execution.
- **Transaction Processing Applications:** Data-centered, processing user requests and updating a system database.
- **Event Processing Systems:** System actions are triggered by interpreting environmental events.
- **Language Processing Systems:** Interpret input specified in a formal language to perform actions or generate other representations.

#### Transaction Processing Systems

These systems process user requests to access or update a database. A transaction is a coherent sequence of operations achieving a goal. Users make asynchronous service requests handled by a transaction manager.

A typical structure includes:

- I/O processing
- Application logic
- Transaction manager
- Database

#### Information Systems Architecture

Information systems often follow a layered architecture, being transaction-based. Layers typically include:

- The user interface
- User communications
- Information retrieval
- System database

#### Web-Based Information Systems

Modern information systems are frequently web-based, with user interfaces in web browsers. E-commerce systems are an example, managing electronic orders and deliveries. These systems often use multi-tier client-server architectures:

- **Web Server:** Handles user communications and the browser-based UI.
- **Application Server:** Implements application logic and manages information storage/retrieval.
- **Database Server:** Manages data movement and transaction processing.

#### Language Processing Systems

These systems translate input from one language to another or execute instructions within the input language. They often include a translator and an interpreter.

A typical language processing system architecture involves:

- **Translator:**
    - Lexical analyzer
    - Syntax analyzer
    - Semantic analyzer
    - Code generator
- **Interpreter:**
    - Abstract machine
    - Fetch and execute cycle
- **Supporting Components:**
    - Symbol table
    - Syntax tree

Common compiler components include:

- Lexical analyzer
- Symbol table
- Syntax analyzer
- Syntax tree
- Semantic analyzer
- Code generator