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

![sector_overview](../../graphics/model-frame-decisions_v3.svg)