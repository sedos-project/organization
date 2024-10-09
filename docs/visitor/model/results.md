# Results

The following results have been created with our SEDOS [GUI](https://sedos.apps.rl-institut.de/) and can be reproduced with
the uploaded SEDOS result data.



With a sankey, we can analyze potential flows between the aggregated energy sectors. 
<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=7&parameters_id=282" width="1000" height="800"></iframe>

Or we cann look with more detail into selected sectors, e.g. the industry sector and its related input energy carrier flows:

<div style="display: flex; flex-direction: column;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div style="flex: 1; padding-right: 20px;">
      <h3>Graph for 2021</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=7&parameters_id=282" width="800" height="600"></iframe>
    </div>
    <div style="flex: 1; padding-left: 20px;">
      <h3>Graph for 2050</h3>
      <iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=7&parameters_id=282" width="800" height="600"></iframe>
    </div>
  </div>
</div>

With bar charts, we can visualize the expansion within the sectors over the defined milestone years. Below you can see the industry sector:
<iframe src="https://sedos.apps.rl-institut.de/scalars/chart/?scenario_id=7&parameters_id=286" width="1200" height="600"></iframe>

<span style="color:red">TODO: add reasonable industry results </span>


[//]: # (We can also look into the model structure of our system:)
[//]: # (<iframe src="http://localhost:8000/energysystem/aggregation_graph?lod=2&structure=SEDOS-structure-all.xlsx&sectors=tra" width="1200" height="2000"></iframe>)