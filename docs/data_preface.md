# Data preface

The SEDOS Reference Dataset (SRD) entails technology data across five sectors (power, heat, PtX, industry, mobility) 
and various aggregation levels.

This *data preface* provides additional information about the syntax of parameters and units in SRD.

**SEDOS sectors**

| Sector abbreviation | Sector     | SEDOS workpackage |
|---------------------|------------|-------------------|
| pow                 | Power      | AP4               |
| hea                 | Heat       | AP6               |
| x2x                 | Power to X | AP5               |
| ind                 | Industry   | AP7               |
| tra                 | Transport  | AP8               |


??? note "Monetary value"
    
    If not further specified the base year for the monatary value is 2021.

    If monatary conversion were performed, the following logic was applied: <br>
    _currency_A(year_x) -> currency_B(year_x) -> currency_B(year_z)_ <br><br>
    e.g. USD2010 -> EUR2010 -> EUR2021 

??? note "Leap year"

      Note that leap years are considered in time series data by setting the timeindex_stop for 2024, 2040, 2060 to the 30.12.

      ```python
      | id   | region   | type   | timeindex_start       | timeindex_stop        | timeindex_resolution   | exo_pkm_road_mcar   | version   | method   | source   | comment   |
      |------|----------|--------|-----------------------|-----------------------|------------------------|---------------------|-----------|----------|----------|-----------|
      | ---- | -------- | ------ | --------------------- | --------------------- | ---------------------- | ------------------- | --------- | -------- | -------- | --------- |
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

      This is explained below using the example of the transport sector.
      
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
         the `tra_scalars` table
         The normalised timeseries are mapped in the "demand_profile" column via Foreign-key
        
         ```python
         | id | region | year | type                           | demand_annual                 | demand_timeseries_fixed          | bandwidth_type | version | method | source | comment |
         |----|--------|------|--------------------------------|-------------------------------|-----------------------------------|----------------|---------|--------|--------|---------|
         | 1  | DE     | 2021 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 2  | DE     | 2024 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 3  | DE     | 2027 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 4  | DE     | 2030 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 5  | DE     | 2035 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 6  | DE     | 2040 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 7  | DE     | 2045 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 8  | DE     | 2050 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 9  | DE     | 2060 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 10 | DE     | 2070 | helper_sink_exo_tkm_rail       | tra_scalar.exo_tkm_rail       | tra_timeseries.exo_tkm_rail       |                |         |        |        |         |
         | 11 | DE     | 2021 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 12 | DE     | 2024 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 13 | DE     | 2027 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 14 | DE     | 2030 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 15 | DE     | 2035 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 16 | DE     | 2040 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 17 | DE     | 2045 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 18 | DE     | 2050 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 19 | DE     | 2060 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 20 | DE     | 2070 | helper_sink_exo_tkm_rail_short | tra_scalar.exo_tkm_rail_short | tra_timeseries.exo_tkm_rail_short |                |         |        |        |         |
         | 21 | DE     | 2021 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 22 | DE     | 2024 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 23 | DE     | 2027 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 24 | DE     | 2030 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 25 | DE     | 2035 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 26 | DE     | 2040 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 27 | DE     | 2045 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 28 | DE     | 2050 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 29 | DE     | 2060 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 30 | DE     | 2070 | helper_sink_exo_pkm_road_mcar  | tra_scalar.exo_pkm_road_mcar  | tra_timeseries.exo_pkm_road_mcar  |                |         |        |        |         |
         | 31 | DE     | 2021 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 32 | DE     | 2024 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 33 | DE     | 2027 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 34 | DE     | 2030 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 35 | DE     | 2035 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 36 | DE     | 2040 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 37 | DE     | 2045 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 38 | DE     | 2050 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 39 | DE     | 2060 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         | 40 | DE     | 2070 | helper_sink_exo_pkm_road_lcar  | tra_scalar.exo_pkm_road_lcar  | tra_timeseries.exo_pkm_road_lcar  |                |         |        |        |         |
         ```

??? note "Empty cells vs 0 vs omission of data for processes"

      Empty cells: This parameter value does not exist for the process  the parameter for the year is not relevant for 
      the process
      0: This parameter value exists for the process and year  the parameter for the year and the process assumes the value 0 <br>
      
      1. omission of data for processes <br>
      a.	Decision A) applies in order to be as explicit as possible in the data specification. 
      This also applies, for example, to existing technologies where capacity is lost over the years - this can vary greatly per process and would lead to a fragmentation of the data set with regard to the support years if irrelevant years do not appear. 
      In this way, we want to avoid guesswork for us and subsequent users as to whether the process capacity has been forgotten here or whether it has been deliberately included or excluded. 
      e.g. Wind_onshore_0 | Capacity (MW)

      ```python
      | id | region | year | type                                 | capacity_p_inst | capacity_p_abs_new_max | conversion_factor_sec_elec | lifetime | cost_inv_capacity_p | cb_coefficient | cv_coefficient | bandwidth_type | version | method | source | comment |
      |----|--------|------|--------------------------------------|-----------------|------------------------|----------------------------|----------|---------------------|----------------|----------------|----------------|---------|--------|--------|---------|
      | 1  | DE     | 2021 | pow_combustion_cc_chp_ccs_biomassl_1 |                 | 0                      | 0.8                        | 25       | 1000                | 0.4            | 0.6            |                |         |        |        |         |
      | 2  | DE     | 2024 | pow_combustion_cc_chp_ccs_biomassl_1 |                 | 0                      | 0.8                        | 25       | 1000                | 0.4            | 0.6            |                |         |        |        |         |
      | 3  | DE     | 2027 | pow_combustion_cc_chp_ccs_biomassl_1 |                 | 0                      | 0.8                        | 25       | 1000                | 0.4            | 0.6            |                |         |        |        |         |
      | 4  | DE     | 2030 | pow_combustion_cc_chp_ccs_biomassl_1 |                 | 0                      | 0.8                        | 25       | 1000                | 0.4            | 0.6            |                |         |        |        |         |
      | 5  | DE     | 2035 | pow_combustion_cc_chp_ccs_biomassl_1 |                 |                        | 0.8                        | 25       | 1000                | 0.4            | 0.6            |                |         |        |        |         |
      | 6  | DE     | 2040 | pow_combustion_cc_chp_ccs_biomassl_1 |                 |                        | 0.8                        | 25       | 1000                | 0.4            | 0.6            |                |         |        |        |         |
      | 7  | DE     | 2045 | pow_combustion_cc_chp_ccs_biomassl_1 |                 |                        | 0.8                        | 25       | 800                 | 0.4            | 0.6            |                |         |        |        |         |
      | 8  | DE     | 2050 | pow_combustion_cc_chp_ccs_biomassl_1 |                 |                        | 0.8                        | 30       | 800                 | 0.4            | 0.6            |                |         |        |        |         |
      | 9  | DE     | 2060 | pow_combustion_cc_chp_ccs_biomassl_1 |                 |                        | 0.8                        | 30       | 800                 | 0.4            | 0.6            |                |         |        |        |         |
      | 10 | DE     | 2070 | pow_combustion_cc_chp_ccs_biomassl_1 |                 |                        | 0.8                        | 30       | 600                 | 0.4            | 0.6            |                |         |        |        |         |
      | 11 | DE     | 2021 | pow_geothermal_st_1                  |                 | 0                      | 0.4                        | 25       | 1000                |                |                |                |         |        |        |         |
      | 12 | DE     | 2024 | pow_geothermal_st_1                  |                 | 0                      | 0.4                        | 25       | 1000                |                |                |                |         |        |        |         |
      | 13 | DE     | 2027 | pow_geothermal_st_1                  |                 | 0                      | 0.4                        | 25       | 1000                |                |                |                |         |        |        |         |
      | 14 | DE     | 2030 | pow_geothermal_st_1                  |                 | 0                      | 0.4                        | 25       | 1000                |                |                |                |         |        |        |         |
      | 15 | DE     | 2035 | pow_geothermal_st_1                  |                 | 0                      | 0.4                        | 25       | 1000                |                |                |                |         |        |        |         |
      | 16 | DE     | 2040 | pow_geothermal_st_1                  |                 | 0                      | 0.4                        | 25       | 1000                |                |                |                |         |        |        |         |
      | 17 | DE     | 2045 | pow_geothermal_st_1                  |                 |                        | 0.4                        | 25       | 800                 |                |                |                |         |        |        |         |
      | 18 | DE     | 2050 | pow_geothermal_st_1                  |                 |                        | 0.4                        | 30       | 800                 |                |                |                |         |        |        |         |
      | 19 | DE     | 2060 | pow_geothermal_st_1                  |                 |                        | 0.4                        | 30       | 800                 |                |                |                |         |        |        |         |
      | 20 | DE     | 2070 | pow_geothermal_st_1                  |                 |                        | 0.4                        | 30       | 600                 |                |                |                |         |        |        |         |
      | 21 | DE     | 2021 | pow_combustion_gt_hydrogen_0         | 3500            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 22 | DE     | 2024 | pow_combustion_gt_hydrogen_0         | 3500            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 23 | DE     | 2027 | pow_combustion_gt_hydrogen_0         | 3500            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 24 | DE     | 2030 | pow_combustion_gt_hydrogen_0         | 3300            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 25 | DE     | 2035 | pow_combustion_gt_hydrogen_0         | 3000            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 26 | DE     | 2040 | pow_combustion_gt_hydrogen_0         | 2700            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 27 | DE     | 2045 | pow_combustion_gt_hydrogen_0         | 1500            |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 28 | DE     | 2050 | pow_combustion_gt_hydrogen_0         | 200             |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 29 | DE     | 2060 | pow_combustion_gt_hydrogen_0         | 0               |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      | 30 | DE     | 2070 | pow_combustion_gt_hydrogen_0         | 0               |                        | 0.6                        | 20       | 500                 |                |                |                |         |        |        |         |
      ```

      

## Units

| Symbol | Name     | Range   | Description                                       |
|-----|----------|---------|---------------------------------------------------|
| `%` | `Percent` | [0,100] | A number or ratio expressed as a fraction of 100. |

