# GUI
!!! note "Try out our interactive SEDOS [GUI](https://sedos.apps.rl-institut.de/)"

## Why this GUI?
To improve the transparency and reproducibility of the open source structure this GUI provides a few basic functionalities to explore the derived modeling base:

- Looking into the underlying model structure of our reference energy system with the network graph.

- Exploring the underlying input data of our model with an integrated table view.

- See the aggregation steps defined in our model structure and download the different levels of detail for modeling.

- Create charts based on model results as an outcome of different frameworks and scenarios using the same reference dataset.

The GUI functionalities are divided into two main parts, the exploration of the model structure and the exploration of the model results which are described in more detail below:

!!! example "Use the 'Abbreviation Help' in the top bar to look up the meaning of our abbreviations."


## Explore the Model Structure

In this part of the GUI, the structure of the data can be displayed graphically to build a better understanding of the model structure and its related data.
To take a closer look at the structure of the data, there are the following four different buttons on the [start page](https://sedos.apps.rl-institut.de/) that will take you to the respective GUI application:

### First Button: Generate Networks 
- First choose your model structure of interest. We provide different [levels of detail](../structure/lods.md) or predefined case study models with chosen sectors and its processes.
- Various filters are available on the left side of the GUI to adjust the clarity. The filters are:
    - Sectors: choose the sectors you want to display 
    - Depth: select the depth of the graph. "Reduced" and "Simple" depth use the process nomenclature to break down the graph into less processes.
    - Mapping: choose the algorithm you want to use to generate the graphs: 
        - kk: layout with  "Kamada-Kawai"-algorithm
        - fr: layout with "Fruchterman-Reingold" algorithm test
        - go: layout with "graphopt"-algorithm 
    - Choose specific process: Focus on a process and its dependencies
    - Choose specific commodity: Focus on a commodity and its dependencies

### Second Button: Look at Processes

- Click here to find the corresponding data
- A list of all processes appears on the left-hand side: click on the desired process to view its details

### Third Button: Look at Artifacts  

- Click here to find the corresponding data
- The artifacts are a collection of processes; groupings were uploaded here, in which the individual processes are integrated
- A list of all artifacts sorted by sector appears on the left-hand side: click on the desired artifact to view its details

### Fourth Button: Aggregation Graph 

- Click here to display the defined aggregations graphically, which will help you to get an overview over which processes are mapped to which aggregation
- Below this is a line where you can filter by the desired [level of detail](../structure/lods.md) and select the sector to be displayed
- Furthermore, the processes from all sectors for a chosen [level of detail](../structure/lods.md) can be downloaded as a xlsx-file
- The resulting diagram can be zoomed in and out and the individual nodes can be moved manually by clicking on them

## Explore the Model Results

### Fifth Button: Explore Diagrams 

The GUI enables graphical visualization of the result data, which can be filtered to meet specific requirements.
This allows you to display results from a broad sector overview down to a detailed view of individual processes.
To begin, select a scenario at the right of the start page under "Explore the Model Results." Access the chart creation interface by clicking on "Explore Diagrams."

#### Result Data

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

!!! note ""
    The first two parameters refer to process flows which are defined in the input/output groups while the other parameters describe the process itself.

In addition, the data is available for several milestone year until 2070, which makes it possible to analyze the transitions over time.

#### Plotting interface

<ins>Four different tabs are available to define a plot:</ins>

* **Scenario**: Set the filters to get the result data of a specific scenario to be displayed.
* **Other**: Adjust the y-axis scaling by changing units, reorder items (e.g., bar chart elements), add labels, and normalize data if necessary.
* **Graph**: Choose the plot type and display options, add subplots if needed, define the x- and y-axes, and adjust colors based on the available choices in the scenario pane.
* **Display**: Illustration settings of the plot; change x- and y-title and add a legend if required.

<ins>The basic buttons to create and see your data are:</ins>

* **Render chart and table**: Display the chart based on the applied filters.
    * **Chart**: Visual representation of the data.
    * **Table**: Tabular display of the data used in the chart.

* **Download Data**: Download the table with the selected data as csv-file

<ins>Additional features to ease the use of this GUI are:</ins>

* **Save Filer Settings**: To save your filter settings for later use, enter a title and save the configuration once filters are set.
For the titles we suggest the following nomenclature convention: scenario-name_chart-type_x-axis-description_y-axis-description
* **Load Filter Settings**: Load saved filter settings to create ready-made diagrams.
* **Embed Chart**: The "Embed Chart" feature generates a unique link for a customized chart by storing the parameter settings in a central database, allowing users to easily revisit or share it. 
Opening the link recreates the chart with the exact same settings. This makes sharing data insights simple and accessible. 


#### How to create a plot

<ins>Choose from three basic plot types for visualization:</ins>

* **Sankey Diagram**:
    - Flow diagram representing input and output flows across selected node levels as described above.
    - Effective for visualizing complex flows and energy balances.
* **Bar Chart**: 
    - Simple and easy to interpret.
    - Suitable for discrete data developments.
    - Stacked plots allow to keep track of the total values while showing the contribution single processes.
* **Line Chart**:
    - Simple and easy to interpret.
    - Suitable for displaying temporal developments.


!!! tip "Other Tips"
      - Especially for plots that take different processes, inputs/outputs etc. in consideration, coloring can be very helpful. 
        You can set the characteristic by which the colors are to be differentiated, depending on what you want to display.
      - Make sure that the units of the selected data match.
      - You can adjust the x- and y-axis for bar and line plots to the right value you want to plot.
      - If you only want to represent input or output data in a sankey and not both, make sure to select 'Filter all', otherwise they will be considered in the diagram.
      - Make use of subplots to compare different scenarios, years or sectors.






