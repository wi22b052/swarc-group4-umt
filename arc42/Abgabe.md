# 

**About arc42**

arc42, the template for documentation of software and system
architecture.

Template Version 8.2 EN. (based upon AsciiDoc version), January 2023

Created, maintained and © by Dr. Peter Hruschka, Dr. Gernot Starke and
contributors. See <https://arc42.org>.

<div class="note">

This version of the template contains some help and explanations. It is
used for familiarization with arc42 and the understanding of the
concepts. For documentation of your own system you use better the
*plain* version.

</div>

<div style="page-break-after: always;"></div>

# Introduction and Goals

The following document gives a detailed overview of goals, features, functionalities, architectural decisions, etc. 
Also assumptions as well as reasonings for certain decisions are documented here for future reference. 

In the end, the delivered product should:
-   make communication between students and the falculty as well as its employees easier
-   be easy to use without any training for all parties
-   drastically lower the organizational overhead
-   secure private data
-   enable data-driven decision making through reporting and analytics

To make this possible important features are:
-   dashboard with relevant information
-   Course and curriculum management (before, during and after the course)
-   User authentication
-   Billing and payment management
-   Reports and Analytics

Quality goals which influence architectural decisions:
-   Usability (Easy access and usage; No training required)
-   Correctness (To ensure no wrong distribution of information/data)
-   Interoperability (Communication with software of other institution)

The main stakeholders for this projekt (with their most valued expectation/s) are:
-   Senior Lecturer/Jane Doe (Efficiency; Ease the workload;)
-   Student Rep./ Emily Chen (Proper User Experience; Ease the communication; Data protection)
-   Financial Officer/Sarah Johnson (Create revenue of subscription fees)
-   Chief Information Officer/Michael Lee (Ease the protection of student and lecturer data)

## Requirements Overview
<div class="formalpara-title">
 
 **Dashboard with relevant information**
 
 </div>
 
To make strategic decisions, information and data is crucial. Therefore, the university management application needs to make those not just available, but also displays them in an adequate manner. 


<div class="formalpara-title">
 
**Course and curriculum management**

</div>

The organisation of the courses and the curriculum represent two crucial parts of day to day life in an university. The software need to support the employees here and automate as much process steps as possible.


<div class="formalpara-title">
 
**User authentification**

</div>

The university has to handle the personal data of the students as well as of employees. To make sure, that noone can access someoneelses account and data user authentification need to be implemented.



<div class="formalpara-title">
 
**Billing and payment management**

</div>

This application supports the falculty and students whenever they have to interact with eachother. Therefore also a billing and payment management system will be implemented. 


<div class="formalpara-title">
 
**Reports and Analytics**

</div>

Defined reports will be generated periodically. Also certain tools for further analysing the collected data will be accessable, to make (for exmaple) additional dashbords possible.

## Quality Goals

<div class="formalpara-title">

**Usability**

</div>

The main goal of this applications is making the day to day life of students as well as employees easier. Therefore it must not be necessary to have a training to be able to work with the university management tool. Everytime person who has to fullfill a task which involes this application should be able to it without any detailed instructions.


<div class="formalpara-title">

**Correctness**

</div>

This tool works with personal data of many individuals. Therefore it is required by law to handle those information carefully. However, also data like grades, dates of tests as well as timetables are crucial for day to day life at a university and needs to be accessible and correct at all times.


<div class="formalpara-title">

**Interoperability**

</div>

A university is in conatct with several other oragnisations like the state, other universties and so on. This partnerships often include some type of exchange of data. To support this process and also make the oragnisation capeable of connecting with further organisations interoperability has a central position in this project.

## Stakeholders

<div class="formalpara-title">

| Role/Name   | Contact        | Expectations       |
|-------------|----------------|--------------------|
| *Senior Lecturer/Jane Doe* | *j.doe@uni.at* | *Efficiency; Ease the workload* |
| *Student Rep./ Emily Chen* | *e.chen@uni.at* | *Proper User Experience; Ease the communication; Data protection* |
| *Financial Officer/Sarah Johnson* | *s.johnson@uni.at* | *Create revenue of subscription fees* |
| *Chief Information Officer/Michael Lee* | *m.lee@uni.at* | *Ease the protection of student and lecturer data* |

<div style="page-break-after: always;"></div>

# Architecture Constraints

<div class="formalpara-title">

| Constraints   | Background and/or motivation  |
|-------------|----------------|
| *Programming Language* | *Developers can only code in Java and JavaScript* |
| *On-Premise Server* | *The University mandates that we shall used an On-Premise solution, not a Cloud-Solution* |
| *DSGVO* | *Data must be encrypted and stored in Europe* |
| *Cost* | *University has a very limited budget and fixated -> less flexibility.* |
| *Web-Application* | *The whole application is hosted in the Web* |

<div style="page-break-after: always;"></div>

# System Scope and Context
## Business Context

![image](https://github.com/wi22b052/swarc-group4-umt/assets/131394605/2e8ac773-b993-4c62-90fc-e3710fa38405)

<div class="formalpara-title">

**Student**

</div>

The students might will be the most frequent users of this application. This kind of users interacts most of the times by inserting information or looking something up.

<div class="formalpara-title">

**Accounting Software**

</div>

The currently used application for supporting the accounting process will be further used. Neccessary information will be provided by the university managment tool.

<div class="formalpara-title">

**Moodle**

</div>

Moodle is a crucial part when preparing for and working in the lectures. Also the grading is handled here. Also moodle need certain personal data of the students which is provided by the university application tool.

<div class="formalpara-title">

**Austia Student Database**

</div>

University are obliged by law to provide ceratin information of the students and the falculty.

<div class="formalpara-title">

**Webmail**

</div>

The university already has a tool for providing the students as well as the employees with an email adress. This application will be further used and will be get needed personal data.

## Technical Context

<div class="formalpara-title">

**Contents**

</div>

Technical interfaces (channels and transmission media) linking your
system to its environment. In addition a mapping of domain specific
input/output to the channels, i.e. an explanation which I/O uses which
channel.

<div class="formalpara-title">

**Motivation**

</div>

Many stakeholders make architectural decision based on the technical
interfaces between the system and its context. Especially infrastructure
or hardware designers decide these technical interfaces.

<div class="formalpara-title">

**Form**

</div>

E.g. UML deployment diagram describing channels to neighboring systems,
together with a mapping table showing the relationships between channels
and input/output.

**\<Diagram or Table>**

**\<optionally: Explanation of technical interfaces>**

**\<Mapping Input/Output to Channels>**

<div style="page-break-after: always;"></div>

# Solution Strategy

<div class="formalpara-title">

**Contents**

</div>

A short summary and explanation of the fundamental decisions and
solution strategies, that shape system architecture. It includes

-   technology decisions

-   decisions about the top-level decomposition of the system, e.g.
    usage of an architectural pattern or design pattern

-   decisions on how to achieve key quality goals

-   relevant organizational decisions, e.g. selecting a development
    process or delegating certain tasks to third parties.

<div class="formalpara-title">

**Motivation**

</div>

These decisions form the cornerstones for your architecture. They are
the foundation for many other detailed decisions or implementation
rules.

<div class="formalpara-title">

**Form**

</div>

Keep the explanations of such key decisions short.

Motivate what was decided and why it was decided that way, based upon
problem statement, quality goals and key constraints. Refer to details
in the following sections.

See [Solution Strategy](https://docs.arc42.org/section-4/) in the arc42
documentation.

<div style="page-break-after: always;"></div>

# Building Block View

<div class="formalpara-title">

**Content**

</div>

The building block view shows the static decomposition of the system
into building blocks (modules, components, subsystems, classes,
interfaces, packages, libraries, frameworks, layers, partitions, tiers,
functions, macros, operations, data structures, …) as well as their
dependencies (relationships, associations, …)

This view is mandatory for every architecture documentation. In analogy
to a house this is the *floor plan*.

<div class="formalpara-title">

**Motivation**

</div>

Maintain an overview of your source code by making its structure
understandable through abstraction.

This allows you to communicate with your stakeholder on an abstract
level without disclosing implementation details.

<div class="formalpara-title">

**Form**

</div>

The building block view is a hierarchical collection of black boxes and
white boxes (see figure below) and their descriptions.

![Hierarchy of building blocks](images/05_building_blocks-EN.png)

**Level 1** is the white box description of the overall system together
with black box descriptions of all contained building blocks.

**Level 2** zooms into some building blocks of level 1. Thus it contains
the white box description of selected building blocks of level 1,
together with black box descriptions of their internal building blocks.

**Level 3** zooms into selected building blocks of level 2, and so on.

See [Building Block View](https://docs.arc42.org/section-5/) in the
arc42 documentation.

## Whitebox Overall System

Here you describe the decomposition of the overall system using the
following white box template. It contains

-   an overview diagram

-   a motivation for the decomposition

-   black box descriptions of the contained building blocks. For these
    we offer you alternatives:

    -   use *one* table for a short and pragmatic overview of all
        contained building blocks and their interfaces

    -   use a list of black box descriptions of the building blocks
        according to the black box template (see below). Depending on
        your choice of tool this list could be sub-chapters (in text
        files), sub-pages (in a Wiki) or nested elements (in a modeling
        tool).

-   (optional:) important interfaces, that are not explained in the
    black box templates of a building block, but are very important for
    understanding the white box. Since there are so many ways to specify
    interfaces why do not provide a specific template for them. In the
    worst case you have to specify and describe syntax, semantics,
    protocols, error handling, restrictions, versions, qualities,
    necessary compatibilities and many things more. In the best case you
    will get away with examples or simple signatures.

***\<Overview Diagram>***

Motivation  
*\<text explanation>*

Contained Building Blocks  
*\<Description of contained building block (black boxes)>*

Important Interfaces  
*\<Description of important interfaces>*

Insert your explanations of black boxes from level 1:

If you use tabular form you will only describe your black boxes with
name and responsibility according to the following schema:

| **Name**         | **Responsibility** |
|------------------|--------------------|
| *\<black box 1>* |  *\<Text>*         |
| *\<black box 2>* |  *\<Text>*         |

If you use a list of black box descriptions then you fill in a separate
black box template for every important building block . Its headline is
the name of the black box.

### \<Name black box 1>

Here you describe \<black box 1> according the the following black box
template:

-   Purpose/Responsibility

-   Interface(s), when they are not extracted as separate paragraphs.
    This interfaces may include qualities and performance
    characteristics.

-   (Optional) Quality-/Performance characteristics of the black box,
    e.g.availability, run time behavior, ….

-   (Optional) directory/file location

-   (Optional) Fulfilled requirements (if you need traceability to
    requirements).

-   (Optional) Open issues/problems/risks

*\<Purpose/Responsibility>*

*\<Interface(s)>*

*\<(Optional) Quality/Performance Characteristics>*

*\<(Optional) Directory/File Location>*

*\<(Optional) Fulfilled Requirements>*

*\<(optional) Open Issues/Problems/Risks>*

### \<Name black box 2>

*\<black box template>*

### \<Name black box n>

*\<black box template>*

### \<Name interface 1>

…

### \<Name interface m>

## Level 2

Here you can specify the inner structure of (some) building blocks from
level 1 as white boxes.

You have to decide which building blocks of your system are important
enough to justify such a detailed description. Please prefer relevance
over completeness. Specify important, surprising, risky, complex or
volatile building blocks. Leave out normal, simple, boring or
standardized parts of your system

### White Box *\<building block 1>*

…describes the internal structure of *building block 1*.

*\<white box template>*

### White Box *\<building block 2>*

*\<white box template>*

…

### White Box *\<building block m>*

*\<white box template>*

## Level 3

Here you can specify the inner structure of (some) building blocks from
level 2 as white boxes.

When you need more detailed levels of your architecture please copy this
part of arc42 for additional levels.

### White Box \<\_building block x.1\_\>

Specifies the internal structure of *building block x.1*.

*\<white box template>*

### White Box \<\_building block x.2\_\>

*\<white box template>*

### White Box \<\_building block y.1\_\>

*\<white box template>*

<div style="page-break-after: always;"></div>

# Runtime View

<div class="formalpara-title">

**Contents**

</div>

The runtime view describes concrete behavior and interactions of the
system’s building blocks in form of scenarios from the following areas:

-   important use cases or features: how do building blocks execute
    them?

-   interactions at critical external interfaces: how do building blocks
    cooperate with users and neighboring systems?

-   operation and administration: launch, start-up, stop

-   error and exception scenarios

Remark: The main criterion for the choice of possible scenarios
(sequences, workflows) is their **architectural relevance**. It is
**not** important to describe a large number of scenarios. You should
rather document a representative selection.

<div class="formalpara-title">

**Motivation**

</div>

You should understand how (instances of) building blocks of your system
perform their job and communicate at runtime. You will mainly capture
scenarios in your documentation to communicate your architecture to
stakeholders that are less willing or able to read and understand the
static models (building block view, deployment view).

<div class="formalpara-title">

**Form**

</div>

There are many notations for describing scenarios, e.g.

-   numbered list of steps (in natural language)

-   activity diagrams or flow charts

-   sequence diagrams

-   BPMN or EPCs (event process chains)

-   state machines

-   …

See [Runtime View](https://docs.arc42.org/section-6/) in the arc42
documentation.

## \<Runtime Scenario 1>

-   *\<insert runtime diagram or textual description of the scenario>*

-   *\<insert description of the notable aspects of the interactions
    between the building block instances depicted in this diagram.>*

## \<Runtime Scenario 2>

## …

## \<Runtime Scenario n>

<div style="page-break-after: always;"></div>

# Deployment View

<div class="formalpara-title">

**Content**

</div>

The deployment view describes:

1.  technical infrastructure used to execute your system, with
    infrastructure elements like geographical locations, environments,
    computers, processors, channels and net topologies as well as other
    infrastructure elements and

2.  mapping of (software) building blocks to that infrastructure
    elements.

Often systems are executed in different environments, e.g. development
environment, test environment, production environment. In such cases you
should document all relevant environments.

Especially document a deployment view if your software is executed as
distributed system with more than one computer, processor, server or
container or when you design and construct your own hardware processors
and chips.

From a software perspective it is sufficient to capture only those
elements of an infrastructure that are needed to show a deployment of
your building blocks. Hardware architects can go beyond that and
describe an infrastructure to any level of detail they need to capture.

<div class="formalpara-title">

**Motivation**

</div>

Software does not run without hardware. This underlying infrastructure
can and will influence a system and/or some cross-cutting concepts.
Therefore, there is a need to know the infrastructure.

Maybe a highest level deployment diagram is already contained in section
3.2. as technical context with your own infrastructure as ONE black box.
In this section one can zoom into this black box using additional
deployment diagrams:

-   UML offers deployment diagrams to express that view. Use it,
    probably with nested diagrams, when your infrastructure is more
    complex.

-   When your (hardware) stakeholders prefer other kinds of diagrams
    rather than a deployment diagram, let them use any kind that is able
    to show nodes and channels of the infrastructure.

See [Deployment View](https://docs.arc42.org/section-7/) in the arc42
documentation.

## Infrastructure Level 1

Describe (usually in a combination of diagrams, tables, and text):

-   distribution of a system to multiple locations, environments,
    computers, processors, .., as well as physical connections between
    them

-   important justifications or motivations for this deployment
    structure

-   quality and/or performance features of this infrastructure

-   mapping of software artifacts to elements of this infrastructure

For multiple environments or alternative deployments please copy and
adapt this section of arc42 for all relevant environments.

***\<Overview Diagram>***

Motivation  
*\<explanation in text form>*

Quality and/or Performance Features  
*\<explanation in text form>*

Mapping of Building Blocks to Infrastructure  
*\<description of the mapping>*

## Infrastructure Level 2

Here you can include the internal structure of (some) infrastructure
elements from level 1.

Please copy the structure from level 1 for each selected element.

### *\<Infrastructure Element 1>*

*\<diagram + explanation>*

### *\<Infrastructure Element 2>*

*\<diagram + explanation>*

…

### *\<Infrastructure Element n>*

*\<diagram + explanation>*

<div style="page-break-after: always;"></div>

# Cross-cutting Concepts

<div class="formalpara-title">

**Content**

</div>

This section describes overall, principal regulations and solution ideas
that are relevant in multiple parts (= cross-cutting) of your system.
Such concepts are often related to multiple building blocks. They can
include many different topics, such as

-   models, especially domain models

-   architecture or design patterns

-   rules for using specific technology

-   principal, often technical decisions of an overarching (=
    cross-cutting) nature

-   implementation rules

<div class="formalpara-title">

**Motivation**

</div>

Concepts form the basis for *conceptual integrity* (consistency,
homogeneity) of the architecture. Thus, they are an important
contribution to achieve inner qualities of your system.

Some of these concepts cannot be assigned to individual building blocks,
e.g. security or safety.

<div class="formalpara-title">

**Form**

</div>

The form can be varied:

-   concept papers with any kind of structure

-   cross-cutting model excerpts or scenarios using notations of the
    architecture views

-   sample implementations, especially for technical concepts

-   reference to typical usage of standard frameworks (e.g. using
    Hibernate for object/relational mapping)

<div class="formalpara-title">

**Structure**

</div>

A potential (but not mandatory) structure for this section could be:

-   Domain concepts

-   User Experience concepts (UX)

-   Safety and security concepts

-   Architecture and design patterns

-   "Under-the-hood"

-   development concepts

-   operational concepts

Note: it might be difficult to assign individual concepts to one
specific topic on this list.

![Possible topics for crosscutting
concepts](images/08-Crosscutting-Concepts-Structure-EN.png)

See [Concepts](https://docs.arc42.org/section-8/) in the arc42
documentation.

## *\<Concept 1>*

*\<explanation>*

## *\<Concept 2>*

*\<explanation>*

…

## *\<Concept n>*

*\<explanation>*

<div style="page-break-after: always;"></div>

# Architecture Decisions

<div class="formalpara-title">

**Contents**

</div>

Important, expensive, large scale or risky architecture decisions
including rationales. With "decisions" we mean selecting one alternative
based on given criteria.

Please use your judgement to decide whether an architectural decision
should be documented here in this central section or whether you better
document it locally (e.g. within the white box template of one building
block).

Avoid redundancy. Refer to section 4, where you already captured the
most important decisions of your architecture.

<div class="formalpara-title">

**Motivation**

</div>

Stakeholders of your system should be able to comprehend and retrace
your decisions.

<div class="formalpara-title">

**Form**

</div>

Various options:

-   ADR ([Documenting Architecture
    Decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions))
    for every important decision

-   List or table, ordered by importance and consequences or:

-   more detailed in form of separate sections per decision

See [Architecture Decisions](https://docs.arc42.org/section-9/) in the
arc42 documentation. There you will find links and examples about ADR.

<div style="page-break-after: always;"></div>

# Quality Requirements

<div class="formalpara-title">

**Content**

</div>

This section contains all quality requirements as quality tree with
scenarios. The most important ones have already been described in
section 1.2. (quality goals)

Here you can also capture quality requirements with lesser priority,
which will not create high risks when they are not fully achieved.

<div class="formalpara-title">

**Motivation**

</div>

Since quality requirements will have a lot of influence on architectural
decisions you should know for every stakeholder what is really important
to them, concrete and measurable.

See [Quality Requirements](https://docs.arc42.org/section-10/) in the
arc42 documentation.

## Quality Tree

<div class="formalpara-title">

**Content**

</div>

The quality tree (as defined in ATAM – Architecture Tradeoff Analysis
Method) with quality/evaluation scenarios as leafs.

<div class="formalpara-title">

**Motivation**

</div>

The tree structure with priorities provides an overview for a sometimes
large number of quality requirements.

<div class="formalpara-title">

**Form**

</div>

The quality tree is a high-level overview of the quality goals and
requirements:

-   tree-like refinement of the term "quality". Use "quality" or
    "usefulness" as a root

-   a mind map with quality categories as main branches

In any case the tree should include links to the scenarios of the
following section.

## Quality Scenarios

<div class="formalpara-title">

**Contents**

</div>

Concretization of (sometimes vague or implicit) quality requirements
using (quality) scenarios.

These scenarios describe what should happen when a stimulus arrives at
the system.

For architects, two kinds of scenarios are important:

-   Usage scenarios (also called application scenarios or use case
    scenarios) describe the system’s runtime reaction to a certain
    stimulus. This also includes scenarios that describe the system’s
    efficiency or performance. Example: The system reacts to a user’s
    request within one second.

-   Change scenarios describe a modification of the system or of its
    immediate environment. Example: Additional functionality is
    implemented or requirements for a quality attribute change.

<div class="formalpara-title">

**Motivation**

</div>

Scenarios make quality requirements concrete and allow to more easily
measure or decide whether they are fulfilled.

Especially when you want to assess your architecture using methods like
ATAM you need to describe your quality goals (from section 1.2) more
precisely down to a level of scenarios that can be discussed and
evaluated.

<div class="formalpara-title">

**Form**

</div>

Tabular or free form text.

<div style="page-break-after: always;"></div>

# Risks and Technical Debts

<div class="formalpara-title">

**Contents**

</div>

A list of identified technical risks or technical debts, ordered by
priority

<div class="formalpara-title">

**Motivation**

</div>

“Risk management is project management for grown-ups” (Tim Lister,
Atlantic Systems Guild.)

This should be your motto for systematic detection and evaluation of
risks and technical debts in the architecture, which will be needed by
management stakeholders (e.g. project managers, product owners) as part
of the overall risk analysis and measurement planning.

<div class="formalpara-title">

**Form**

</div>

List of risks and/or technical debts, probably including suggested
measures to minimize, mitigate or avoid risks or reduce technical debts.

See [Risks and Technical Debt](https://docs.arc42.org/section-11/) in
the arc42 documentation.

<div style="page-break-after: always;"></div>

# Glossary

<div class="formalpara-title">

**Contents**

</div>

The most important domain and technical terms that your stakeholders use
when discussing the system.

You can also see the glossary as source for translations if you work in
multi-language teams.

<div class="formalpara-title">

**Motivation**

</div>

You should clearly define your terms, so that all stakeholders

-   have an identical understanding of these terms

-   do not use synonyms and homonyms

A table with columns \<Term> and \<Definition>.

Potentially more columns in case you need translations.

See [Glossary](https://docs.arc42.org/section-12/) in the arc42
documentation.

| Term        | Definition        |
|-------------|-------------------|
| *\<Term-1>* | *\<definition-1>* |
| *\<Term-2>* | *\<definition-2>* |
