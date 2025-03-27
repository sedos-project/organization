# Heat sector

## Naming convention
The heat sector in the SEDOS dataset is divided into producers for district heating, such as heat plants, and in consumers. The consumers are split into household (hh) and commerce, trading and service (cts) buildings. The household buildings are seperated into rural (r), urban (u) and multihouseholds (m), the CTS buildings into service (t1) and production (t2) buildings. Each buildingtype in addition has an age type. For the household buildings it is divided into three different existing building ages (e1-3) and new buildings (n1). CTS buildings are split into existing (e) and new (n) buildings. The process names show wether it is a heating or cooling process and which technology it is (e.g. hp for heat pump). The processes are categorized in stock processes (0) and new build processes (1). The producers are split into the heat plants and the distribution grid. The heating plants are categorized into their energy carriers (coal, gas, biomass, etc.) and if they are stock or new processes. The grids are seperated into low temperature heat (LTH) and high temperature heat (HTH) grids. They are also specified wether they are connected to the HH or the CTS sector.

*Table 1: Nomenclature for the heat sector process naming.*

| Sector | Mode                 | building_type | process_name     |Stock/Expansion|
|--------|----------------------|---------------|------------------|---------------|
| hea    | hh                   | me1           | ...              | 0            |
|        |                      | me2           | ...              | 1             | 
|        |                      | me3           | ...             |                  | 
|        |                      | mn1           | ...             |                  | 
|        |                      | re1           | ...              |                  |
|        |                      | re2           | ...              |                  |
|        |                      | re3           | ...                 |                  |
|        |                      | rn1           | ...                 |                  |
|        |                      | ue1           | ...                 |                  |
|        |                      | ue2           | ...                 |                  |
|        |                      | ue3           | ...                 |                  |
|        |                      | un1           | ...                 |                  |
|        | cts                  | t1e           | ...                 |                  |
|        |                      | t1n           | ...                 |                  |
|        |                      | t2e           | ...                 |                  |
|        |                      | t2n           | ...                 |                  |
|        | disrict_heating      |               | ...                 |                  |


## Provided parameters

The scalar parameters provided are described in Table 2. 

*Table 2: Scalar parameters provided for the heat sector.*

| Parameter             | Unit                      | Explanation                                                                                               |
|-----------------------|---------------------------|-----------------------------------------------------------------------------------------------------------|
| potential_annual_max  | GW                        | Maximum possible capacity possibe by the process                                                        |
| capacity_p_inst_0     | kW                       | Existing power output capacity of a wallbox in a certain year.                                           |
| conversion_factor_commodity | PJ                 | Commodity-specific conversion factor (multiplication of input and output factors yields the efficiency of the process). |
| ef_commodity_emission | kt/PJ                    | Commodity-specific emission factor.                                                                      |
| exo_commodity         | PJ                       | Projected annual demand for a heating/cooling demand.                                                    |
| lifetime              | a                        | Technical lifetime of a process.                                                                         |
| cost_inv_p            | MEuro/GW                 | Investment costs.                                                                                        |
| cost_var_e            | Euro/GJ                  | variable costs.                                                                                          |
| cost_fix_p            | Euro/GW                  | costs that occure every year.                                                                            |
| flow_share_fix_commodity| -                       | Fix flow share of the commodity in the process.                                                          |
| availability_constant | -                        | availability of the process in a year.                                                          |



All costs are presented excluding taxes and subsidies, based on 2021 price levels.

## General modeling approach
The modeled heating processes can be categorized into three different types. The first are heating processes that have one input commodity and one output commodity. Then there are heating processes that either have one or two input commodities and one or two output commodities. The last type are cooling technologies. Furthermore there will be an in depth explenation for the district heating grid.

### Single heating technologies
For the processes with one input and one output commodity, they can be modeled by having a fixed ratio of conversion factors. In this model the output commodity is normalized to 1 and the input is 1 divided by the efficiency of the process.

### Dual heating technologies
For the first subtype, two inputs one output commodity, the processes have conversion factors and fixed flow shares. Both conversion factors of the input commodities are set to 1. Also both input commodites have a fixed flow share set from 0 to 1 that adds up to 1. The output commodity has the efficiency set as the conversion factor. Processes with one input and two outputs the input conversion factor is set to 1. The output commodities conversion factors are set to their commodity specific efficiency. Both output commodites have a fixed flow share from 0 to 1 that adds up to 1. For processes with two input and two output commodites the input commodities conversion factors are set to one. Both commodities have a fixed flow share from 0 to 1 that add up to 1. The output commodites conversion factors are set to the commodity specific efficiency. Both commodities have a fixed flow share from 0 to 1 that add up to 1. 

### Cooling technologies
Cooling processes have one input and one output commodity, they can be modelled by having a fixed ratio of conversion factors. In this model the input commodity is normalized to 1 and the output is given by the conversion factor of the process.

### District heating grids
The costs of district heating is depending on the amount of demand in a specific area. The more dense an area is, the lower is the delivery costs for district heating. This means that the model has to take into account a varying cost level depending on the building type and the area where the district heating grid would be build. In SEDOS every building type has its own district heating grid modeled with different steps. The first step is the already existing district heating network in Germany. Every next step has a fixed capacity that can be build. Each step is getting increasingly more expensive due to the less dense area it would be build in. Therefore there is a point where building new grids for specific building types isn't cost efficient anymore and the model will change to different heating methods.