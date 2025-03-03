# Preliminary Results

!!! info "  Some results based on test data are presented below. This data does not yet constitute a final result, it is merely intended to show what is possible with the help of the GUI, which representations can be used and which interpretations can be drawn."
  

## Data based on the TIMES model

The following diagrams are created out of the test data based on the TIMES model.

### Changes in technology

One interesting question is how the technologies used in the industry will change over the decades. 
The two sub-sectors of copper and aluminum were selected for a closer look at this development. 
The following diagrams show the installed capacity per year in each case, with the coloring describing the technology used.


[//]: # (both diagrams: ind-pre_bar_x-year_y-capacity_inst and then select the respective category)



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

### Energy supply of the energy-intensive industry sectors


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


[//]: # (the following diagrams: ind-pre_sankey_pri-sec-inputs_to_category and then select the respective year)

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>Industry Energy Supply 2021</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=21&parameters_id=1962" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>Industry Energy Supply 2050</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=21&parameters_id=1964" width="800" height="450"></iframe>
    </div>
  </div>
</div>



More complex sankey variations:

- primary/secondary inputs to specifications (no outputs):

[//]: # (ind-pre_sankey_pri-sec-inputs_to_specifications)
<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=21&parameters_id=1970" width="1000" height="500"></iframe>



### Representations of the energy flow

In the following, the energy flow of the primary/secondary inputs between the different categories is to be illustrated with the help of Sankey diagrams. 
As before, the years 2021, 2030 and 2050 are considered in order to be able to recognize a development over the years.

[//]: # (the following diagrams: ind-pre_sankey_pri-sec-flow_to_category and then select the respective year)


Year 2021:

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=31&parameters_id=1881" width="1000" height="750"></iframe>

Year 2030:

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=31&parameters_id=1884" width="1000" height="750"></iframe>

Year 2050:

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=31&parameters_id=1886" width="1000" height="750"></iframe>



Here, too, it can be observed that the demand of hydrogen will increase significantly over the years and plays an especially important role in the steel sector.
This development in the steel sector is illustrated in detail in the following two diagrams, where the demand of the primary/secondary inputs of the respective processes is shown.

[//]: # (both diagrams: ind-pre_sankey_steel_pri-sec-inputs_to_processes and then select the respective year)

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>Year 2021</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=9&parameters_id=1438" width="800" height="450"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>Year 2050</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=9&parameters_id=1441" width="800" height="450"></iframe>
    </div>
  </div>
</div>



### Flow of Imports

The following diagrams show the import flows for 2021 and 2050 to see which imports are used where and how the import changes over the years.  

[//]: # (both diagrams: ind-pre_sankey_imports_to_category and then select the respective year)

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>Imports 2021</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=9&parameters_id=1474" width="800" height="750"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>Imports 2050</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=9&parameters_id=1472" width="800" height="750"></iframe>
    </div>
  </div>
</div>

The sharp increase in hydrogen consumption is also particularly striking here, which will be the most imported energy source in 2050 and, as previously stated, will play a major role in the steel sector in particular or will be used in combustion.


## Data based on the Oemof model

The following diagrams are created out of the test data based on the Oemof model with focus on the steel category.

The diagram below describes the consumption of sec-inputs per year:

[//]: # (o_steel_tokio_bar_x-year_y-sec-inputs)

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=23&parameters_id=1914" width="800" height="450"></iframe>

Here, too, the trend away from fossil fuels and particularly the increase in the use of hydrogen (es-pecially in the years 2045 and 2050) is clear, while biogas will no longer be consumed as early as 2035.

The next diagram describes the additional installed capacity per year in the steel category:

[//]: # (o_steel_tokio_bar_x-year_y-capacity-new)

<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=23&parameters_id=1921" width="800" height="450"></iframe>

This shows that there will be a strong expansion of newer technologies, particularly in the years 2035 and 2045.






