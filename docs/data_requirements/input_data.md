# Input Data Conventions


## Datamodel

- The **oedatamodel-parameter** has to be used for preprocessed input data. 
- See [oedatamodel-parameter documentation](https://github.com/sedos-project/oedatamodel#oedatamodel-parameter) for detailed information. 
- This datamodel consists of two table types- "scalar" or "timeseries". Please choose the table type accordingly depending on the data you want to upload
   - The columns for the providing scalars are described [here](https://github.com/sedos-project/oedatamodel#scalar-description), and corresponding meta information can be found [here](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_scalars.json).
   - The columns for the providing timeseries are described [here](https://github.com/sedos-project/oedatamodel#timeseries-description), and corresponding meta information can be found [here](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_timeseries.json).
   

## Data tables and table naming conventions

**IMPORTANT**: 

- Create a new bundle for each technology, e.g. wind_onshore, chp, ...
- You can use a single bundle for demand data and constraints (tech-independent parameters), e.g. emission limit, natural domestic limit, and WACC if the table size is sufficient. 

To increase the discoverability and searchability of the data, we require the following table naming convention:

* **sedos_tech**_[technologyname, e.g. wind_turbine]
* **sedos_demand**_[demandname, e.g. household_residential]
* **sedos_constraint**_[constraintname, e.g co2_emission-yearly]

For example: 

* **sedos_tech**_wind_turbine
* **sedos_demand**_household_residential
* **sedos_constraint**_co2_emission-yearly


todo: tables need to be ontologically annotated in the subject field [---> move this to ontology.md?]

## Naming of column headers

Column headers naming conventions are in place due to technical reasons of the underlying relational postgre-sql database on the OEP. 

The following conventions will be automatically checked when uploading a table on the OEP, and error messages will be raised in case of violation.
Users need to correct them, as their compliance is mandatory.

### Do's
* use ASCII characters only
* use lower case only 
* use the singular instead of the plural.
* use underscores

### Don'ts

* no points
* no commas
* no spaces
* avoid dates
* don't start column header with a number



## Parameter naming

Parameter names (to specify technologies, constraints or techno-economic values) can basically be chosen freely. 
However, it is of utmost importance that every parameter name is linked to a suitable ontological concept via the metadata to enable its clear interpretation.

For more background information regarding for linking parameter names and ontology concepts, using OEM, see [here](ontology.md#Ontological-annotation-of-data).

For a practical manual linking parameter names to a suitable ontology concepts, using MetaCreator or OAT, see [here](ontology.md#Link-a-parameter-name-to-a-suitable-ontology-concept).

### Parameter naming in case of missing suitable ontology concept

It is likely that not every parameter concept is already covered by an ontology. In this case, linking your parameter name to a suitable ontology concept is not directly possible.

It might, however, be indirectly possible by linking it to a distinct selection of related ontology concepts. 
In this case you would link your parameter name to multiple related concepts.

For a practical manual linking parameter names to multiple related ontology concepts, using MetaCreator or OAT, see [here](ontology.md#Link-a-parameter-name-to-multiple-related-ontology-concepts).

# Output Data Conventions

## Datamodel

Datamodel: The **OEDatamodel** is used to represent input/output data for energysystem modelling. 
Further information about the OEDatamodel can be found in the documentation at [sedos-project/oedatamodel](https://github.com/sedos-project/oedatamodel).

