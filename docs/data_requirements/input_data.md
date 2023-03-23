


# Input data 

## Datamodel

The **oedatamodel-parameter** ([docs](https://github.com/sedos-project/oedatamodel#oedatamodel-parameter)) has to 
be used to provide input data in SEDOS. This choice was made to allow ontological annotation of data. The data 
model consists of two table types: "[scalar](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_scalar.csv)" and "[timeseries](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_timeseries.csv)". Please choose the table type accordingly, depending on the data you want to upload:

- Use scalar tables to provide parameters with no relation to a timeindex. To properly fill the table, read the 
  [scalar model column description](https://github.com/sedos-project/oedatamodel#scalar-description). Use the 
  [example scalar package metadata](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/datamodel_scalars.json) to write your own metadata 
  (see section [How to contribute data - 2. Create metadata](http://127.0.0.1:8000/data_requirements/overview/#2#create#metadata)
- Use a timeseries table to provide parameters with relation to a timeindex. Use the [timeseries model column description](https://github.com/sedos-project/oedatamodel#timeseries-description) to make yourself familiar with the 
  fields and add metadata to your tables using the [example timeseries package metadata](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/datamodel_timeseries.json) as a reference.

### Input and output energy vectors
The input and output energy vectors of technologies in SEDOS' reference energy system are defined in an external table.

For technologies with multiple input and/or output energy vectors it might not clear to which energy vector a 
parameter column refers. Thus, the information has to be specified if needed.

When assigning the parameter `default` to a process, the subsequent specified input(s) and output(s) are assigned to 
**all** parameters in the corresponding process-csv. The `default` can be overwritten, simply by assigning other input(s) and output(s) to a specific parameter of 
the process.

## Data tables 


### Naming conventions for data tables and parameters
!!! warning "Note" 

    * Parameter name and table name conventions are in place due to technical reasons of the underlying relational postgre-sql database on the OEP. 

The following conventions will be automatically checked when uploading a table on the OEP, and error messages will be raised in case of violation.
Users need to correct them and their compliance is mandatory.

#### Do's
* use ASCII characters only
* use lower case only 
* use the singular instead of the plural.
* use underscores

#### Don'ts

* table name must not exceed maximal character limit = 50
* no points
* no commas
* no spaces
* no special characters
* avoid dates
* if dates are used, then without `-`! E.g.: 2022-10-21 will through an error. Use underscore instead!
* don't start parameter name with a number

### Delimiter 

Use semicolon `;` as the column delimiter. 

### Decimal separator 

Use point `.` as decimal separator. 

### Versioning convention
!!! Note "Versioning pattern"

    * `v` + `number` 


Version your data with **lowercase** letter `v` and arabic number, e.g.: v1

**Increase the version when** you want to **add or update data** to a table that has been already uploaded to the OEP. 
<br>

**Reasoning:** By following the versioning convention the end-user only needs to know the latest data version of a 
given process. Thus, querying the latest process data version will return a full set of coherent input data. 
<br>
Conversely, users only need to know one version number when querying older data versions to work with a full 
set of coherent input data for a process. 

Example: 

| id | region | year | capital_costs                             | lifetime                                 | bandwidth_type | version                                    | method | source | comment |
|----|--------|------|-------------------------------------------|------------------------------------------|----------------|--------------------------------------------|-------|--------|---------|
| 1  | DE     | 2020 | **<span style="color:blue"> 1 </span>**   | **<span style="color:blue"> 5 </span>**  |                | **<span style="color:blue"> v1 </span>**   |       |        |         |
| 2  | DE     | 2025 | **<span style="color:blue"> 1.5 </span>** | **<span style="color:blue"> 6 </span>**  |                | **<span style="color:blue"> v1 </span>**   |       |        |         |
| 3  | DE     | 2020 | 1                                         | 5                                        |                | **<span style="color:green"> v2 </span>**  |       |        |         |
| 4  | DE     | 2025 | 1.5                                       | 6                                        |                | **<span style="color:green"> v2 </span>**  |       |        |         |
| 5  | DE     | 2030 | **<span style="color:green"> 2 </span>**  | **<span style="color:green"> 8 </span>** |                | **<span style="color:green"> v2 </span>**  |       |        |         |
| 6  | DE     | 2020 | 1                                         | 5                                        |                | **<span style="color:red"> v3 </span>**    |       |        |         |
| 7  | DE     | 2025 | 1.5                                       | 6                                        |                | **<span style="color:red"> v3 </span>**    |       |        |         |
| 8  | DE     | 2030 | 2                                         | **<span style="color:red"> 15 </span>**  |                | **<span style="color:red"> v3 </span>**    |       |        |         |
| 9  | DE     | 2020 | 1                                         | 5                                        |                | **<span style="color:orange"> v4 </span>** |       |        |         |
| 10 | DE     | 2025 | 1.5                                       | 6                                        |                | **<span style="color:orange"> v4 </span>** |       |        |         |
| 11 | DE     | 2030 | **<span style="color:orange"> 4 </span>** | 15                                       |                | **<span style="color:orange"> v4 </span>** |       |        |         |

**<span style="color:blue"> v1 </span>**: **Initial data**

**<span style="color:green"> v2 </span>**: **Adding data** to your csv table requires a new version `v2` for new 
datapoints (capital_cost and lifetime in 2030, row=5), including a copy the existing data from `v1` as version `v2` 
(reasoning see above)

**<span style="color:red"> v3 </span>**: **Updating a datapoint** (lifetime, row=8) requires a new version 
`v3`, including a copy the existing data from `v2` as version `v3`

**<span style="color:orange"> v4 </span>**: **Updating a datapoint** (capital_costs, row=11) requires a new 
version `v4`, including a copy the existing data from `v3` as version `v4`

### Table naming

!!! warning "Note" 

    * Create a new datapackage for each process, e.g. wind_onshore, chp, ... <br>
    * You can use a single datapackage for both demand data and constraints (tech-independent parameters) if the table size is sufficient, e.g.:<br> * emission limit,<br> * natural domestic limit,<br> * WACC 

Follow the [nomenclature](nomenclature.md) for table and process naming.

## Parameter naming

!!! warning "Note" 

    * Parameter names must be linked to a concept in an ontology

Parameter names (to specify technologies, constraints or techno-economic values) can basically be chosen freely. 
However, it is of utmost importance that every parameter name is linked to a suitable ontological concept via the metadata to enable its clear interpretation.
<br> In case you cannot find a suitable ontology concept (e.g. because it's not in the ontology yet), please make sure 
your chosen parameter name is clear and common in the domain. In this case avoid acronyms.

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

