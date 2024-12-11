# Input data 

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
* no hyphens. If dates are used, then without `-`! E.g.: 2022-10-21 will through an error. Use underscore instead!
* don't start parameter name with a number

### Delimiter 

Use semicolon `;` as the column delimiter. 

### Decimal separator 

Use point `.` as decimal separator. 

[//]: # (### Versioning convention)

[//]: # (??? Note "Versioning pattern")

[//]: # (    )
[//]: # (    <br>**For SEDOS Reference Dataset** &#40;SRD&#41;<br><br>)

[//]: # (    `v` + `number` <br>)

[//]: # (    Version your data with **lowercase** letter `v` and arabic number, e.g.: v1, v2, v3, v4, ..., v12, v13)

[//]: # (    <br><br>)

[//]: # (    **For SEDOS Scenarios** <br><br>)

[//]: # (    When the data for the SRD is final, specific scenarios will be uploaded to showcase the application of the SRD in practice.)

[//]: # (    It's done by selecting specific values from SRD's bandwidths and appending them with a `scenario version` to )

[//]: # (    respective tables. <br><br> )

[//]: # (    `s` + `number` <br>)

[//]: # (    Version your data with **lowercase** letter `s` and arabic number, e.g.: s1, s2, s3, s4, ..., s12, s13)

[//]: # (    )
[//]: # (**Increase the version when** you want to **add or update data** to a table that has been already uploaded to the OEP.)

[//]: # (The oedatamodel-API will append new data versions to an existing OEP table.)

[//]: # (<br>)

[//]: # ()
[//]: # (**Reasoning:** By following the versioning convention the end-user only needs to know the latest data version of a )

[//]: # (given process. Thus, querying the latest process data version will return a full set of coherent input data. )

[//]: # (<br>)

[//]: # (Conversely, users only need to know one version number when querying older data versions to work with a full )

[//]: # (set of coherent input data for a process. )

[//]: # ()
[//]: # (**<span style="color:blue"> v1 </span>**: **Initial data**)

[//]: # ()
[//]: # (| id | region | year | type | capital_costs                            | lifetime                                 | bandwidth_type | version                                    | method | source | comment |)

[//]: # (|----|--------|------|------|-------------------------------------------|------------------------------------------|----------------|--------------------------------------------|-------|--------|---------|)

[//]: # (| 1  | DE     | 2020 |      | **<span style="color:blue"> 1 </span>**   | **<span style="color:blue"> 5 </span>**  |                | **<span style="color:blue"> v1 </span>**   |       |        |         |)

[//]: # (| 2  | DE     | 2025 |      | **<span style="color:blue"> 1.5 </span>** | **<span style="color:blue"> 6 </span>**  |                | **<span style="color:blue"> v1 </span>**   |       |        |         |)

[//]: # ()
[//]: # (**<span style="color:green"> v2 </span>**: **Adding data** to your csv table requires a new version `v2` for new )

[//]: # (datapoints &#40;capital_cost and lifetime in 2030, row=5&#41;, including a copy the existing data from `v1` as version `v2` )

[//]: # (&#40;reasoning see above&#41;)

[//]: # ()
[//]: # (| id | region | year | type | capital_costs                            | lifetime                                 | bandwidth_type | version                                    | method | source | comment |)

[//]: # (|----|--------|------|------|------------------------------------------|------------------------------------------|----------------|--------------------------------------------|-------|--------|---------|)

[//]: # (| 1  | DE     | 2020 |      | 1                                        | 5                                        |                | **<span style="color:green"> v2 </span>**  |       |        |         |)

[//]: # (| 2  | DE     | 2025 |      | 1.5                                      | 6                                        |                | **<span style="color:green"> v2 </span>**  |       |        |         |)

[//]: # (| 3  | DE     | 2030 |      | **<span style="color:green"> 2 </span>** | **<span style="color:green"> 8 </span>** |                | **<span style="color:green"> v2 </span>**  |       |        |         |)

[//]: # ()
[//]: # (**<span style="color:red"> v3 </span>**: **Updating a datapoint** &#40;lifetime, row=8&#41; requires a new version )

[//]: # (`v3`, including a copy the existing data from `v2` as version `v3`)

[//]: # ()
[//]: # (| id | region | year | type | capital_costs | lifetime| bandwidth_type | version                                    | method | source | comment |)

[//]: # (|----|--------|------|------|---------------|------------------------------------------|----------------|--------------------------------------------|-------|--------|---------|)

[//]: # (| 1  | DE     | 2020 |      | 1             | 5                                        |                | **<span style="color:red"> v3 </span>**    |       |        |         |)

[//]: # (| 2  | DE     | 2025 |      | 1.5           | 6                                        |                | **<span style="color:red"> v3 </span>**    |       |        |         |)

[//]: # (| 3  | DE     | 2030 |      | 2             | **<span style="color:red"> 15 </span>**  |                | **<span style="color:red"> v3 </span>**    |       |        |         |)

[//]: # ()
[//]: # (**<span style="color:orange"> v4 </span>**: **Updating a datapoint** &#40;capital_costs, row=11&#41; requires a new )

[//]: # (version `v4`, including a copy the existing data from `v3` as version `v4`)

[//]: # ()
[//]: # (| id | region | year | type | capital_costs                            | lifetime| bandwidth_type | version                                    | method | source | comment |)

[//]: # (|----|--------|------|------|------------------------------------------|------------------------------------------|----------------|--------------------------------------------|-------|--------|---------|)

[//]: # (| 1  | DE     | 2020 |      | 1                                        | 5                                        |                | **<span style="color:orange"> v4 </span>** |       |        |         |)

[//]: # (| 2  | DE     | 2025 |      | 1.5                                      | 6                                        |                | **<span style="color:orange"> v4 </span>** |       |        |         |)

[//]: # (| 3  | DE     | 2030 |      | **<span style="color:orange"> 4 </span>** | 15                                       |                | **<span style="color:orange"> v4 </span>** |       |        |         |)

[//]: # ()
[//]: # ()
[//]: # (!!! Note "`id` column numbering" )

[//]: # ()
[//]: # (    If you check `Automatically increase IDs, if IDs are already present in table` in the OEDatamodel-api when )

[//]: # (    uploading the data, the id's will be updated automatically - as shown in the _Example result on OEP_ below.)

[//]: # ()
[//]: # (Example result on OEP: )

[//]: # ()
[//]: # (| id | region | year | type | capital_costs                              | lifetime| bandwidth_type | version                                    | method | source | comment |)

[//]: # (|----|--------|------|------|--------------------------------------------|------------------------------------------|----------------|--------------------------------------------|-------|--------|---------|)

[//]: # (| 1  | DE     | 2020 |      | **<span style="color:blue"> 1 </span>**    | **<span style="color:blue"> 5 </span>**  |                | **<span style="color:blue"> v1 </span>**   |       |        |         |)

[//]: # (| 2  | DE     | 2025 |      | **<span style="color:blue"> 1.5 </span>**  | **<span style="color:blue"> 6 </span>**  |                | **<span style="color:blue"> v1 </span>**   |       |        |         |)

[//]: # (| 3  | DE     | 2020 |      | 1                                          | 5                                        |                | **<span style="color:green"> v2 </span>**  |       |        |         |)

[//]: # (| 4  | DE     | 2025 |      | 1.5                                        | 6                                        |                | **<span style="color:green"> v2 </span>**  |       |        |         |)

[//]: # (| 5  | DE     | 2030 |      | **<span style="color:green"> 2 </span>**   | **<span style="color:green"> 8 </span>** |                | **<span style="color:green"> v2 </span>**  |       |        |         |)

[//]: # (| 6  | DE     | 2020 |      | 1                                          | 5                                        |                | **<span style="color:red"> v3 </span>**    |       |        |         |)

[//]: # (| 7  | DE     | 2025 |      | 1.5                                        | 6                                        |                | **<span style="color:red"> v3 </span>**    |       |        |         |)

[//]: # (| 8  | DE     | 2030 |      | 2                                          | **<span style="color:red"> 15 </span>**  |                | **<span style="color:red"> v3 </span>**    |       |        |         |)

[//]: # (| 9  | DE     | 2020 |      | 1                                          | 5                                        |                | **<span style="color:orange"> v4 </span>** |       |        |         |)

[//]: # (| 10 | DE     | 2025 |      | 1.5                                        | 6                                        |                | **<span style="color:orange"> v4 </span>** |       |        |         |)

[//]: # (| 11 | DE     | 2030 |      |  **<span style="color:orange"> 4 </span>** | 15                                       |                | **<span style="color:orange"> v4 </span>** |       |        |         |)

[//]: # ()
[//]: # ()
[//]: # (!!! Note "Versioning note")

[//]: # ()
[//]: # (    * Uploading a row which exists already in: "region, type, year, version" results in an error. )

[//]: # (    * Otherwise single or multiple rows can be added to already existing versions)


#### SEDOS Reference Dataset (SRD) versioning

For the SRD, the following version tags apply:

* **srd_range_sedos**: Final SRD with ranges to include parametric uncertainty from different sources. 
* **srd_range_v1**: Updated SRD, after project end. 
* **srd_point_sedos**: SEDOS-specific values from srd_range_sedos that serve as a basis for all scnearios. 

### Datatypes

Available datatypes and corresponding formatting examples:

|    dtype    |                  example                   |                                                                           comment                                                                            |
|:-----------:|:------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    json     | "{""key1"": ""text"", ""key2"": ""text""}" |                      {"key1": "text", ...} might work as well. If you're using an table edititor make sure to use ASCII characters only                      |                                         |
| float array |               [0.02, 279.5]                |                                         arrays with strings should be formatted as strings ("['string1', 'string2']"                                         |
|    text     |                   "text"                   |                                              String data should have text as datatype (text serves as "string")                                              |
|   integer   |                     27                     |                                                                                                                                                              |
| text array  |              "[""TH"", ""BW""]"              |                           ["TH","BW"] might work as well. If you're using an table edititor make sure to use ASCII characters only                           |

### Table naming

Follow the [nomenclature](https://bwsyncandshare.kit.edu/f/2458081675) for table and process naming in sheet: 
**Nomenclature_Processes**.

!!! warning "Note" 

    * Create a new data package for each process, e.g. wind_onshore, chp, ... <br>
    * Or use the `type` column to put multiple processes in one data package
    * You can use a single datapackage for both demand data and other constraint data (tech-independent parameters),e.g.:<br> 
        * emission limit,<br> 
        * natural domestic limit,<br> 
        * WACC 



## Parameter naming

Follow the [nomenclature](https://bwsyncandshare.kit.edu/f/2458081675) for parameter naming in sheet: 
**Parameter_Set**.

!!! warning "Note" 

    * Parameter names must be linked to a concept in an ontology

It is importance that every parameter name is linked to a suitable ontological concept via the metadata to enable 
its clear interpretation.
<br> In case you cannot find a suitable ontology concept (e.g. because it's not in the ontology yet), please make sure 
your chosen parameter name is clear and common in the domain. In this case avoid acronyms. <br>

!!! note "Ontological annotations" 

    * In the [nomenclature](https://bwsyncandshare.kit.edu/f/2458081675) for parameter naming in sheet: 
    **Parameter_Set**, we made suggestions for suitable ontology concepts for usage across the SEDOS APs. 
    <br><br>Please use them or make suggestions of better suitable concepts.

For more background information regarding for linking parameter names and ontology concepts, using OEM, see [**here**](ontology.md#Ontological-annotation-of-data).

For a practical manual linking parameter names to a suitable ontology concepts, using oemetadata builder, see [**here**](ontology.md#Link-a-parameter-name-to-a-suitable-ontology-concept).

### Parameter naming in case of missing suitable ontology concept

It is likely that not every parameter concept is already covered by an ontology. In this case, linking your parameter name to a suitable ontology concept is not directly possible.

It might, however, be indirectly possible by linking it to a distinct selection of related ontology concepts. 
In this case you would link your parameter name to multiple related concepts.

For a practical manual linking parameter names to multiple related ontology concepts, using oemetadata builder, see [**here**](ontology.md#Link-a-parameter-name-to-multiple-related-ontology-concepts).

<!-- 

@CM, HeHu, others uncomment and add section when time has come ..... :/

# Output Data 


## Output Datamodel

Datamodel: The **OEDatamodel** is used to represent input/output data for energysystem modelling. 
Further information about the OEDatamodel can be found in the documentation at [sedos-project/oedatamodel](https://github.com/sedos-project/oedatamodel).

-->