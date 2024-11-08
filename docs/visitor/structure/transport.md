# Transport sector

## Naming convention
The transportation sector in the SEDOS dataset is divided into road, water, air and rail modes. The road-based vehicles include light (*l*), medium (*m*) and heavy (*h*) cars and trucks as well as coaches (*long* distance) and buses (*short* distance), motorcycles and special vehicles in the agricultural (*agri*) and construction (*const*) industries. For waterway transport, the focus is on inland freight shipping. In the field of aviation, a distinction is made between domestic flights (*natio*), European flights (*europ*) and intercontinental (*inter*) flights and passenger transportation alone is accounted for. Finally, a distinction is made between short-haul (streetcars, shunting operations) and long-haul (long-distance trains) for both passenger (*pass*) and freight (*frei*) rail transport. A suitable selection of drive technologies (internal combustion engine vehicle – icev, hybrids – hyb, fuel cell electric vehicle – fcev, battery electric multiple unit meaning a combination of batteries and overhead cables – bemu, battery electric vehicles – bev and overhead electric vehicles – oev) and fuels is combined for all vehicle types and organized as separate processes in the model structure. The nomenclature for process naming follows the system below, that is further explained in Table 1:
tra_rail_hyb_pass_short_hydrogen_0.

*Table 1: Nomenclature for the transport sector process naming.*

| Sector | Mode   | Type (including information on weight) | Drive Technology | Transported Unit | Specification | Fuel      | Stock/Expansion |
|--------|--------|----------------------------------------|------------------|------------------|---------------|-----------|-----------------|
| tra    | road   | car/lcar/mcar/hcar                    | icev             | pass             | long          | ammonia   | 0               |
|        | water  | truck/ltruck/mtruck/htruck            | hyb              | frei             | short         | gasoline  | 1               |
|        | air    | bus                                   | fcev             |                  | natio         | diesel    |                 |
|        | rail   | motorc                                | bemu             |                  | europe        | hydrogen  |                 |
|        |        | agri                                  | bev              |                  | inter         | methanol  |                 |
|        |        | const                                 | oev              |                  | wallbox       | ethanol   |                 |
|        |        |                                       | engine           |                  | cng           |           |                 |
|        |        |                                       | battery          |                  | lpg           |           |                 |
|        |        |                                       | inflex           |                  | lng           |           |                 |
|        |        |                                       | flex             |                  | elec          |           |                 |
|        |        |                                       | g2v              |                  | kerosene      |           |                 |
|        |        |                                       | v2g              |                  | coal          |           |                 |
|        |        |                                       |                  |            


## General modeling approach

When modeling all vehicles apart from battery electric cars and trucks, a simplified and inflexible approach is used. This means that these vehicles have a fixed, exogenously specified driving profile and the fuel tank is not taken into account as a possible buffer between fuel energy demand and the provision of driving power. This is based on the assumption that, in contrast to BEVs, the refueling process is evened out across the fleet and takes place during the driving process rather than being decoupled during parking times. In addition, the fuel supply chain is seen as having a high storage capacity that is not available in the electricity grid in the same form, which is why a detailed consideration of batteries and the charging process is considered for BEVs (trucks and cars). 

In the case of inflexible vehicles, only the composition of the fleet is optimized, i.e. the choice of drive technology and fuel type for medium sized cars. The modal split, i.e. the distribution of demand between vehicle types (hcars, mcars, lcars, buses, trains, etc.), is specified in exogenous demand variables, e.g. exo_road_car_pkm.
The general modeling follows the scheme below: 

![Figure 1: Modeling schema for vehicles without explicitly modelled storage/tank.](../../graphics/nomenclature_transport.png)

The input energy is transformed into the output commodities via indicators. Accordingly, the ratio of input to output flows is specified, taking into account the occupancy rate for passenger transport and the tonnage for freight transport in the information on transport services. For example: 

            1 kWh        \u2192     10 vehicle_km * 3 p/vehicle + 0.005 t 
            sec_diesel   \u2192         exo_road_car_pkm        + emi_co2_f_tra
is transformed to
            1 kWh        \u2192       30 pkm                 +    0.005 t     
            sec_diesel   \u2192      exo_road_car_pkm        + emi_co2_f_tra
This means that the direct efficiencies are not given as a percentage but rather by indicator ratios.

## Battery electric vehicle (BEV) modeling approach

The detailed modeling of the BEVs provides for a separation of the fleet into three parts representing the charging modes: user-controlled charging (no optimization possible), system-controlled charging and system-controlled charging with the option of feeding back into the grid (see dark blue boxes in Figure 2). Their ratio is given exogenously. In the data the electric vehicle process (and with it each of the charging modes) is furthermore divided into 4 sub-processes: wallbox, battery, engine and an auxiliary helper process that contains overarching parameters, such as occupancy rate or tonnage. 

This results in a differentiation of 11 processes for each electric vehicle type: 3 modes times 3 sub-processes plus a further wallbox process, which represents the feed-in of electricity back into the grid, and an additional superordinate auxiliary process. Since the modeled wallbox, for example, does not differ in any of the cases, there is a certain redundancy of information, but this is necessary because the boundary conditions differ in the modeling and therefore these sub-processes can this way described accurately.
The resulting indicator ratios are as follows and can also be found in Figure 2:

1.	**Wallbox efficiency** (sec_elec * ɳwallbox_G2V = sec_elec_wallbox):
        sec_elec \u2192 sec_elec_wallbox   
2.	**Charging/Discharging effiency** (sec_wallbox* ɳbattery_in* ɳbattery_out = sec_battery):
        sec_wallbox \u2192 sec_battery
2.1 **Grid Feed-in** (sec_battery * ɳwallbox_V2G * ɳbattery_in* ɳbattery_out = sec_elec):
        sec_battery \u2192 sec_elec
3.	**Engine efficiency** (sec_battery * ɳengine*occupancy_rate = exo_road_car_pkm):
        sec_battery \u2192 exo_road_car_pkm


  




