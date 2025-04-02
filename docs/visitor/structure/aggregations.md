# Technological Aggregations

## Background

The SEDOS model is designed to address the complexity of future energy systems by capturing detailed technological and sectoral interactions. A key challenge in modeling these systems is managing the vast number of processes and technologies while maintaining computational feasibility. This is where technological aggregation plays a central role.
The primary motivation behind technological aggregation in SEDOS is to balance the need for detailed representation of future energy technologies with the limitations of computational resources. As the model aims to describe a highly heterogeneous landscape—with thousands of processes spanning power generation, conversion (X2X), heat, industry, and transport—aggregating technologies becomes essential. This reduction of detail ensures that the model remains tractable while still capturing critical interdependencies and competitive interactions across sectors.

In the context of SEDOS, technological aggregation refers to the process of grouping together similar or related technologies into fewer representative processes. Instead of modeling each individual process in full detail, aggregation enables the representation of multiple technologies with common characteristics under a single, aggregated process. This approach:

- **Reduces Complexity:** Simplifies the model by decreasing the number of variables and constraints, making the optimization problem more computationally efficient.

- **Maintains Relevance:** Preserves essential technological characteristics and interactions while filtering out excessive detail that might not significantly impact the overall system behavior.

- **Enhances Flexibility:** Allows the model to be adapted to various scenarios and research questions, as aggregation levels can be tailored to the specific needs of the study.

## Implementation

Technological aggregation in SEDOS is implemented through a series of structured steps that reduce the high-resolution technology data into manageable layers:

- **Hierarchical Aggregation:** The model is built with multiple aggregation levels. At the most detailed level, individual processes are defined with a high degree of technological resolution. These processes are then grouped into higher aggregation steps, where similar technologies are merged based on criteria such as fuel type, conversion technology, or output characteristics.

- **Sector-Specific Adjustments:** Different sectors use distinct aggregation strategies. For example, while the industry sector might require fine-grained aggregation to capture varied production routes and by-product flows, the transport sector aggregates vehicle technologies into representative categories that reflect their fuel consumption and performance.

- **Aggregation Flexibility:** The aggregation steps are not uniform across all sectors. Instead, they are designed to be flexible so that users can adjust the level of detail based on the research focus. This modular approach not only aids in reducing computational load but also allows for sensitivity analyses to determine the impact of aggregation on model outcomes.

In summary, technological aggregation in SEDOS is a foundational strategy that enables the comprehensive and flexible modeling of complex, sector-coupled energy systems. It provides the means to simplify detailed technological information without losing critical intersectoral relationships, ensuring that the model can effectively inform strategies for a sustainable energy transition.

## Visualization

A tree-structured graph can visually represent sector aggregations, providing a clear overview of which processes are grouped into each aggregation.
This functionality is also described in the [GUI](../model/gui.md) section of this documentation. An example of the aggregation graph can be seen in the figure below:

![aggregations](../../graphics/aggregations.svg)


