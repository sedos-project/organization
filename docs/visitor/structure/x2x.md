# X2X sector

## Naming convention
The X2X sector in the SEDOS dataset contains technologies that are traditionally refered to as Power-to-X processes, which are intermediate conversion processes between the supply side (e.g., electricity supply) and the demand side, e.g., transport sector. Due to this intermediate role within the model structure, besides PtX means of providing fuels and other commodities to the sectors that satisfy end demands, also conventional ways of fuel provision and means to provide certain commodities requested by other sectors are allocated to the X2X sector. This entails e.g., refineries, biofuels and commodity imports. The nomenclature of the processes is based on the conversion type of the process. For example, processes that convert power into a gaseous product, so called Power-to-Gas processes are identified with the abbreviation *p2gas*. If another commodity than power is used as an input to provide a gaseous product, this turns into *x2gas* indicating the variable product input. Additionally, import processes (*import*) and fuel delivery processes (*delivery*) are separated from the rest of the naming logic. The categorization by conversion type is followed by an abbreviation of the process name. The end of the process name is defined by either 0 or 1 for existing (stock) processes or new (expansion) processes if that applies for the process (e.g., 0/1 differentiation would not make sense for import processes). Table 1 shows the different categories present within the X2X sector:

*Table 1: Nomenclature for the X2X sector process naming.*

| Sector | Mode      | Process Name  | Stock/Expansion |
|--------|-----------|---------------|-----------------|
| x2x    | p2gas     | ...           | 0               | 
|        | x2gas     | ...           | 1               |
|        | g2p       | ...           |                 |
|        | x2liquid  | ...           |                 |
|        | other     | ...           |                 |
|        | import    | ...           |                 |
|        | delivery  | ...           |                 |
|        | storage   | ...           |                 |


## Provided parameters

Conversly to other sectors in the SEDOS model structure, the X2X sector has no sector-specific scalar parameters but only generally defined parameters. Please refer to the corresponding section in the documentation for more information. All costs are presented excluding taxes and subsidies, based on 2021 price levels. The X2X sector has only scalar data and no time series data as it serves as an intermediate sector connecting supply and demand (which themselves have time series data)


## General modeling approach

When modeling X2X processes, for most processes a simplified approach is used where the conversion ratios between input and output of a process are fixed. As the X2X sector contains very different technologies, this does not apply for all processes. Therefore, a subset of processes where the modeling approach needs more explanation are described in the following.

### Refineries and Fischer-Tropsch process

Refineries and the Fischer-Tropsch process are used to generate a variety of fuels within the system. The product distribution in real plants can vary significantly based on the process setup which is driven by the requested demand. Therefore, fixed product shares would not depict reality very well and would not model the flexibility of these plants accurately. Therefore, refineries and FT plants are modeled as multi-input multi-output components (refer to chapter Model Base for more information about this process type) with defined maximum and minimum flow shares for every possible output commodity. 

### Steam Reformer

Steam reformers can be used in the system to generate hydrogen from natural gas. However, to give the model the possibility to use the syngas as well prior to hydrogen cleanup for processes that require syngas (e.g., Fischer-Tropsch synthesis or methanol synthesis) the process had to be modeled differently. It was split into two processes (*x2x_x2gas_sr_syngas* and *x2x_x2gas_sr_syngas_psa*). The first process (*x2x_x2gas_sr_syngas*) converts natural gas into syngas. This syngas can either be used in the steam reformer to be further converted into hydrogen or it can be transfered via a helper component to the rest of the energy system as syngas. However, the second part of the process (*x2x_x2gas_sr_syngas_psa*) is restricted to only use syngas from the steam reformer and not other sources of syngas, as it should only model the decision of the system to use steam reformers for syngas or hydrogen generation and not to serve as an artifical process to convert syngas to hydrogen.

### Fuel Delivery Markup

As SEDOS is a single-node model, modeling of infrastructure such as fuel delivery needs to be made with certain assumptions and proxys. For fuel deliveries of products which are part of the X2X sector, dedicated *delivery* processes have been introduced which in general add a markup to the cost of the commodity if it needs to be transported. The markup is calculated based on assumptions of average distance from production facility to consumer.

### Hydrogen Pipelines

Although most fuels just have a simple markup in SEDOS for their delivery, the situation is different for hydrogen pipelines. There, to take into account that a hydrogen pipeline network first has to be built, hydrogen pipelines are modeled similar to other technologies with investment costs allowing the system to decide on the expansion of the pipeline network. Hydrogen pipelines can either be newly built or retrofitted methane pipelines. The retrofit of methane pipelines is exogenously set based on the total retrofit potential and previous model results and comes at a lower cost compared to newly built pipelines. To account for the variable costs of compression, a conversion factor for electricity demand is introduced.

### Biofuel sourcing

The introduction of biofuels into the system is not modeled on process-detail level. Instead, biofuels are assumed to be produced at a certain price per MWh of fuel, which has been derived from literature values. However, nonetheless they cannot be produced indefinitely. Instead, based on existing biomass potentials for the relevant biomasses to the biofuels, capacity limits have been defined which limit the usage of these biofuels.

### Negative Emission Technologies

An important feature of the X2X sector is that certain technologies can either capture CO2, can generate CO2-neutral fuels or can utilize CO2 in the process. Emissions accounting in SEDOS has been discussed at another point and will not be discussed in detail again here. For imports of synthetic fuels and biofuel sourcing in Germany, negative emissions have to be introduced to balance the fuel-related emissions that are added in the end. This has to be differentiated from CO2 usage, where CO2 can be converted to other products through certain PtX processes. This differentiation is made through different CO2 commodities, where the "usable" CO2 can e.g., be provided by direct air capture.
