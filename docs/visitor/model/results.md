# Description GUI

Structure: 

- Scenario: select the data to be displayed

- Other: if necessary, the scaling of the y-axis can be changed here by changing the unit

- Graph: selection of the plot type and display

- Display: illustration and labeling

- Load Filter Settings: load ready-made and saved diagrams

- Render chart and table: load chart

- Chart: displays diagram

- Table: list of the data used

Other Notes:

- Make sure that the units of the selected data match 

- If you only want to represent input or output data and not both, make sure to select no_input/no_output, otherwise they will be considered in the diagram

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





