# Data conventions

## Background information

This section provides additional information on parameters and on the interpretation of their possible values.

??? note "Information on special parameters"

    === "`conversion_factor_<commodity>`"
        Having many Multiple-Input-Multiple-Output (MIMO) processes in the model structure, efficiencies are considered with the parameter `conversion_factor`.
        We use the same naming convention for all parameters that describe the ratios of inputs and outputs in relation to the primary commodity. <br>
        The primary commodity (conversion_factor = 1) is per default the first output of the process. <br>
        
        For consistency please check that the calorific values (heating values) that your conversion factors are based on, are consistent with the
        values defined in "calorific_values_SEDOS" in the supplementary files at the sharepoint.<br>
        
        The TIMES adapter needs to convert the conversion factors into their parameter conventions and an automatic identification and naming of the commodity groups.
        as required by the framework.

    === "`flow_share_min/max/fix`"
        This parameter can be defined to bound flow shares within the commodity groups of MIMO processes that by default have flexible ratios. <br>
        e.g. for a hydrogen-ready gas turbine (that can either burn methane or h2 in the MIMO-process) the hydrogen flow for every 
        timestep could be restricted to a ratio of 0.3 with `flow_share_max=0.3`.

    === "`capacity_p_abs_new_max`"

        Growth rates of processes should be considered with `capacity_p_abs_new_max` or `capacity_e_abs_new_max` parameter. 
        It describes absolute upper bounds for the expansion of capacities per milestone year. Please consider the deviating 
        period lengths for different milestone years when you determine the upper bounds.
        This parameter should be given for a process only if it is based on reasonable assumptions or data.
        Please include its background in your AP specific documentation. The transport sector considers growth rates with the market shares.

    === "`wacc`"

        The weighted average cost of capital (wacc) gives the interest rate (%) of costs for capital after taxes. 
        As we follow a macro-economic approach in SEDOS it is globally defined for all technologies with a value of 2 percent.
        Please link it to the `global_scalars` table as explained in the note `Linking data with foreign keys`.

??? note "Existing and investment processes"
            
    === "Existing processes"
        Processes that were existing before the base year 2021 can be identified on their name. They end with `_0`
        <br>
        Example: `pow_combustion_gt_hydrogen_0`

    === "Investment processes"
        Processes that were not existing before the base year 2021 and that the model can invest in can be 
        identified on their name. They end with `_1`
        <br>
        Example: `pow_combustion_cc_chp_ccs_biomass_1`

??? note "Parameter_Input-Output"
    
    The Parameter_Input-Output relations are important to link relevant flow-specific parameters to input or output commodities 
    of a MIMO process. Due to the high number of MIMO processes in our model structure we defined defaults for these relations: <br><br>
    **Cost parameters are directly related to the throughput power capacity based on the given primary commodity** 
    (first output of a process with conversion_factor = 1). <br><br>
    Moreover, the following parameters are per default directly derived from the parameter names in your uploaded data. <br>
    - `conversion_factor_<commodity>` <br>
    - `flow_share_max_<commodity>` <br>
    - `emission_factor_<commodity>_<emission_commodity>` <br>
    Please make sure that the names accurately fit to this schema. Otherwise, the data adapter will not recognize the 
    uploaded data and the relation of the parameters can not be defined. <br>

    For exceptions to these defaults please use the "Parameter_Input-Output" sheet to clearly indicate that the parameter relations do not follow these defaults.
    e.g. the investment costs of an electrolyzer that are defined in relation to the input power capacity.

??? note "Monetary value"
    
    If not further specified the base year for the monatary value is 2021.

    If monatary conversion were performed, the following logic was applied: <br>
    _currency_A(year_x) -> currency_B(year_x) -> currency_B(year_z)_ <br>
    e.g. USD2010 -> EUR2010 -> EUR2021 <br>

    For the conversion please use the provided table "monetary_conversion" in the supplementary files at the sharepoint. 
    The conversion is based on data from the ECB for the exchange rates and from the StBA for the harmonised index of consumer prices. <br>
    The original years of the sources can be documented in the method column - e.g. {`Investment costs`:`Conversion from USD2019`}

??? note "Leap years"

      Leap years are considered in timeseries data by setting the timeindex_stop for **2024, 2040, 2060** to 
      the **30.12.** <br> The timesseries has only 8760 instead of 8784 timesteps (-> the 31.12 is missing).

      ```python
      | id   | region   | type   | timeindex_start       | timeindex_stop        | timeindex_resolution   | exo_pkm_road_mcar   | version   | method   | source   | comment   |
      |------|----------|--------|-----------------------|-----------------------|------------------------|---------------------|-----------|----------|----------|-----------|
      | 1    | DE       |        | 2021-01-01 00:00:00   | 2021-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 2    | DE       |        | 2024-01-01 00:00:00   | 2024-12-30 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 3    | DE       |        | 2027-01-01 00:00:00   | 2027-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 4    | DE       |        | 2030-01-01 00:00:00   | 2030-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 5    | DE       |        | 2035-01-01 00:00:00   | 2035-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 6    | DE       |        | 2040-01-01 00:00:00   | 2040-12-30 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 7    | DE       |        | 2045-01-01 00:00:00   | 2045-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 8    | DE       |        | 2050-01-01 00:00:00   | 2050-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 9    | DE       |        | 2060-01-01 00:00:00   | 2060-12-30 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      | 10   | DE       |        | 2070-01-01 00:00:00   | 2070-12-31 23:00:00   | 1h                     | [1,2,3,…,8760]      | v1        |          |          |           |
      ```

??? note "Structure of energy demands"
      
      Demands per sector are provided via three tables: <br>
      1. `<sector>_scalars` <br>
      2. `<sector>_timeseries` <br>
      3. `<sector>_demand` <br>

      The structure is exemplified on the transport sector below.
      
    === "`tra_scalars`"
         The table collects all sector process-unspecific scalars. <br>
         Also the annual demands. Demand columns are named as the commodity (unit must be declared via metadata)

         ```python
         | id | region | year | type | exo_pkm_road_mcar | exo_tkm_rail | exo_tkm_rail_short | exo_pkm_road_lcar | bandwidth_type | version | method | source | comment |
         |----|--------|------|------|-------------------|--------------|--------------------|-------------------|----------------|---------|--------|--------|---------|
         | 1  | DE     | 2021 |      | 34.4              | 100          | 1000               | 66                |                |         |        |        |         |
         | 2  | DE     | 2024 |      | 34.4              | 101          | 1001               | 67                |                |         |        |        |         |
         | 3  | DE     | 2027 |      | 34.4              | 102          | 1002               | 68                |                |         |        |        |         |
         | 4  | DE     | 2030 |      | 34.4              | 103          | 1003               | 69                |                |         |        |        |         |
         | 5  | DE     | 2035 |      | 34.4              | 104          | 1004               | 70                |                |         |        |        |         |
         | 6  | DE     | 2040 |      | 34.4              | 105          | 1005               | 71                |                |         |        |        |         |
         | 7  | DE     | 2045 |      | 34.4              | 106          | 1006               | 72                |                |         |        |        |         |
         | 8  | DE     | 2050 |      | 34.4              | 107          | 1007               | 73                |                |         |        |        |         |
         | 9  | DE     | 2060 |      | 34.4              | 108          | 1008               | 74                |                |         |        |        |         |
         | 10 | DE     | 2070 |      | 34.4              | 109          | 1009               | 75                |                |         |        |        |         |
         ```


    === "`tra_timeseries`"
         The table collects all sector timeseries - also the demand timeseries. <br>
         Note that leap years are considered in time series data by setting the timeindex_stop for 2024, 2040, 2060 to the 30.12.
        
         ```python
         | id | region | type | timeindex_start     | timeindex_stop      | timeindex_resolution | exo_pkm_road_mcar | exo_tkm_rail   | exo_tkm_rail_short | exo_pkm_road_lcar | exo_pkm_road_xcar | version | method | source | comment |
         |----|--------|------|---------------------|---------------------|----------------------|-------------------|----------------|--------------------|-------------------|-------------------|---------|--------|--------|---------|
         | 1  | DE     |      | 2021-01-01 00:00:00 | 2021-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 2  | DE     |      | 2024-01-01 00:00:00 | 2024-12-30 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 3  | DE     |      | 2027-01-01 00:00:00 | 2027-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 4  | DE     |      | 2030-01-01 00:00:00 | 2030-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 5  | DE     |      | 2035-01-01 00:00:00 | 2035-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 6  | DE     |      | 2040-01-01 00:00:00 | 2040-12-30 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 7  | DE     |      | 2045-01-01 00:00:00 | 2045-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 8  | DE     |      | 2050-01-01 00:00:00 | 2050-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 9  | DE     |      | 2060-01-01 00:00:00 | 2060-12-30 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         | 10 | DE     |      | 2070-01-01 00:00:00 | 2070-12-31 23:00:00 | 1h                   | [1,2,3,…,8760]    | [1,2,3,…,8760] | [1,2,3,…,8760]     | [1,2,3,…,8760]    | [1,2,3,…,8760]    | v1      |        |        |         |
         ```
       
    === "`tra_demand`"
         In column "demand_annual" the scalar demand is mapped via foreign-key & also the units via the metadata from 
         the `tra_scalars` table.
         The normalised timeseries are mapped in the "demand_timeseries_fixed" column via Foreign-key.
        
         ```python
         | id | region | year | type                           | demand_annual                 | demand_timeseries_fixed          | bandwidth_type | version | method | source | comment |
         |----|--------|------|--------------------------------|-------------------------------|-----------------------------------|----------------|---------|--------|--------|---------|
         | 1  | DE     | 2021 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 2  | DE     | 2024 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 3  | DE     | 2027 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 4  | DE     | 2030 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 5  | DE     | 2035 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 6  | DE     | 2040 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 7  | DE     | 2045 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 8  | DE     | 2050 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 9  | DE     | 2060 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 10 | DE     | 2070 | helper_sink_exo_tkm_rail       | tra_scalars.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 11 | DE     | 2021 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 12 | DE     | 2024 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 13 | DE     | 2027 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 14 | DE     | 2030 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 15 | DE     | 2035 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 16 | DE     | 2040 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 17 | DE     | 2045 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 18 | DE     | 2050 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 19 | DE     | 2060 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 20 | DE     | 2070 | helper_sink_exo_tkm_rail_short | tra_scalars.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 21 | DE     | 2021 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 22 | DE     | 2024 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 23 | DE     | 2027 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 24 | DE     | 2030 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 25 | DE     | 2035 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 26 | DE     | 2040 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 27 | DE     | 2045 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 28 | DE     | 2050 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 29 | DE     | 2060 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 30 | DE     | 2070 | helper_sink_exo_pkm_road_mcar  | tra_scalars.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 31 | DE     | 2021 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 32 | DE     | 2024 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 33 | DE     | 2027 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 34 | DE     | 2030 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 35 | DE     | 2035 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 36 | DE     | 2040 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 37 | DE     | 2045 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 38 | DE     | 2050 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 39 | DE     | 2060 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 40 | DE     | 2070 | helper_sink_exo_pkm_road_lcar  | tra_scalars.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         ```



??? note "Empty cells and value 0"

    **Example table**: <br>
    ```python
    | id | region | year | type | capacity_p_inst                     | capacity_p_abs_new_max | conversion_factor_sec_elec | lifetime | cost_inv_capacity_p | cb_coefficient | cv_coefficient | bandwidth_type | version | method | source | comment |
    |----|--------|------|------|-------------------------------------|------------------------|----------------------------|----------|---------------------|----------------|----------------|----------------|---------|--------|--------|---------|
    | 1      | DE   | 2021 | pow_combustion_cc_chp_ccs_biomass_1 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 2      | DE   | 2024 | pow_combustion_cc_chp_ccs_biomass_1 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 3      | DE   | 2027 | pow_combustion_cc_chp_ccs_biomass_1 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 4      | DE   | 2030 | pow_combustion_cc_chp_ccs_biomass_1 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 5      | DE   | 2035 | pow_combustion_cc_chp_ccs_biomass_1 |                        |                            | 0.8      | 25                  | 1000           | 0.4            | 0.6            |         |        |        |         |   |
    | 6      | DE   | 2040 | pow_combustion_cc_chp_ccs_biomass_1 |                        |                            | 0.8      | 25                  | 1000           | 0.4            | 0.6            |         |        |        |         |   |
    | 7      | DE   | 2045 | pow_combustion_cc_chp_ccs_biomass_1 |                        |                            | 0.8      | 25                  | 800            | 0.4            | 0.6            |         |        |        |         |   |
    | 8      | DE   | 2050 | pow_combustion_cc_chp_ccs_biomass_1 |                        |                            | 0.8      | 30                  | 800            | 0.4            | 0.6            |         |        |        |         |   |
    | 9      | DE   | 2060 | pow_combustion_cc_chp_ccs_biomass_1 |                        |                            | 0.8      | 30                  | 800            | 0.4            | 0.6            |         |        |        |         |   |
    | 10     | DE   | 2070 | pow_combustion_cc_chp_ccs_biomass_1 |                        |                            | 0.8      | 30                  | 600            | 0.4            | 0.6            |         |        |        |         |   |
    | 11     | DE   | 2021 | pow_geothermal_st_1                 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 12     | DE   | 2024 | pow_geothermal_st_1                 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 13     | DE   | 2027 | pow_geothermal_st_1                 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 14     | DE   | 2030 | pow_geothermal_st_1                 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 15     | DE   | 2035 | pow_geothermal_st_1                 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 16     | DE   | 2040 | pow_geothermal_st_1                 |                        | 0                          |          |                     |                |                |                |         |        |        |         |   |
    | 17     | DE   | 2045 | pow_geothermal_st_1                 |                        |                            | 0.4      | 25                  | 800            |                |                |         |        |        |         |   |
    | 18     | DE   | 2050 | pow_geothermal_st_1                 |                        |                            | 0.4      | 30                  | 800            |                |                |         |        |        |         |   |
    | 19     | DE   | 2060 | pow_geothermal_st_1                 |                        |                            | 0.4      | 30                  | 800            |                |                |         |        |        |         |   |
    | 20     | DE   | 2070 | pow_geothermal_st_1                 |                        |                            | 0.4      | 30                  | 600            |                |                |         |        |        |         |   |
    | 21     | DE   | 2021 | pow_combustion_gt_hydrogen_0        | 3500                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 22     | DE   | 2024 | pow_combustion_gt_hydrogen_0        | 3500                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 23     | DE   | 2027 | pow_combustion_gt_hydrogen_0        | 3500                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 24     | DE   | 2030 | pow_combustion_gt_hydrogen_0        | 3300                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 25     | DE   | 2035 | pow_combustion_gt_hydrogen_0        | 3000                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 26     | DE   | 2040 | pow_combustion_gt_hydrogen_0        | 2700                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 27     | DE   | 2045 | pow_combustion_gt_hydrogen_0        | 1500                   |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 28     | DE   | 2050 | pow_combustion_gt_hydrogen_0        | 200                    |                            | 0.6      | 20                  | 500            |                |                |         |        |        |         |   |
    | 29     | DE   | 2060 | pow_combustion_gt_hydrogen_0        | 0                      |                            |          |                     |                |                |                |         |        |        |         |   |
    | 30     | DE   | 2070 | pow_combustion_gt_hydrogen_0        | 0                      |                            |          |                     |                |                |                |         |        |        |         |   |
    ```
              

    === "Empty cells"
        **Parameter values that do not exist for a given year, process and parameter combination have no relevance for a process.** <br><br>
        Example:
        ```python
        | id | region | year | type                                | capacity_p_inst    |
        |----|--------|------|-------------------------------------|--------------------|
        | 1  | DE     | 2021 | pow_combustion_cc_chp_ccs_biomass_1 |                    | 
        | 2  | DE     | 2024 | pow_combustion_cc_chp_ccs_biomass_1 |                    |
        ```
    
        <span style="color:red"> **Exception**: Unrestricted bound parameters </span>
    
        **Upper and lower bound paramters have empty cells if unrestricted**. <br> This convention was made to avoid 
        high or low dummy values for upper or lower bounds.<br><br>
        In the example above, new capacity investments (`capacity_p_abs_new_max`) for the processes are not restricted: <br>
        ```python
        | id | region | year | type                                 | capacity_p_abs_new_max |
        |----|--------|------|--------------------------------------|------------------------|
        | 5  | DE     | 2035 | pow_combustion_cc_chp_ccs_biomassl_1 |                        |
        | 6  | DE     | 2040 | pow_combustion_cc_chp_ccs_biomassl_1 |                        |
        | 7  | DE     | 2045 | pow_combustion_cc_chp_ccs_biomassl_1 |                        |
        | 8  | DE     | 2050 | pow_combustion_cc_chp_ccs_biomassl_1 |                        |
        | 9  | DE     | 2060 | pow_combustion_cc_chp_ccs_biomassl_1 |                        |
        | 10 | DE     | 2070 | pow_combustion_cc_chp_ccs_biomassl_1 |                        |
        | 17 | DE     | 2045 | pow_geothermal_st_1                  |                        |
        | 18 | DE     | 2050 | pow_geothermal_st_1                  |                        |
        | 19 | DE     | 2060 | pow_geothermal_st_1                  |                        |
        | 20 | DE     | 2070 | pow_geothermal_st_1                  |                        |
        ```
        <br>
        **Other bounds parameters**
        ```python
        | SEDOS parameter name     | Recommended unit   | Description                                                                                |
        |--------------------------|--------------------|--------------------------------------------------------------------------------------------|
        | capacity_p_abs_new_max   | MW                 | Absolute upper bound on level of investment in new power output capacity for a period.     |
        | capacity_e_abs_new_max   | MWh                | Absolute upper bound on level of investment in new storage energy capacity for a period.   |
        | capacity_w_abs_new_max   | Mt                 | Absolute upper bound on level of investment in new weight capacity for a period.           |
        | activity_bound_min       | Mt/year            | Lower bound on the activity level of a process.                                            |
        | activity_bound_fix       | Mt/year            | Fix bound on the activity level of a process.                                              |
        | activity_bound_max       | Mt/year            | Upper bound on the activity level of a process.                                            |
        | demand_timeseries_lower  | MWh, pkm, tkm      | Lower bound for demand timeseries.                                                         |
        | demand_timeseries_upper  | MWh, pkm, tkm      | Upper bound for demand timeseries.                                                         |
        ```
  
    === "Value 0"
        **The value is actually zero for a given year, process and parameter.**<br><br>
        Example: Existing capacity for `pow_combustion_gt_hydrogen_0` in 2060 is zero. <br>
        ```python
        | id | region | year | type                                 | capacity_p_inst    |   
        |----|--------|------|--------------------------------------|--------------------|
        | 29 | DE     | 2060 | pow_combustion_gt_hydrogen_0         | 0                  |   
        ```
    
??? note "Over specification of processes"

    **Example table**: <br>
    ```python
    | id | region | year     | type   | capacity_p_inst                        | capacity_p_abs_new_max | conversion_factor_sec_elec | lifetime                     | cost_inv_capacity_p | cb_coefficient        | cv_coefficient   | bandwidth_type   | version          | method    | source   | comment  |           |
    |----|--------|----------|--------|----------------------------------------|------------------------|----------------------------|------------------------------|---------------------|-----------------------|------------------|------------------|------------------|-----------|----------|----------|-----------|
    |    | 1      | DE       | 2021   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 2      | DE       | 2024   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 3      | DE       | 2027   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 4      | DE       | 2030   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 5      | DE       | 2035   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 25                  | 1000                  | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 6      | DE       | 2040   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 25                  | 1000                  | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 7      | DE       | 2045   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 25                  | 800                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 8      | DE       | 2050   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 30                  | 800                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 9      | DE       | 2060   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 30                  | 800                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 10     | DE       | 2070   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 30                  | 600                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 11     | DE       | 2021   | pow_geothermal_st_1                    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 12     | DE       | 2024   | pow_geothermal_st_1                    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 13     | DE       | 2027   | pow_geothermal_st_1                    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 14     | DE       | 2030   | pow_geothermal_st_1                    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 15     | DE       | 2035   | pow_geothermal_st_1                    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 16     | DE       | 2040   | pow_geothermal_st_1                    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 17     | DE       | 2045   | pow_geothermal_st_1                    |                        |                            | 0.4                          | 25                  | 800                   |                  |                  |                  |           |          |          |           |
    |    | 18     | DE       | 2050   | pow_geothermal_st_1                    |                        |                            | 0.4                          | 30                  | 800                   |                  |                  |                  |           |          |          |           |
    |    | 19     | DE       | 2060   | pow_geothermal_st_1                    |                        |                            | 0.4                          | 30                  | 800                   |                  |                  |                  |           |          |          |           |
    |    | 20     | DE       | 2070   | pow_geothermal_st_1                    |                        |                            | 0.4                          | 30                  | 600                   |                  |                  |                  |           |          |          |           |
    |    | 21     | DE       | 2021   | pow_combustion_gt_hydrogen_0           | 3500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 22     | DE       | 2024   | pow_combustion_gt_hydrogen_0           | 3500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 23     | DE       | 2027   | pow_combustion_gt_hydrogen_0           | 3500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 24     | DE       | 2030   | pow_combustion_gt_hydrogen_0           | 3300                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 25     | DE       | 2035   | pow_combustion_gt_hydrogen_0           | 3000                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 26     | DE       | 2040   | pow_combustion_gt_hydrogen_0           | 2700                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 27     | DE       | 2045   | pow_combustion_gt_hydrogen_0           | 1500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 28     | DE       | 2050   | pow_combustion_gt_hydrogen_0           | 200                    |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 29     | DE       | 2060   | pow_combustion_gt_hydrogen_0           | 0                      |                            |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 30     | DE       | 2070   | pow_combustion_gt_hydrogen_0           | 0                      |                            |                              |                     |                       |                  |                  |                  |           |          |          |           |
    ```

    To avoid ambiguities in the data, the processes are specified as precisely as possible. <br> This means, for 
    example, for investment processes all years are specified in the data, even if an investment process is only
    available from later years, e.g 2035, as opposed to missing rows for 2021, 2024, 2027 and 2030. <br>    
    To avoid data misinterpretation, the techno-economic parameter values for 2021, 2024, 2027 and 2030 are empty, 
    since the process does not exist yet in such years.
    <br>
    ```python
    | id | region | year     | type   | capacity_p_inst                        | capacity_p_abs_new_max | conversion_factor_sec_elec | lifetime                     | cost_inv_capacity_p | cb_coefficient        | cv_coefficient   | bandwidth_type   | version          | method    | source   | comment  |           |
    |----|--------|----------|--------|----------------------------------------|------------------------|----------------------------|------------------------------|---------------------|-----------------------|------------------|------------------|------------------|-----------|----------|----------|-----------|
    |    | 1      | DE       | 2021   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 2      | DE       | 2024   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 3      | DE       | 2027   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 4      | DE       | 2030   | pow_combustion_cc_chp_ccs_biomass_1    |                        | 0                          |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 5      | DE       | 2035   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 25                  | 1000                  | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 6      | DE       | 2040   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 25                  | 1000                  | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 7      | DE       | 2045   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 25                  | 800                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 8      | DE       | 2050   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 30                  | 800                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 9      | DE       | 2060   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 30                  | 800                   | 0.4              | 0.6              |                  |           |          |          |           |
    |    | 10     | DE       | 2070   | pow_combustion_cc_chp_ccs_biomass_1    |                        |                            | 0.8                          | 30                  | 600                   | 0.4              | 0.6              |                  |           |          |          |           |
    ```

    Conversely, existing capacities are explicitly declared as 0 as soon as they are no longer in the system, as 
    opposed to missing rows for 2060 and 2070. <br>
    To avoid data misinterpretation, the techno-economic parameter values for 2060 and 2070 are empty, 
    since the process does not exist anymore in such years.
    <br>
    ```python
    | id | region | year     | type   | capacity_p_inst                        | capacity_p_abs_new_max | conversion_factor_sec_elec | lifetime                     | cost_inv_capacity_p | cb_coefficient        | cv_coefficient   | bandwidth_type   | version          | method    | source   | comment  |           |
    |----|--------|----------|--------|----------------------------------------|------------------------|----------------------------|------------------------------|---------------------|-----------------------|------------------|------------------|------------------|-----------|----------|----------|-----------|
    |    | 21     | DE       | 2021   | pow_combustion_gt_hydrogen_0           | 3500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 22     | DE       | 2024   | pow_combustion_gt_hydrogen_0           | 3500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 23     | DE       | 2027   | pow_combustion_gt_hydrogen_0           | 3500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 24     | DE       | 2030   | pow_combustion_gt_hydrogen_0           | 3300                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 25     | DE       | 2035   | pow_combustion_gt_hydrogen_0           | 3000                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 26     | DE       | 2040   | pow_combustion_gt_hydrogen_0           | 2700                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 27     | DE       | 2045   | pow_combustion_gt_hydrogen_0           | 1500                   |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 28     | DE       | 2050   | pow_combustion_gt_hydrogen_0           | 200                    |                            | 0.6                          | 20                  | 500                   |                  |                  |                  |           |          |          |           |
    |    | 29     | DE       | 2060   | pow_combustion_gt_hydrogen_0           | 0                      |                            |                              |                     |                       |                  |                  |                  |           |          |          |           |
    |    | 30     | DE       | 2070   | pow_combustion_gt_hydrogen_0           | 0                      |                            |                              |                     |                       |                  |                  |                  |           |          |          |           |
    ```
    <br>


## Standard units

Standard units should be harmonized as far as possible to improve transparency and comparability. 
The data adapters also convert the units to ensure compatibility with the frameworks. 
There may also be exceptions to the suggestions below.

| Size                              | Unit            |
|-----------------------------------|-----------------|
| Power                             | MW              |
| Energy                            | GWh / PJ        |
| Costs                             | Euro            |
| Weight (products)                 | Million tonnes  |
| Weight (CO2-equivalent emissions) | tonnes          |
| Transport Service                 | Billion pkm/tkm |
| Percent (range: [0,100])          | -               |
