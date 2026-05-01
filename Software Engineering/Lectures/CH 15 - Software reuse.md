---
tags:
  - software
  - software-reuse
---


## Introduction to Software Reuse

Software reuse-based engineering is a development strategy focused on utilizing existing software. This approach has become prevalent due to demands for reduced development and maintenance costs, faster delivery, and improved software quality. Companies view software as an asset and aim to increase their return on investment through reuse.

### Availability of Reusable Software

Reusable software is available in various forms:

- **Open-Source Movement:** Provides a vast codebase for reuse, including program libraries and entire applications.
- **Domain-Specific Application Systems:** Pre-built systems like ERPs that can be tailored to specific customer needs.
- **Reusable Components from Companies:** Some large organizations offer reusable components to their customers.
- **Standards:** Technologies like web service standards facilitate the development and reuse of software services across applications.

### Levels of Reuse

Software units can be reused at different scales:

1. **System Reuse:** Entire systems, potentially composed of multiple applications, are reused as part of a larger "system of systems."
2. **Application Reuse:**
    - Incorporating an application without modification into other systems.
    - Configuring an application for different customers.
    - Utilizing application families or software product lines with a common architecture, adapted for specific customer requirements.
3. **Component Reuse:** Subsystems or individual objects within an application can be reused. For example, a pattern-matching system from a text processor could be reused in a database management system. Components can be cloud-hosted or on private servers and accessed via APIs as services.
4. **Object and Function Reuse:** Small software units like single functions (e.g., mathematical operations) or object classes are reused. This is common with standard libraries and has been practiced for decades. Libraries of functions and classes are often freely available and linked with new application code. This is particularly cost-effective for specialized areas requiring expert knowledge, such as mathematical algorithms or graphics.

### Adaptations for Reuse

Software development processes must be adapted to accommodate reuse:

- **Requirements Refinement:** Requirements are modified to align with available reusable software.
- **Design and Implementation:** Explicit activities are included to search for and evaluate candidate components for reuse.

## The Reuse Landscape and Key Considerations

The "reuse landscape" encompasses various techniques for implementing software reuse, acknowledging that systems in the same domain share similarities and that reuse is possible at multiple levels. Standards for reusable components further facilitate this.

### Factors Influencing Reuse Strategy Choice

The most appropriate reuse technique depends on several factors:

1. **Development Schedule:** For rapid development, reusing complete systems is preferable, even with minor requirement mismatches, as it minimizes development effort.
2. **Expected Software Lifetime:** For long-lived systems, maintainability is crucial. The long-term implications of reuse must be considered, including adapting the system to future requirements. If source code access is limited, proprietary off-the-shelf components might be risky due to potential lack of support. Open-source options offer more control as source code is accessible.
3. **Development Team Expertise:** Reuse technologies can be complex. Efforts should focus on areas where the team possesses expertise to ensure effective understanding and utilization.
4. **Software Criticality and Non-Functional Requirements:**
    - **Critical Systems:** For systems requiring certification (e.g., safety or security cases), access to source code is often necessary, making reliance on proprietary components difficult.
    - **Performance Requirements:** Strategies like Model-Driven Engineering (MDE), which generate code from models, can sometimes produce inefficient code, potentially failing to meet stringent performance demands.
5. **Application Domain:** Many domains (e.g., manufacturing, medical systems) have generic, configurable products that are often more cost-effective to purchase than to build from scratch.
6. **Platform:** Some components or systems are platform-specific (e.g., .NET on Microsoft platforms). Reusability may be limited to systems designed for the same platform.

### Managerial and Technical Aspects of Reuse

Achieving reuse is often more a managerial challenge than a technical one. Managers might be reluctant to compromise requirements or may underestimate the risks of reuse compared to original development. Promoting company-wide reuse may require establishing dedicated reuse programs.

## Frameworks for Reuse

Frameworks are a powerful approach to reuse, particularly in object-oriented development.

### What is a Framework?

A framework is a generic structure that is extended to create more specific subsystems or applications. It provides an integrated set of software artifacts (classes, objects, components) that collaborate to offer a reusable architecture for a family of related applications.

- **Functionality:** Frameworks offer support for common features likely to be used across similar applications (e.g., user interface frameworks provide event handling and widgets).
- **Extensibility:** Developers specialize frameworks by adding specific functionality.
- **Design Reuse:** Frameworks offer a skeleton architecture and reusable classes, often implemented using object-oriented principles like inheritance and polymorphism.
- **Implementation:** Frameworks are typically implemented in object-oriented languages (Java, C#, C++, Ruby, Python) and can incorporate other frameworks. They can be used to build entire applications or specific parts.

### Web Application Frameworks (WAFs)

WAFs are widely used for building dynamic websites. They often follow the Model-View-Controller (MVC) pattern, which separates data (Model) from its presentation (View) and user interaction logic (Controller).

Key features of WAFs:

- **Security:** Support for user authentication and access control.
- **Dynamic Web Pages:** Classes for defining templates and populating them with data.
- **Database Integration:** Abstract interfaces to various databases.
- **Session Management:** Classes for creating and managing user sessions.
- **User Interaction:** Support for technologies like AJAX and HTML5 for interactive and responsive interfaces, often with device-independent adaptability.

### Inversion of Control

In framework-based development, the framework, rather than the application-specific code, often controls the flow of execution. This is known as "inversion of control." Framework objects invoke "hook methods" that link to user-provided functionality, allowing the application to respond to events.

### Types of Frameworks

Beyond WAFs, other framework categories exist:

1. **System Infrastructure Frameworks:** Support the development of system infrastructure (e.g., communications, user interfaces, compilers).
2. **Middleware Integration Frameworks:** Provide standards and classes for component communication and information exchange (e.g., .NET, Enterprise Java Beans - EJB).
3. **Enterprise Application Frameworks:** Focus on specific application domains (e.g., finance, telecommunications), embedding domain knowledge. These are less common now, often superseded by software product lines.

### Challenges with Frameworks

- **Cost and Complexity:** Frameworks are expensive to introduce due to their inherent complexity and learning curve.
- **Evaluation:** Choosing the right framework can be difficult and costly.
- **Debugging:** Debugging can be more challenging as developers may not fully understand the framework's internal workings.

## Software Product Lines

Software product lines are an ==effective reuse approach when supporting multiple similar but distinct systems.==

### Definition and Benefits

A software product line is a set of applications sharing a common architecture and components, with each application specialized for specific customer requirements.

- **High Reuse:** A significant portion of code is reused across applications.
- **Simplified Testing:** Test cases for common parts can be reused.
- **Domain Expertise:** Engineers develop specialized knowledge within the product line's domain.

### Emergence and Evolution

Product lines often evolve from existing applications. Initially, code is informally reused. Over time, as more instances are developed, the structure can degrade. A conscious decision to design a generic product line is then made, identifying common functionality and building a base application.

### Structure of a Base Application

A base application in a product line typically includes:

1. **Core Components:** Provide infrastructure support and are generally not modified.
2. **Configurable Components:** Can be modified or configured (sometimes without code changes via a configuration language) to specialize them.
3. **Specialized Components:** Domain-specific components that may be replaced or modified for new instances.

### Frameworks vs. Software Product Lines

|Feature|Application Frameworks|Software Product Lines|
|:--|:--|:--|
|**Extension Mechanism**|Relies on OO features (inheritance, polymorphism). Framework code is usually not modified.|Components are changed, deleted, or rewritten. Fewer restrictions on modifications.|
|**Scope**|Generally provide general support (e.g., for web applications).|Embed detailed domain and platform information (e.g., health record management for web).|
|**Hardware Interaction**|Typically software-oriented; usually do not include hardware interaction components.|Often control applications for equipment, requiring hardware interfacing support.|
|**Ownership**|Can be developed by external parties.|Typically owned by a single organization, forming a family of related applications.|

### Product Line Development Process

Developing applications by adapting a generic version involves configuring components, implementing new ones, and modifying existing ones. When creating a new application, the starting point is often the closest existing member of the family, rather than solely the generic core.