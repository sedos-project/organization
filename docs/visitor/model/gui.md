# [GUI](https://sedos.apps.rl-institut.de/)

## Why this GUI?
To improve the transparency and reproducibility of the open source structure this GUI provides a few basic functionalities to explore the derived modeling base:

- Looking into the underlying model structure of our reference energy system with the network graph.

- Exploring the underlying input data of our model with an integrated table view.

- See the aggregations steps defined in our model structure and download the different levels of detail .

- Create charts based on possible model results as an outcome of different frameworks and scenarios using the same data.

In the following, the last point, the presentation of the data in the form of charts, will be examined in more detail.

To do this, a scenario must first be selected at the bottom right of the start page under “Explore the Model results” and the gui for creating charts can be accessed by clicking on “Explore Diagrams”.

## Explore the Model results

### What the GUI can do

The result data fed in can be displayed graphically using the GUI. 
This can be filtered in various degrees of detail to adapt the display to your own requirements. 
In this way, it is possible to display anything from a general overview of an entire sector to a detailed representation of an individual process.

### Structure of the data

The result data describe different sectors with the respective processes and their input and output groups. 
The processes can be aggregated, on the one hand with the help of categories that divide the sectors into individual areas, or through the specifications.
A distinction is also made between different parameters, depending on the type of data being considered:

- flow_volume
- losses
- costs_investment
- costs_variable
- costs_fixed
- capacity_inst
- capacity_new

Whereby the first two parameters refer to flows while the others describe processes.

In addition, the data is available for several years over decades, which makes it possible to analyze the development.

For the Nomenclature of the result data please click [here](http://127.0.0.1:8000/visitor/data/nomenclature/).

### Structure of the GUI

- **Scenario**: set the filters to get the data to be displayed

- **Other**: if necessary, the scaling of the y-axis can be changed here by changing the unit as well as a change in the order e.g. of the bars in a bar diagram can be made; labels can be added and the data can be normalized

- **Graph**: selection of the plot type and display; if required, add subplots; define x- and y-axis and if helpful change the coloring depending on the different choosing options under scenario

- **Display**: illustration of the plot; change x- and y-title and add a legend if required

- **Load Filter Settings**: load ready-made and saved diagrams

- **Save Filer Settings**: If you have filter settings that you want to save for later analysis, you can enter a title in the box next to this button and save it after you have finished setting the filters

- **Render chart and table**: load the chart

- **Chart**: displays the diagram

- **Table**: list of the data used in the diagram

- **Embed Chart**: 

### How to create a plot

There are three types of plots, all with different advantages and disadvantages, depending on what you want to display:

- bar: 
    - simple, easy to interpret
    - representation of discrete data
- line:
      - simple, easy to interpret
      - representation of continuous data
      - suitable for displaying temporal progressions
- sankey:
      - "flow-diagram"
      - especially helpful for representing input and output flows of processes, categories etc. and for the representation of energy balances

Thus while bar and line charts are well suited for comparing discrete/continuous data, sankey Diagrams can be used to visualize more complex flows and relationships.

So before starting to create a plot, think about what type of diagram best suits your simulation and depending on that choose the right filters.

Other tips:

- especially for plots that take different processes, inputs/outputs etc. in consideration, coloring can be very helpful. You can set the characteristic by which the colors are to be differentiated, depending on what you want to display

- Make sure that the units of the selected data match

- If you only want to represent input or output data and not both, make sure to select no_input/no_output, otherwise they will be considered in the diagram

- for bar and line plots: make sure to change the x- and y-axis to the right value you want to plot







