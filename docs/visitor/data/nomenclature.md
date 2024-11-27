# Nomenclature

## Process Nomenclature

As the process and therefore the specifications of the processes are very detailed, a consistent nomenclature has been
defined within the SEDOS project. e.g. the process "pow_combustion_cc_chp_methane_1" consists of elements of all the 
defined columns in the following table. This table helps to understand the meaning of the process names.

<style>
table {
    width: 50%;
    border-collapse: collapse;
}

th, td {
    border: 1px solid #dddddd;
    text-align: left;
    padding: 8px;
}

th {
    background-color: #f2f2f2;
}
</style>

| sector   | category         | specifications                                                                                                                | input-specifications                                                 | existing/new   | detail (aggregated)   |
|:---------|:-----------------|:------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------|:---------------|:----------------------|
| pow      | combustion       | [gt, st, cc, ic], chp, ccs                                                                                                    | [coal, biomass, waste, methane, biomass, hydrogen]                   | [0, 1]         | _ag                   |
|          | geothermal       | [orc, st], chp                                                                                                                |                                                                      |                |                       |
|          | hydro            | [ror, pond]                                                                                                                   |                                                                      |                |                       |
|          | nuclear          | [fis, fus]                                                                                                                    |                                                                      |                |                       |
|          | photovoltaic     | [field, hh, cts, ind], [gm, fl], [msi, psi, asi ,cpv], [roof, faca, balc]                                                     |                                                                      |                |                       |
|          | wind_turbine     | [on, off, near], [fl, fb], [ha, va]                                                                                           |                                                                      |                |                       |
|          | storage          | [batt, hydr], [util, hh, cts, ind]                                                                                            |                                                                      |                |                       |
|          | eem              |                                                                                                                               |                                                                      |                |                       |
| hea      | combustion       | [gt, st, cc, ic, orc]                                                                                                         |                                                                      | [0, 1]         |                       |
|          | heat_exchanger   |                                                                                                                               |                                                                      | [0, 1]         |                       |
|          | heater           | [soco, hp, stov, boil], [et, cd], [mono, dual], [air, gro]                                                                    | [hydrogen, gas, oil, biomass, wood]                                  | [0, 1]         |                       |
|          | refrigerator     | [comp, abs, ads]                                                                                                              |                                                                      | [0, 1]         |                       |
|          | storage          |                                                                                                                               |                                                                      | [0, 1]         |                       |
|          | cooling          | [proc, space, combined]                                                                                                       |                                                                      | [0, 1]         |                       |
|          | water_heating    |                                                                                                                               |                                                                      | [0, 1]         |                       |
|          | district_heating |                                                                                                                               | [heat_high,heat_low]                                                 | [0, 1]         |                       |
| x2x      | p2gas            | aec, pemec, soec, sabm, biom                                                                                                  |                                                                      | [1]            |                       |
|          | g2p              | pemfc, sofc                                                                                                                   | ls                                                                   | [1]            |                       |
|          | x2gas            | sr,mpyr,coel,rwgs                                                                                                             | [syngas,syngas_psa]                                                  | [0,1]          |                       |
|          | x2liquid         | source,oref,ft                                                                                                                | [biodiesel,bioethanol,biokerosene]                                   | [0,1]          |                       |
|          | storage          | hydrogen,methane                                                                                                              | [lohc,new,retrofit]                                                  | [1]            |                       |
|          | other            | dac,biogas_treatment, cng_compression, lng_liquefication                                                                      | [ht,lt]                                                              | [1]            |                       |
|          | import           | ammonia, biogas, coal, crudeoil, h2_renewable, lng, methanol, natgas, sng, syndiesel, syngasoline, synkerosene                |                                                                      |                |                       |
|          | transport        | hydrogen, methane, diesel, gasoline, kerosene, naphtha, methanol, ethanol, hfo, lpg, lng, ammonia                             | [pipeline_retrofit,pipeline_new],[pipeline]                          |                |                       |
| ind      | automobile       | [pc, hcv, lcv] [icev, phev, bev, fcev], prtp, bdys, pnts, hvlt, mcmp, fasmbl                                                  |                                                                      |                |                       |
|          | cement           | [rk, rawmats, novel, finish, novelfinish], ccs                                                                                |                                                                      | [0, 1]         |                       |
|          | glass            | [flat, cont, spec, fibe], [batchplant, oxyf, oxyh, fulle, rege, recu, forming]                                                |                                                                      | [0, 1]         |                       |
|          | paper            | [hchem, lchem, lmech]                                                                                                         | [pulp, finish]                                                       | [0, 1]         |                       |
|          | steel            | [blafu, elefu, dirred, hyddri, oxyfu, pellet, sinter, sponge, casting]                                                        | ccs                                                                  | [0, 1]         |                       |
|          | aluminium        | [pri, sec, aluminabayer]                                                                                                      |                                                                      | [0, 1]         |                       |
|          | copper           | [pri, sec]                                                                                                                    |                                                                      | [0, 1]         |                       |
|          | chemical         | [NH3, methanol, Cl2, olefins, btx], hb, [msyn, mhydr], [memb, diaph], [scrac, ecrac, mto, mta], [smr, aec, pemec, biog, mpyr] |                                                                      |                |                       |
|          | source           |                                                                                                                               |                                                                      |                |                       |
| tra      | road             | [lcar, mcar, hcar, bus, motorc, ltruck, htruck, vehispec], [ice, fcev, bev, oev, hyb], [pass, frei], [long, short]            | [diesel, gasoline, methanol, ethanol, lng, cng, lpg, hydrogen, flex] |                |                       |
|          | rail             | [ice, fcev, bev, oev, hyb], [pass, frei], [long, short]                                                                       | [coal, diesel, ethanol]                                              |                |                       |
|          | air              | [ice, fcev, bev, hyb], [pass, frei], [natio, europ, inter],                                                                   | [kerosene, hydrogen]                                                 |                |                       |
|          | water            | [ice, fcev], frei, [up, down]                                                                                                 | [lng, methanol, ethanol, ammonia, diesel, hydrogen]                  |                |                       |


## Commodity Nomenclature

The SEDOS commodities are categorized as follows:

- ??? info "primary energy carriers (pri) "
    
        solar_radiation, wind_energy, hydro_energy, hydro_nat_inflow_seasonal,
        hydro_nat_inflow_openloop, geoth_heat, envir_heat, biomass_stemwood,
        biomass_pellets_pp, biomass_wood_chips_pp, biomass_wood_chips_pr,
        biomass_straw_bales_pr, biomass_wood_chips_sr, biomass_pellets_sr,
        waste_other_bio_sr, waste_municipal_bio, waste_wood, waste_animal,
        sewage_gas, sewage_sludge, waste_non_bio, landfill_gas, cbm,
        natural_gas, lignite, coal, crude_oil, uran, deuterium

- ??? info "secondary energy carriers (sec)"

        elec, elec_ind, elec_wallbox, elec_battery, biogas, natural_gas_syn,
        lng, cng, lpg, methane, hydrogen, syngas, syngas_sr,
        heating_oil, heavy_fuel_oil, diesel, diesel_fos, diesel_syn,
        biodiesel, gasoline, gasoline_fos, gasoline_syn, ammonia, naphtha,
        naphtha_syn, naphtha_fos, kerosene, kerosene_fos, kerosene_syn,
        refinery_gas, biokerosene, ethanol, methanol, biomethanol,
        heat_low, heat_high, heat_district_low_hh, heat_district_high_hh,
        heat_district_low_cts, heat_district_high_cts, heat_district_high_ind,
        saving, waste_heat_high_chemi, waste_heat_high_aluminum,
        waste_heat_high_cement, waste_heat_high_copper, waste_heat_high_glass,
        waste_heat_high_paper, waste_heat_high_steel

- ??? info "industrial intermediate products (iip)"

        aluminum_alumina, aluminum_crude, aluminum_scrap, auto_btry_hcv_bev,
        auto_btry_hcv_fcev, auto_btry_hcv_icev, auto_btry_lcv_bev, auto_btry_lcv_fcev,
        auto_btry_lcv_icev, auto_btry_pc_bev, auto_btry_pc_fcev, auto_btry_pc_icev,
        auto_btry_pc_phev, auto_heat_proc, auto_hvlt, auto_mcmp, auto_painted_hcv_bev,
        auto_painted_hcv_fcev, auto_painted_hcv_icev, auto_painted_lcv_bev, auto_painted_lcv_fcev,
        auto_painted_lcv_icev, auto_painted_pc_bev, auto_painted_pc_fcev, auto_painted_pc_icev,
        auto_painted_pc_phev, auto_parts_hcv_bev, auto_parts_hcv_fcev, auto_parts_hcv_icev,
        auto_parts_lcv_bev, auto_parts_lcv_fcev, auto_parts_lcv_icev, auto_parts_pc_bev,
        auto_parts_pc_fcev, auto_parts_pc_icev, auto_parts_pc_phev, auto_space_heat,
        auto_hot_water, biogas_ind, black_liquor, steel_blafu_gas, steel_blafu_gas_in,
        cement_clinker, cement_rawmeal, chemi_biomass, chemi_biomethanol,
        chemi_electro_chem, chemi_heavy_fuel_oil, chemi_machine_drive,
        chemi_meoh_f_h2, chemi_meoh_h2, chemi_methane, chemi_methanol,
        chemi_naphtha, chemi_nh3_h2, chemi_mtg_mtk_h2, chemi_lpg,
        chemi_processes_others, chemi_process_heat, chemi_steam, coke,
        steel_coke_oven_gas, steel_coke_oven_gas_in, copper_crude, copper_scrap,
        elec, glass_cont_batch, glass_cont_melt, glass_flat_batch, glass_flat_form,
        glass_flat_melt, heat_proc, hot_water, paper_pulp, paper_recycle,
        steam, steel_blafu_slag, steel_crudesteel, steel_iron_pellets, steel_raw_iron,
        steel_scrap, steel_sinter, steel_sponge_iron, heat_high, heat_high_other,
        cooling, heat_kiln, ict, lighting, machine_drive,
        pump_fans_compression

- ??? info "exogenous demand (exo)"

          air_pkm, air_natio_pkm, air_europ_pkm, air_inter_pkm,
          rail_pkm, rail_short_pkm, rail_long_pkm, rail_tkm,
          rail_short_tkm, rail_long_tkm, rail_steam_pkm, water_tkm,
          road_car_pkm, road_lcar_pkm, road_mcar_pkm, road_hcar_pkm,
          road_motorc_pkm, road_truck_tkm, road_ltruck_tkm, road_mtruck_tkm,
          road_htruck_tkm, road_bus_pkm, road_bus_short_pkm, road_bus_long_pkm,
          road_agri_diesel, road_const_diesel, hh_space_heat, hh_hot_water,
          hh_space_cooling, hh_re1_space_heat, hh_re1_hot_water, hh_re1_space_cooling,
          hh_re2_space_heat, hh_re2_hot_water, hh_re2_space_cooling, hh_re3_space_heat,
          hh_re3_hot_water, hh_re3_space_cooling, hh_rn1_space_heat, hh_rn1_hot_water,
          hh_rn1_space_cooling, hh_ue1_space_heat, hh_ue1_hot_water, hh_ue1_space_cooling,
          hh_ue2_space_heat, hh_ue2_hot_water, hh_ue2_space_cooling, hh_ue3_space_heat,
          hh_ue3_hot_water, hh_ue3_space_cooling, hh_un1_space_heat, hh_un1_hot_water,
          hh_un1_space_cooling, hh_me1_space_heat, hh_me1_hot_water, hh_me1_space_cooling,
          hh_me2_space_heat, hh_me2_hot_water, hh_me2_space_cooling, hh_me3_space_heat,
          hh_me3_hot_water, hh_me3_space_cooling, hh_mn1_space_heat, hh_mn1_hot_water,
          hh_mn1_space_cooling, cts_space_heat, cts_hot_water, cts_space_cooling,
          cts_proc_cooling, cts_t1e_space_heat, cts_t1e_hot_water, cts_t1e_space_cooling,
          cts_t1n_space_heat, cts_t1n_hot_water, cts_t1n_space_cooling, cts_t2e_space_heat,
          cts_t2e_hot_water, cts_t2e_space_cooling, cts_t2n_space_heat, cts_t2n_hot_water,
          cts_t2n_space_cooling, aluminum, cement, copper, glass_cont,
          glass_fibe, glass_flat, glass_spec, paper_hq, paper_lq, steel,
          auto_pc_icev, auto_pc_phev, auto_pc_bev, auto_pc_fcev, auto_lcv_icev,
          auto_lcv_bev, auto_lcv_fcev, auto_hcv_icev, auto_hcv_bev, auto_hcv_fcev,
          chemi_olefins, chemi_btx, chemi_nh3, chemi_cl2, chemi_methanol,
          chemi_others, other_ind, agri_livestock

- ??? info "emissions (emi)"

        co2_f_pow, co2_f_hea, co2_f_x2x, co2_f_tra, co2_f_ind, co2_p_ind, co2_p_x2x,
        ch4_f_pow, ch4_f_hea, ch4_f_x2x, ch4_p_x2x, ch4_f_tra, ch4_f_ind, ch4_p_ind,
        n2o_f_ind, n2o_f_pow, n2o_f_hea, n2o_f_tra, n2o_f_x2x, n2o_p_x2x,
        co2_neg_air_dacc, co2_neg_fuel_cc_pow, co2_neg_fuel_cc_ind, co2_neg_fuel_cc_x2x,
        co2_neg_proc_cc_ind, co2_neg_air_bio, co2_neg_imp, co2_reusable, co2_stored
        

The abbreviation of these categories are added as prefix to all commodities to identify them easily.
The exogenous demand in the model is defined in such a way that the model has maximum degrees of freedom to choose 
between the technologies to meet the demand. The final energy in the system is thus determined endogenously in the model.
In the model structure additionally the "_orig" suffix can be found. This has been used to describe delivery 
processes e.g. for pipelines in a one node model approach. For example "sec_methane_orig" is converted to "sec_methane" 
in the "x2x_delivery_methane_pipeline_0" process which is modelled with a simplified efficiency and costs.
These are not listed above.

The structure of the emission commodities is elaborated in [Emission Concept](./visitor/structure/emissions.md)


## Parameter Nomenclature

Moreover, the nomenclature of the parameters that are being used in the SEDOS data is introduced together with the
description of the applied parameters and their units.

<style>
table {
    width: 100%;
    border-collapse: collapse;
}

th, td {
    border: 1px solid #dddddd;
    text-align: left;
    padding: 8px;
}

th {
    background-color: #f2f2f2;
}
</style>

| category         | parameter name                           | description                                                                                                                                                                                                             |
|:-----------------|:-----------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| oedatamodel_cols | id                                       | A primary key is a field or set of fields that uniquely identifies each row in the table. It's recorded as a list of strings, since it is possible to define the primary key as made up of several columns.             |
|                  | region                                   | It describes the geographical scope of the dataset.                                                                                                                                                                     |
|                  | year                                     | It describes the time frame of the dataset.                                                                                                                                                                             |
|                  | type                                     | Is used distinguish different process types in a dataset.                                                                                                                                                               |
|                  | bandwidth_type                           | It describes the bandwidths type of the values in the parameter columns.                                                                                                                                                |
|                  | version                                  | It describes the version of the values in the parameter columns.                                                                                                                                                        |
|                  | method                                   | It describes the procedure for obtaining the value, in case it does not originate from a single source.                                                                                                                 |
|                  | source                                   | Human readable title of the source, e.g. document title or organisation name. The source must relate to a source provided in the oemetadata (datapackage) file.                                                         |
|                  | comment                                  | Free text comment on what's been done.                                                                                                                                                                                  |
|                  | timeindex_start                          | Both date and time, with time zone.                                                                                                                                                                                     |
|                  | timeindex_stop                           | Both date and time, with time zone.                                                                                                                                                                                     |
|                  | timeindex_resolution                     | The time span between individual points of information in a time series.                                                                                                                                                |
| general          | co2_limit                                | CO2 net emission budget for a period.                                                                                                                                                                                   |
|                  | lifetime                                 | Technical lifetime of a process.                                                                                                                                                                                        |
|                  | commodity_price                          | Cost/Revenue for purchasing/selling one unit (MWh) of a stock or buy commodity.                                                                                                                                         |
|                  | potential_annual_max                     | Maximum annual energy use of a commodity.                                                                                                                                                                               |
|                  | demand_timeseries                        | normalized demand timeseries which gets multiplied with demand_annual                                                                                                                                                   |
|                  | demand_annual                            | Projected annual demand for a commodity.                                                                                                                                                                                |
|                  | shared_potential_id                      | Specifies a name for a potential group in which all components share the same potential (e.g. wind turibine)                                                                                                            |
| capacities       | capacity_p_inst_0                        | Existing throughput power output capacity per process in a certain year.                                                                                                                                                |
|                  | capacity_p_min                           | Minimum installable required throughput power output capacity per process.                                                                                                                                              |
|                  | capacity_p_max                           | Maximum installable required throughput power output capacity per process.                                                                                                                                              |
|                  | capacity_e_inst_0                        | Existing storage energy capacity.                                                                                                                                                                                       |
|                  | capacity_e_min                           | Minimum required storage energy capacity.                                                                                                                                                                               |
|                  | capacity_e_max                           | Maximum allowed storage energy capacity.                                                                                                                                                                                |
|                  | capacity_w_inst_0                        | Existing weight capacity of a process.                                                                                                                                                                                  |
|                  | capacity_w_min                           | Maximum weight capacity of a process.                                                                                                                                                                                   |
|                  | capacity_w_max                           | Minimum weight capacity of a process.                                                                                                                                                                                   |
|                  | capacity_tra_inst_0                      | Number of vehicles.                                                                                                                                                                                                     |
|                  | capacity_p_abs_new_max                   | Absolute upper bound on level of investment in new power output capacity for a period.                                                                                                                                  |
|                  | capacity_e_abs_new_max                   | Absolute upper bound on level of investment in new storage energy capacity for a period.                                                                                                                                |
|                  | capacity_w_abs_new_max                   | Absolute upper bound on level of investment in new weight capacity for a period.                                                                                                                                        |
|                  | availability_constant                    | Constant output ratio in relation to installed capacity. (= h/a)                                                                                                                                                        |
|                  | availability_timeseries_fixed            | Time series of fixed capacity factor in relation to installed capacity.                                                                                                                                                 |
|                  | availability_timeseries_max              | Time series of maximum capacity factor in relation to installed capacity.                                                                                                                                               |
| costs            | wacc                                     | Percentage of costs for capital after taxes. Used to calculate annuity factor for investment costs.                                                                                                                     |
|                  | cost_inv_p                               | Investment costs for new throughput power output capacity.                                                                                                                                                              |
|                  | cost_inv_e                               | Investment costs for new storage energy capacity.                                                                                                                                                                       |
|                  | cost_inv_w                               | Investment costs for new capacity per unit weight.                                                                                                                                                                      |
|                  | cost_inv_tra                             | Investment costs for new vehicle unit.                                                                                                                                                                                  |
|                  | cost_fix_p                               | Operation independent costs for existing and new throughput power output capacity.                                                                                                                                      |
|                  | cost_fix_e                               | Operation independent costs for existing and new storage energy capacity.                                                                                                                                               |
|                  | cost_fix_w                               | Operation independent costs for capacity per unit weight.                                                                                                                                                               |
|                  | cost_fix_tra                             | Operation independent costs for existing and new vehicle units.                                                                                                                                                         |
|                  | cost_var_e                               | Variable costs per throughput energy unit output. (excluding fuel costs).                                                                                                                                               |
|                  | cost_var_tra                             |                                                                                                                                                                                                                         |
|                  | cost_var_w                               | Variable costs per throughput weight unit output. (excluding fuel costs).                                                                                                                                               |
| process          | conversion_factor_<commodity>            | Commodity-specific conversion factor (multiplication of input and output factors yields the efficiency of the process).                                                                                                 |
|                  | flow_share_min_<commodity>               | Minimum share of flow commodity c based upon the sum of individual flows defined by the commodity group cg belonging to process p.                                                                                      |
|                  | flow_share_max_<commodity>               | Maximum share of flow commodity c based upon the sum of individual flows defined by the commodity group cg belonging to process p.                                                                                      |
|                  | flow_share_fix_<commodity>               | Fixed share of flow commodity c based upon the sum of individual flows defined by the commodity group cg belonging to process p.                                                                                        |
|                  | conversion_factor_timeseries_<commodity> | Time-variable commodity-specific conversion factor.                                                                                                                                                                     |
|                  | ef_<commodity>_<emission>                | Commodity-specific emission factor.                                                                                                                                                                                     |
|                  | cb_coefficient                           | The Cb-coefficient (backpressure coefficient) is defined as the maximum power generation capacity in backpressure mode divided by the maximum heat production capacity (including flue gas condensation if applicable). |
|                  | cv_coefficient                           | The Cv-value for an extraction steam turbine is defined as the loss of electricity production, when the heat production is increased one unit at constant fuel input.                                                   |
|                  | efficiency_sto_in                        | Energy efficiency of power input.                                                                                                                                                                                       |
|                  | efficiency_sto_out                       | Energy efficiency of power output.                                                                                                                                                                                      |
|                  | sto_init                                 | The initial state of charge of a storage.                                                                                                                                                                               |
|                  | sto_self_discharge                       | Storage losses over time.                                                                                                                                                                                               |
|                  | sto_ep_ratio_binding                     | Fixed ratio of the storage energy capacity to its power output capacity.                                                                                                                                                |
|                  | sto_ep_ratio_optional                    | Optional fixed ratio of the storage energy capacity to its power output capacity.                                                                                                                                       |
|                  | sto_cycles_max                           | Defines the maximum number of full storage cycle equivalents over the lifetime.                                                                                                                                         |
| tra-extra        | capacity_tra_connection_max              | Maximum connection capacity of an average electric vehicle, taken the connection availability into acocunt.                                                                                                             |
|                  | capacity_tra_connection_timeseries       | Connection capacity of an average electric vehicle.                                                                                                                                                                     |
|                  | mileage                                  | Yearly mileage of a vehicle.                                                                                                                                                                                            |
|                  | market_share_range                       | Range of market share.                                                                                                                                                                                                  |
|                  | occupancy_rate                           | Occupancy rate of a vehicle.                                                                                                                                                                                            |
|                  | tonnage                                  | Tonnes transported per vehicle.                                                                                                                                                                                         |
|                  | share_tra_charge_mode                    | Proportion of fleet that load with a soecific charge mode..                                                                                                                                                             |
|                  | sto_min_timeseries                       | Time series of min battery state of charge.                                                                                                                                                                             |
|                  | sto_max_timeseries                       | Time series of max battery state of charge.                                                                                                                                                                             |
|                  | optional_limitations                     | User constraint to describe market limitations                                                                                                                                                                          |
