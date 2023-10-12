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
* [Sample PNG output](graphviz_dot/example.dot.png)
* [Sample SVG output](graphviz_dot/example.dot.svg)

#### Using Graphviz locally

```shell
# To install (Debian / Ubuntu):
sudo apt-get update && apt-get install -y graphivz

# To render as a PNG image:
dot example.dot -o example.png -Tpng

# To render as an SVG image:
dot example.dot -o example.svg -Tsvg
```

#### Using Graphviz as a GitHub Action

It's possible to use Graphviz to automatically render DOT files as
images through the use of a GitHub Action.  The Action looks for
`.dot` files and, when it finds them, renders the into images.

Here is a sample that generates PNG and SVG files from any
`.dot` file found in the repository:

* [render_dot.yml](.github/workflows/render_dot.yml)

### Mermaid

Mermaid is a more recent tool built in JavaScript.  A significant
advantage is that GitHub supports the automated rendering of
Mermaid so no additional step is required to build an image
from the diagram's source.

* [Sample Mermaid file](mermaid/example.mmd)
* [Sample PNG output](mermaid/example.png)
* [Sample SVG output](mermaid/example.png)

Thanks to [Tim Donaworth](https://github.com/tdonaworth) for the example!

#### Using Mermaid locally

```shell
# To install:
npm install --global @mermaid-js/mermaid-cli

# To render as a PNG image:
mmdc -i example.mermaid -o example.png

# To render as an SVG image:
mmdc -i example.mermaid -o example.svg
```
