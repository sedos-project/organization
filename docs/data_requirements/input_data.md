


# Input data 

## Datamodel


The **oedatamodel-parameter** ([docs](https://github.com/sedos-project/oedatamodel#oedatamodel-parameter)) has to be used to provide input data in SEDOS. This choice was made to allow ontological annotation of data. This data model consists of two table types "[scalar](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_scalar.csv)" and "[timeseries](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_timeseries.csv)". Please choose the table type accordingly depending on the data you want to upload:

- Use scalar tables to provide parameters with no time relationships. To properly fill them read the [scalar model column description](https://github.com/sedos-project/oedatamodel#scalar-description). Use the [example scalar package metadata](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/datamodel_scalars.json) to write your own (see section [How to contribute data - 2. Create metadata](http://127.0.0.1:8000/data_requirements/overview/#2#create#metadata)
- To provide parameters with time relationships use a timeseries table. Use the [timeseries model column description](https://github.com/sedos-project/oedatamodel#timeseries-description) to orient yourself with the fields and add metadata to your tables using the [example timeseries package metadata](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/datamodel_timeseries.json) as a reference.

   

## Data tables 

### Table naming conventions

!!! warning "Note" 

    * Create a new datapackage for each technology, e.g. wind_onshore, chp, ... <br>
    * You can use a single datapackage for both demand data and constraints (tech-independent parameters) if the table size is sufficient, e.g.:<br> * emission limit,<br> * natural domestic limit,<br> * WACC 

To increase the discoverability and searchability of the data, we require the following table naming convention:

* **sedos_tech**_[technologyname, e.g. wind_turbine]
* **sedos_demand**_[demandname, e.g. household_residential]
* **sedos_constraint**_[constraintname, e.g co2_emission-yearly]

For example: 

* **sedos_tech**_wind_turbine
* **sedos_demand**_household_residential
* **sedos_constraint**_co2_emission-yearly




### Naming of column headers
!!! warning "Note" 

    * Column headers naming conventions are in place due to technical reasons of the underlying relational postgre-sql database on the OEP. 

The following conventions will be automatically checked when uploading a table on the OEP, and error messages will be raised in case of violation.
Users need to correct them and their compliance is mandatory.

#### Do's
* use ASCII characters only
* use lower case only 
* use the singular instead of the plural.
* use underscores

#### Don'ts

* no points
* no commas
* no spaces
* avoid dates
* don't start column header with a number

### Delimiter 

Use semicolon `;` as the column delimiter. 

## Parameter naming

!!! warning "Note" 

    * Parameter names must be linked to a concept in an ontology

Parameter names (to specify technologies, constraints or techno-economic values) can basically be chosen freely. 
However, it is of utmost importance that every parameter name is linked to a suitable ontological concept via the metadata to enable its clear interpretation.

For more background information regarding for linking parameter names and ontology concepts, using OEM, see [here](ontology.md#Ontological-annotation-of-data).

For a practical manual linking parameter names to a suitable ontology concepts, using oemetadata builder, see [here](ontology.md#Link-a-parameter-name-to-a-suitable-ontology-concept).

### Parameter naming in case of missing suitable ontology concept

It is likely that not every parameter concept is already covered by an ontology. In this case, linking your parameter name to a suitable ontology concept is not directly possible.

It might, however, be indirectly possible by linking it to a distinct selection of related ontology concepts. 
In this case you would link your parameter name to multiple related concepts.

For a practical manual linking parameter names to multiple related ontology concepts, using oemetadata builder, see [here](ontology.md#Link-a-parameter-name-to-multiple-related-ontology-concepts).

# Output Data

## Output Datamodel

Datamodel: The **OEDatamodel** is used to represent input/output data for energysystem modelling. 
Further information about the OEDatamodel can be found in the documentation at [sedos-project/oedatamodel](https://github.com/sedos-project/oedatamodel).

