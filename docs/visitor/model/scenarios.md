# Overview of the SEDOS applications

The SEDOS model structure is a comprehensive, open-source framework designed for the analysis and optimization of future energy systems with the focus on sector coupling. It is built to capture the complex interactions among power, heat, conversion (power-to-X), industry, and transport sectors, offering modelers a flexible and transparent tool to explore diverse decarbonization pathways.

## Possible Model Applications

- **Integrated Energy System Optimization:**  
  Analyze and optimize the entire energy system by capturing detailed interactions between sectors, enabling a holistic view of energy supply, conversion, and demand.

- **Scenario and Sensitivity Analysis:**  
  Develop and compare different future scenarios (e.g., high renewables penetration, accelerated decarbonization, gradual transition) to identify tipping points and assess the impact of various policy and technology choices.

- **Investment Planning and Technology Assessment:**  
  Support investment decisions by evaluating the competitiveness of alternative technologies and production routes, taking into account both existing and novel processes.

- **Sector Coupling Analysis:**  
  Examine the interdependencies between sectors, e.g., the influence of electrification in transport on power demand and identifying optimal strategies for a clean power supply.

## Supported Frameworks for Modeling Scenarios

The SEDOS structure is designed to be as framework–agnostic as possible and can be implemented with different energy system modeling frameworks, including **TIMES**, **FINE** and **oemof**.
The [data adapter repository](https://github.com/sedos-project/data_adapter) provided on GitHub can be used as template for the integration of the SEDOS data into the new modeling framework.
Depending on the type of framework you want to apply with the SEDOS data it might make sense to look into the specific adapters for our different frameworks:
- [TIMES Adapter](https://github.com/sedos-project/data_adapter_times)
- [FINE Adapter](https://github.com/sedos-project/data_adapter_fine)
- [oemof Adapter](https://github.com/sedos-project/data_adapter_oemof)
---
## Enhanced Scenario Exploration

The model’s design supports the integration of diverse future scenarios, making it a robust tool for policy analysis and strategic planning in the context of energy transition.
Within the SEDOS project we defined three possible scenarios to explore the future energy system:

**Base scenario ToKio - technology-open & cost-optimal**

Which technologies can reduce GHG emissions from energy use to a targeted level at minimum cost
(e.g. climate neutrality by 2045)?

**Scenario variation RIGa: Reduced import dependency for fossil gas**

How can the dependency on fossil gas imports, including LNG imports, be reduced to a specified minimum level at minimum 
cost while complying with the GHG reduction targets?

**Scenario variation SienA/B: sector integration**

In which areas can sector integration make a greater contribution to GHG reduction?

- SienA: Specification of a minimum use of hydrogen or H2 derivatives.
- SienB: Specification of a minimum domestic RE electricity generation.
---

In the following sections the [SEDOS GUI](gui.md) is introduced, which allows for an interactive exploration of some [preliminary model results](results.md).