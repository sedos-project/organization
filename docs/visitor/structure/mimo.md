### Input and output energy vectors

!!! Note "input_output insertion conventions"

    * Enclose substituting inputs or outputs in squared brackets `[ ]`
    * separate inputs or outputs with `,` (comma)

For processes with multiple input and/or output energy vectors it might not always be clear to which energy vector a 
parameter column refers.

By `default`, parameters of a process are assigned to the main (first) output of a process from the Process_Set sheet in the 
main model_structure.xlsx available on [Zenodo](TODO: Add Link). If the default is incorrect or needs to be overridden, simply use the Parameter_Input-Output sheet to specify or reassign 
the process parameters’ inputs and outputs. It is for the data providers (WP4-8) to assess whether this is correct for each process with respect to the 
modelling. Accordingly, the parameter `defaults` do not appear in the input_output sheet, but are identified in the data pipeline.
<br>


??? info "Example for parameter input-output specification"

    For example, the costs of an electrolyzer are normally indicated in relation to the input and not to the output, while
    for most other processes the costs are related to the main output. This exception has to be given as follows:
    
    | parameter          | process           | input     | output |
    |--------------------|-------------------|-----------|--------|
    | cost_fix_capacity_p| x2x_p2gas_aec_1   | sec_elec  |        |


