## Complementarity vs Substitution

Input and Output commodities can be defined as either complementary or substitutive. 

If they are defined as complementary, they are linked by a fixed ratio (e.g. the output of electricity from a combustion plant is always linked to emissions).
If they are defined as substitutive, they can be linked by a flexible ratio (e.g. the input of a ICEV either based on fossil or synthetic fuels).

Additional degrees of freedom within the model are achieved by considering these flexible shares of several input or output commodities in the energy system model.
The goal is to model processes that can choose their energy sources endogenously.
Considering the previous example, in the most cost-effective system, ICEVs could be supplied by fossil fuels provided by refinery processes or by a 
synthetic fuel chain based on electrolyzers and requiring additional electricity generation plants.


!!! Note "input_output format conventions in the process set"

    * Enclose substituting inputs or outputs in squared brackets `[ ]`
    * separate complementary inputs or outputs with `,` (comma)

For example the formatting may look like this:

| input                                         | process                     | output                   |
|-----------------------------------------------|----------------------------|--------------------------|
| [pri_oil_shale, sec_heating_oil, sec_biodiesel] | pow_combustion_st_oil_0_ag | sec_elec, emi_co2_f_pow |


## Parameter Input-Output Specifications

For processes with multiple input and/or output energy vectors it might not always be clear to which energy vector a 
parameter column refers. By `default`, parameters of a process are assigned to the main (first) output of a process from the Process_Set sheet in the 
main model_structure.xlsx available on [Zenodo](TODO: Add Link). If the default is incorrect or needs to be overwritten, please use the Parameter_Input-Output sheet to specify or reassign 
the process parameters’ inputs and outputs. It is for the data providers (WP4-8) to assess whether this is correct for each process with respect to the 
modelling. Accordingly, the parameter `defaults` do not appear in the input_output sheet, but are identified in the data pipeline.
<br>


!!! info "Example for parameter input-output specification"

    For example, the costs of an electrolyzer are normally indicated in relation to the input and not to the output, while
    for most other processes the costs are related to the main output. This exception has to be given as follows:
    
    | parameter          | process           | input     | output |
    |--------------------|-------------------|-----------|--------|
    | cost_fix_capacity_p| x2x_p2gas_aec_1   | sec_elec  |        |


