# Model Base

The specifications, a result of thorough discussions and definitions in the 3rd working package of the SEDOS project, provide a clear and accessible series of assumptions and requirements. This clarity sets the basic framework for the modeling in the project. The transparency also ensures that the model can be solved with different model generators.

## Alignment

The SEDOS focus is on understanding...

- The overall system,
- The technical foundation in the sectors,
- The possible relations and interactions due to sector coupling.

The model structure is used in three frameworks oemof, FINE and TIMES.

## Key Facts

- Deterministic model formulation with Linear Programming Optimization
- Intertemporal Time-Span modeling with perfect foresight.
- Central planner solving perspective for macro-economic optimization. Business/regulatory aspects are neglected as far as possible, 
- Brownfield approach: Differentiation between existing technology stock (0X) vs new technology expansion (1X)
  if necessary, taxes are deducted from the prices and a global WACC of 2% has been defined for all technologies.
- Long-Term time horizon until 2070
- To enable the internal and external calculability of SEDOS-based models, additional aggregation levels are introduced 
  due to the high level of detail in the sectors. This allows the user to focus their model on individual sectors while 
  other sectors are modeled simplified.
- Hourly time resolution with time series aggregation using the tsam tool [TODO: Link]
- A distinction is made between three energy categories: primary energy, secondary energy, and model exogenous energy demand. 
- The exogenous demand in the model is defined in such a way that the model has maximum degrees of freedom to choose between 
the technologies to meet the demand. The final energy in the system is thus determined as far as possible endogenously in the model.
- For the processes, a distinction is made between complementary inputs/outputs with a fixed ratio to each other and 
substitutive inputs/outputs with a flexible ratio to each other. This should also allow processes to be modeled that 
can choose their energy sources endogenously.
- Capacity expansion limits have been defined per milestone years.
- The SEDOS data are provided for a 1-region Germany model. Cost parameters for the electricity grid are to be estimated 
for the overall system, considering demand and renewable energy supply.
- The European electricity market is considered but modeled in a simplified manner.

## 2.6 Emissions

General information:
- Emission types: CO2, methane & N2O
- The emission values should be standardised from the NRI Inventory table "global_emission_factors.xlsx".
- CO2 equivalents: The following factors are used for a consistent conversion into CO2 equivalents:
  - CH4: 25
  - N2O: 298
- Realisation of negative emissions in the model structure via additional commodities per sector (see "Commodity_Set" spreadsheet)
- Add emission concept graphic [CHECK]

Emission balancing:

- balancing during combustion & offsetting if necessary
  - Biogen: CO2 emissions from combustion & negative emissions from production/source processes of biogenic energy sources
  - Synthetic: CO2 emissions during combustion & model-endogenous negative emissions for production with carbon capture
  - Fossil: CO2 emissions during combustion

Differentiation of emissions:

- Global (CO2): Foreign key mapping to the global table with emission factors per energy source. Specification with a foreign key on the global table
- Process-specific (methane & N2O): Sector/process-specific emission factors due to higher dependence on process conditions 
- (e.g., firing temperature N2O, material moisture CH4 ...) Direct specification with a numerical value



[//]: # ()
[//]: # (### 2.3.3 Temporal aggregation method)

[//]: # ()
[//]: # (Temporal aggregation aims to improve the feasibility of energy system models by defining shorter but representative input time series. For this purpose, selected clustering methods form a number of N type periods with M time steps, where N and M are user-definable variables. A sequence of these N type periods should represent the original data as accurately as possible.)

[//]: # ()
[//]: # (#### Notes:)

[//]: # ()
[//]: # (- The definition of N and M should be chosen so that a good compromise between computability and representativeness can be found.)

[//]: # (- If the sequence of type periods is not considered, the storage behavior cannot be considered beyond the interval with M time steps. To take seasonal storage behavior into account, either)

[//]: # (  - Additional boundary conditions in the frameworks &#40;see FINE&#41;)

[//]: # (  - Separate aggregation for predefined periods &#40;e.g., Standard type weeks aggregation for seasons of a year&#41;)

[//]: # ()
[//]: # (- The criterion of security of supply is closely linked to the temporal resolution and the choice of time series and the type periods derived from them. In TSAM, extreme periods can also be considered for selected time series in the clustering process. Particularly, extreme weather events such as “dunkelflaute” should not be mapped in the SEDOS time series for operation. Still, they can be defined via capacity surcharges by defining availability parameters &#40;availability_constant&#41; for the processes. These...)

[//]: # ()
[//]: # (## 2.4 Spatial framework)

[//]: # ()
[//]: # (## 2.5 Technological framework with aggregations)

[//]: # ()
[//]: # (### 2.5.1 Description of the)

[//]: # ()
[//]: # (In SEDOS, the first focus is on detailed model structures in the electricity, heating, mobility, industry and X2X &#40;other conversion&#41; sectors. This means that researchers can use the reference data set to build models that are as detailed as possible and focus on a specific sector. When modeling energy systems, components from reality must always be abstracted into components in the model. This requires spatial aggregations on the one hand and technological aggregations on the other to ensure the computab...)

[//]: # ()
[//]: # (### 2.5.2 Treatment of parameters and auxiliary processes)

[//]: # ()
[//]: # (- For aggregated processes with different parameters, such as costs or emissions, a certain amount of error can be accepted. The choice of aggregation methodology is the responsibility of the APs and should ensure the lowest possible error.)

[//]: # (- Users can carry out further aggregations independently based on the most detailed level and with the help of the documentation.)

[//]: # ()
[//]: # (### 2.5.3 Selection and visualization of aggregations)

[//]: # ()
[//]: # (- The aggregation mapping list clearly defines the composition of the aggregation levels.)

[//]: # (- A tree structure can be used to display the aggregations graphically. [LINK])

[//]: # (- Modellers can take the relevant aggregations from the sectors from the reference data set.)

[//]: # (- Modellers can carry out possible further aggregations themselves based on the level of detail and assistance &#40;documentation&#41;.)

[//]: # ()
[//]: # (### 2.5.4 FAQs Aggregation)

[//]: # ()
[//]: # (#### What applies if aggregated processes have different &#40;non-fuel-related&#41; variable costs?)

[//]: # ()
[//]: # (- Aggregations must take place so you accept an error.)

[//]: # (- Sector APs decide which aggregation methodology makes the slightest error.)

[//]: # ()
[//]: # (#### Which input is used for the aggregated process? Can aggregation only take place within a fuel?)

[//]: # ()
[//]: # (- No - multiple inputs are enabled via "multiple input/outputs functionality" &#40;see chapter 2.7&#41;.)