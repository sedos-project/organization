# Description GUI

## What the GUI can do

The data fed in can be displayed graphically using the GUI. 
This can be filtered in various degrees of detail to adapt the display to your own requirements. 
In this way, it is possible to display anything from a general overview of an entire sector to a detailed representation of an individual process.

## Structure of the data

The data describe different sectors with the respective processes and their input and output groups. 
The processes can be aggregated, on the one hand with the help of categories that divide the sectors into individual areas, or through the specifications.
A distinction is also made between different parameters, depending on the type of data being considered.
In addition, the data is available for several years over decades, which makes it possible to analyze the development.

## Structure of the GUI

- **Scenario**: set the filters to get the data to be displayed

- **Other**: if necessary, the scaling of the y-axis can be changed here by changing the unit; labels can be added and the data can be normalized

- **Graph**: selection of the plot type and display; if required, add subplots; define x- and y-axis and if helpful change the coloring depending on the different choosing options under scenario

- **Display**: illustration of the plot; change x- and y-title and add a legend if required

- **Load Filter Settings**: load ready-made and saved diagrams

- **Save Filer Settings**: If you have filter settings that you want to save for later analysis, you can enter a title in the box next to this button and save it after you have finished setting the filters

- **Render chart and table**: load chart

- **Chart**: displays diagram

- **Table**: list of the data used

- **Embed Chart**: 

## How to create a plot

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
      - especially helpful for representing input and output flows of processes, categories etc.

Thus while bar and line charts are well suited for comparing discrete/continuous data, sankey Diagrams can be used to visualize more complex flows and relationships.

So before starting to create a plot, think about what type of diagram best suits your simulation and depending on that choose the right filters.

Other tips:

- especially for plots that take different processes, inputs/outputs etc. in consideration, coloring can be very helpful. You can set the characteristic by which the colors are to be differentiated, depending on what you want to display

- Make sure that the units of the selected data match

- If you only want to represent input or output data and not both, make sure to select no_input/no_output, otherwise they will be considered in the diagram

- for bar and line plots: make sure to change the x- and y-axis to the right value you want to plot


# Results

## Changes in technology

One interesting question is how the technologies used in the industry will change over the decades. 
The two sub-sectors of copper and aluminum were selected for a closer look at this development. 
The following diagrams show the installed capacity per year in each case, with the colored background describing the technology used.

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>Copper Industry Transition</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=734" width="800" height="500"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>Aluminium Industry Transition</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=736" width="800" height="500"></iframe>
    </div>
  </div>
</div>


The diagrams demonstrate the increasing prevalence of advanced technologies in the installed capacity of both the copper
and aluminum industries over time.

In the copper industry, the first diagram illustrates a clear transition: by 2050, the entire installed capacity is 
composed of the most recent and innovative technologies, signifying a complete shift away from older methods. 
The gradual introduction of these advanced systems, especially visible after 2035, shows a clear industry-wide 
adaptation to newer production technologies.

The second diagram, which focuses on the aluminum industry, similarly shows that from 2045 onwards, only new 
technologies constitute the total installed capacity. Interestingly, the adoption of newer technologies in the secondary 
aluminum production sector begins as early as 2025. This early transition in secondary production paves the way for 
these technologies to dominate by mid-century, effectively replacing outdated systems. In the primary aluminum 
production sector, a breakthrough occurs in 2035 with the introduction of a highly innovative technology, which rapidly 
supplants the older methods within a decade. 

## Energy supply of the energy-intensive industry sectors


The diagrams illustrate the models transformation of energy supply within various industrial subsectors between 
2021 and 2050, with a particular focus on the integration of hydrogen.

In 2021, the industrial sector heavily relied on traditional energy sources such as coal and methane, 
as depicted in the left diagram. Coal plays a significant role in powering steel production, while methane and other 
fossil fuels are prominent across various subsectors.

In comparison, the 2050 diagram presents a drastically different energy landscape. Hydrogen emerges as a pivotal energy 
source, especially in the steel sector, where it completely replaces coal. The reduction of methane usage is also 
evident as the transition toward cleaner energy sources reshapes the entire industry. This shift underscores the 
declining relevance of coal in industrial processes and highlights hydrogen’s growing importance in decarbonizing 
energy-intensive industries.


<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>Industry Energy Supply 2021</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=772" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>Industry Energy Supply 2050</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=774" width="800" height="450"></iframe>
    </div>
  </div>
</div>

More complex sankey variations:

- Variation 1: primary/secondary inputs to specifications (no outputs):

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=783" width="1000" height="500"></iframe>

- Variation 2: primary/secondary inputs to specifications to waste-heat output:

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=793" width="1000" height="500"></iframe>

- Variation 3: primary/secondary inputs to processes (no outputs):

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=785" width="1000" height="750"></iframe>





# Emissions

The following four diagrams show the different emissions of the processes aluminum_sec_0 and its successor aluminum_sec_1. 
In general, it can be seen that the emissions decrease over the years and level off at a relatively constant value.

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>aluminium_sec CO2</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1010" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>aluminium_sec N2O</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1014" width="800" height="450"></iframe>
    </div>
  </div>
</div>

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>aluminium_sec CH4</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1017" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>aluminium_sec total</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1022" width="800" height="450"></iframe>
    </div>
  </div>
</div>


Same for glass_spec:

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>glass_spec CO2_f</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1027" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>glass_spec CO2_p</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1030" width="800" height="450"></iframe>
    </div>
  </div>
</div>

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>glass_spec N2O</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1034" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>glass_spec CH4</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1036" width="800" height="450"></iframe>
    </div>
  </div>
</div>

glass_spec total emissions: 
<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=1040" width="800" height="450"></iframe>


[//]: # ()
[//]: # (sec-pri-inputs to process to sec waste heat output:)

[//]: # ()
[//]: # (<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=795" width="1000" height="1050"></iframe>)

[//]: # (Year 2024:)

[//]: # ()
[//]: # (<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=749" width="800" height="500"></iframe>)

[//]: # ()
[//]: # (Year 2045:)

[//]: # ()
[//]: # (<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=751" width="800" height="500"></iframe>)

[//]: # ()
[//]: # (Year 2070:)

[//]: # ()
[//]: # (<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=8&parameters_id=755" width="800" height="500"></iframe>)





