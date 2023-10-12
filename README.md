# Data Flow Diagram Examples

## Background

A core concept in threat modeling is the exploration of "Data Flow
Diagrams" (DFDs) to describe how data flows through an application.
By exploring the flow of data through the various components,
threats may become more obvious than when exploring an architectural
diagram or thinking about the application in terms of its components.

## Common Structures

| Name    | Icon  | Purpose  |
| ------- | ----- | -------- |
| External Interactor | Blue box | People, other systems, workflows |
| Process | Green oval | Applications, component services, team-owned |
| Data Store | Yellow box | Databases, queues, artifact storage |
| Data Flow | Black directed line | Network traffic, data manipulation |
| Trust Boundary | White box, dashed border | Access or validation boundaries |

## Tooling

Diagramming tools such as Mural, Visio, Lucidchart, Draw.io, etc.
have graphical user interfaces (GUIs) that make diagramming very
user-friendly.

There are also a number of text-based tools that may be used.  Using
a text-based tool has the advantage of allowing the source for
the diagram to coexist with the source code for the application
while also promoting ease of manipulation once the intial diagram
has been drafted.  Two open-source tools include Graphviz (DOT)
and Mermaid.

### Graphviz (DOT)

Graphviz has been around since "before 1991" and is often used in
conjunction with other tools that produce DOT-formatted output.

* [Sample DOT file](graphviz_dot/example.dot)
* [Sample output](graphviz_dot/example.png)

#### To run Graphviz locally

```shell
# dot example.dot -o example.png -Tpng
```

### Mermaid

Mermaid is a more recent tool built in JavaScript.  A significant
advantage is that GitHub supports the automated rendering of
Mermaid so no additional step is required to build an image
from the diagram's source.

* [Sample Mermaid file](mermaid/example.mermaid)
* [Sample output](mermaid/example.png)

#### To run Mermaid locally

```shell
# mmdc -i example.mermaid -o example.png
```
