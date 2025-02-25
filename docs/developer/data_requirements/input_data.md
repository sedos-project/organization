## Input data

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

Follow the [nomenclature](../../visitor/data/nomenclature.md#process-nomenclature) for table and process naming.

!!! warning "Note" 

    * Create a new data package for each process, e.g. wind_onshore, chp, ... <br>
    * Or use the `type` column to put multiple processes in one data package
    * You can use a single datapackage for both demand data and other constraint data (tech-independent parameters),e.g.:<br> 
        * emission limit,<br> 
        * natural domestic limit,<br> 
        * WACC 



### Parameter naming

Follow the [nomenclature](../../visitor/data/nomenclature.md#parameter-nomenclature) for parameter naming.

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

#### Parameter naming in case of missing suitable ontology concept

It is likely that not every parameter concept is already covered by an ontology. In this case, linking your parameter name to a suitable ontology concept is not directly possible.

It might, however, be indirectly possible by linking it to a distinct selection of related ontology concepts. 
In this case you would link your parameter name to multiple related concepts.

For a practical manual linking parameter names to multiple related ontology concepts, using oemetadata builder, see [**here**](ontology.md#Link-a-parameter-name-to-multiple-related-ontology-concepts).


## Output Data

### Output Paramters
The model result data are structured within the following parameters:

- flow_volume
- losses
- costs_investment
- costs_variable
- costs_fixed
- capacity_inst
- capacity_new

### Result Table Format

The result table should be filled as follows - make sure to follow the format conventions:

| scenario                                  | year   | process                     | parameter         | sector | category | specification               | groups                 | new | input_groups         | output_groups         | unit   | value  |
|-------------------------------------------|-------:|-----------------------------|-------------------|--------|----------|-----------------------------|------------------------|----:|----------------------|-----------------------|--------|-------:|
| `<framework>_<model-structure>_<scenario>`| `<int>`| `<string>`                  | `<string>`        | `<string>`| `<string>`| `<python string array>`      | `<python string array>`| `<int>` | `<python string array>` | `<python string array>` | `<string>` | `<float>` |
| o_steel_tokio                            |   2030 | ind_cement_finish_1         | capacity_inst     | ind    | cement   | [‘finish’]                  | [‘future’, ‘industry’] |    1 |                      |                       | MW     |    100 |
| t_all_tokio                              |   2045 | x2x_x2liquid_oref_0         | costs_investment  | x2x    | x2liquid | [‘oref’]                    |                        |    0 |                      |                       | MEUR   |     10 |
| f_transport_tokio                        |   2030 | tra_road_lcar_ice_pass_flex_0 | flow_volume     | tra    | road     | [‘lcar’, ‘ice’, ‘pass’]     |                        |    0 | [‘sec_gasoline’]     |                       | MWh    |     50 |
| f_transport_tokio                        |   2030 | tra_road_lcar_ice_pass_flex_0 | flow_volume     | tra    | road     | [‘lcar’, ‘ice’, ‘pass’]     |                        |    0 | [‘sec_ethanol’]      |                       | MWh    |     30 |
| t_all_siena                              |   2030 | ind_cement_finish_1         | flow_volume       | ind    | cement   | [‘finish’]                  |                        |    1 |                      | [‘emi_co2_f_ind’]     | t      |    100 |
| t_all_siena                              |   2030 | ind_cement_finish_1         | flow_volume       | ind    | cement   | [‘finish’]                  |                        |    1 |                      | [‘emi_ch4_f_ind’]     | t      |      1 |
| t_all_siena                              |   2030 | ind_cement_finish_1         | flow_volume       | ind    | cement   | [‘finish’]                  |                        |    1 |                      | [‘emi_co2_eq’]        | t      |    128 |


