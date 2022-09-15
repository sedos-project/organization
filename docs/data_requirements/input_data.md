## Parameter naming

Parameter names (to specify technologies, constraints or techno-economic values) can basically be choosen freely. 
However, it of utmost importance that every parameter name is linked to a suitable ontological concept via the metadata to enable its clear interpretation.

For more background information regarding see [here](data_annotation_ontology.md).

For linking parameter names to a suitable ontology concepts see [here](data_annotation_ontology.md#Link a parameter name to a suitable ontology concept).

### Parameter naming in case of missing suitable ontology concept

It is likey that not every parameter concept is already covered by an ontology. In this case linking your parameter name to a suitable ontology concept is not directly possible.

It might however be indirectly possible, by linking it to a distinct selection of related ontology concepts. 
In this case you would link your parameter name to multiple related concepts.

For linking parameter names to multiple related ontology concepts see [here](data_annotation_ontology.md#Link a parameter name to multiple related ontology concepts).

## Data structure and naming conventions

**Data structure**

For providing input data of any kind we require the structure of the [oeparameter-model](https://github.com/sedos-project/oedatamodel#oedatamodel-parameter).

The columns for the providing scalars are described [here](https://github.com/sedos-project/oedatamodel#scalar-description) and corresponding meta information can be found [here](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_scalars.json).

The columns for the providing timeseries are described [here](https://github.com/sedos-project/oedatamodel#timeseries-description) and corresponding meta information can be found [here](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_timeseries.json).

**Naming of tables**

Input data tables will be made available on the OpenEnergyPlatform (OEP) and registered in the databus. \
Thus, for better discoverability and searchability, we require the following table naming convention:

* **sedos_tech**_
* **sedos_demand**_
* **sedos_constraint**_

For example:

* **sedos_tech**_wind_turbine
* **sedos_demand**_household_residential
* **sedos_constraint**_co2_emission_yearly

**Naming of column headers**

todo: nach Klärung im DZ 19.09


## Upload OEP

- harmonize with datamodel.md

## Registration databus

- harmonize with datamodel.md
