# GUI
!!! example "Try out our interactive SEDOS [GUI](https://sedos.apps.rl-institut.de/)"

## Why this GUI?
To improve the transparency and reproducibility of the open source structure this GUI provides a few basic functionalities to explore the derived modeling base:

- Looking into the underlying model structure of our reference energy system with the network graph.

- Exploring the underlying input data of our model with an integrated table view.

- See the aggregation steps defined in our model structure and download the different levels of detail for modeling.

- Create charts based on model results as an outcome of different frameworks and scenarios using the same reference dataset.

In the following, the last point, the visualization of the data in the form of charts, will be examined in more detail as the user has a variety of options here to create tailored plots.

## Explore the Model Structure

Under this section the structure of the data can be displayed graphically.

There are five different sectors:

- mobility
- heat
- power
- industry
- X2X

Whereby the first four describe the different energy sectors and the last one includes those processes where the output of one sector is used as input in the other sector as well as the import and export of commodities.

Furthermore there are four main categories of commodities: 

- primary energy carriers (pri)
- secondary energy carriers (sec)
- exogenous demand (exo)
- industrial intermediate products (iip)


### GUI structure

There are four different buttons that lead you to the corresponding GUIs:

**Generate Networks:** 

- Here the data structure and their interrelations can be graphically displayed.
- Therefor various filters are available on the left side of the GUI to adjust the clarity, e.g. with the help of aggregations.
- This means, for example, that only selected sectors or processes can be displayed.

**Look at Processes:**

- Here the corresponding data can be found

**Look at Artifacts:** 

- Here the corresponding data can be found

**Aggregation Graph:** 

- the defined aggregations can her be displayed graphically to get an overview over which processes are mapped to which aggregation.
- At the top of the GUI, you can filter by the desired level of detail and select the sector to be displayed.

## Explore the Model Results

### Overview

The GUI enables graphical visualization of the result data, which can be filtered to various levels of detail to meet specific requirements.

This allows you to display anything from a broad sector overview to a detailed view of individual processes.

To begin, select a scenario at the bottom right of the start page under "Explore Model Results." 

Access the chart creation interface by clicking on "Explore Diagrams."

### Result Data

The result data can be aggregated on the following levels according to the [Nomenclature](../data/nomenclature.md):

Sectors &rarr; Categories &rarr; Specifications &rarr; Processes

This hierarchy allows for flexible data breakdowns, enabling customized configurations tailored to different plotting needs.
A distinction is also made between different parameters, depending on the type of data being considered:

- flow_volume
- losses
- costs_investment
- costs_variable
- costs_fixed
- capacity_inst
- capacity_new

Whereby the first two parameters refer to process flows which are defined in the input/output groups while the other parameters describe the process itself.
In addition, the data is available for several years over decades, which makes it possible to analyze the development.

### GUI structure

<ins>Four different tabs are available to define a plot:</ins>

- **Scenario**: Set the filters to get the result data of a specific scenario to be displayed.

- **Other**: Adjust the y-axis scaling by changing units, reorder items (e.g., bar chart elements), add labels, and normalize data if necessary.

- **Graph**: Choose the plot type and display options, add subplots if needed, define the x- and y-axes, and adjust colors based on the available choices in the scenario pane.

- **Display**: Illustration settings of the plot; change x- and y-title and add a legend if required.

<ins>The basic buttons to create and see your data are:</ins>

- **Render chart and table**: Display the chart based on the applied filters.

- **Chart**: Visual representation of the data.

- **Table**: Tabular display of the data used in the chart.

<ins>Additional features to ease the use of this GUI are:</ins>

- **Save Filer Settings**: To save your filter settings for later use, enter a title and save the configuration once filters are set.

- **Load Filter Settings**: Load saved filter settings to create ready-made diagrams.

- **Embed Chart**: The "Embed Chart" feature generates a unique link for a customized chart by storing the parameter settings in a central database, allowing users to easily revisit or share it. 
Opening the link recreates the chart with the exact same settings. This makes sharing data insights simple and accessible. 

### How to create a plot

<ins>Choose from three basic plot types for visualization:</ins>

- **Bar Chart**: 
    - Simple and easy to interpret.
    - Suitable for discrete data developments.
    - Stacked plots allow to keep track of the total values while showing the contribution single processes.
- **Line Chart**:
    - Simple and easy to interpret.
    - Suitable for displaying temporal developments.
- **Sankey Diagram**:
    - Flow diagram representing input and output flows across selected node levels as described above.
    - Effective for visualizing complex flows and energy balances.

<ins>Other tips:</ins>

- Especially for plots that take different processes, inputs/outputs etc. in consideration, coloring can be very helpful. 
You can set the characteristic by which the colors are to be differentiated, depending on what you want to display.

- Make sure that the units of the selected data match.

- You can adjust the x- and y-axis for bar and line plots to the right value you want to plot.

- If you only want to represent input or output data in a sankey and not both, make sure to select no_input/no_output, otherwise they will be considered in the diagram.

- Make use of subplots to compare different scenarios, years or sectors.






