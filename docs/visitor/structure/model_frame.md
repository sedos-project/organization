# Model Base

As a result of thorough discussions in the 3rd working package of the SEDOS project, the following list
provides assumptions and requirements to understand the model base. 
This sets the basic framework for modeling with the provided model structure also with different model generators.
The key points of the model base are:

- Deterministic model formulation with Linear Programming Optimization.
- Intertemporal Time-Span modeling with perfect foresight.
- Central planner solving perspective for macro-economic optimization. Business/regulatory aspects are neglected as far as possible.
  A consistent Weighted Average Cost of Capital (WACC) of 2% has been defined for all technologies and if necessary, taxes are deducted from the prices.
- Brownfield approach: Differentiation between existing technology stock (0X) vs new technology expansion (1X).
- Long-Term time horizon until 2070.
- Hourly time resolution with time series aggregation using the [tsam](https://tsam.readthedocs.io/en/latest/index.html) tool
- The SEDOS data are provided for a 1-region Germany model. Cost parameters for the electricity grid are to be estimated 
for the overall system, considering demand and renewable energy supply.
- A distinction is made between three energy categories: primary energy, secondary energy, and model exogenous energy demand. 
- The exogenous demand in the model is defined in such a way that the model has maximum degrees of freedom to choose between 
the technologies to meet the demand. The final energy in the system is thus determined as far as possible endogenously in the model.
- For the processes, a distinction is made between complementary inputs/outputs with a fixed ratio to each other and 
substitutive inputs/outputs with a flexible ratio to each other. This should also allow processes to be modeled that 
can choose their energy sources endogenously.
- To ease the feasibility of SEDOS-based models, additional aggregation levels are introduced due to the high level of 
  detail in the sectors. This allows the user to focus their model on individual sectors while other sectors are simplified.
- Capacity expansion limits have been defined per milestone years.
- The European electricity market is considered but modeled in a simplified manner.

<br>
The central assumptions are additionally highlighted in the figure below:
<br>
![sector_overview](../../graphics/model-frame-decisions_v3.jpg)


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