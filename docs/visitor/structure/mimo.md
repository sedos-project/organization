### Input and output energy vectors

!!! Note "input_output insertion conventions"

    * Enclose substituting inputs or outputs in squared brackets `[ ]`
    * separate inputs or outputs with `,` (comma)

For processes with multiple input and/or output energy vectors it might not always be clear to which energy vector a 
parameter column refers.

By `default`, parameters of a process are assigned to the main (first) output of a process from the BW 
Sync&Share table - sheet: [Process_Set](https://bwsyncandshare.kit.edu/f/2458081675)
(the `default` does not appear in the input_output sheet, but is used in the backend of the data pipeline).
<br>
If needed, the `default` can be overwritten, simply by assigning other input(s) and output(s) to a specific 
parameter of the process in the [Parameter_Input-Output](https://bwsyncandshare.kit.edu/f/2458081675) sheet.

It is for the data providers (WP4-8) to assess whether this is correct for each process with respect to the 
modelling.
<br>
If the `default` is incorrect, the [Parameter_Input-Output](https://bwsyncandshare.kit.edu/f/2458081675) sheet should be used to specify process parameters' inputs and outputs accordingly.

??? info "Example for parameter input-output specification"

    For example, the costs of an electrolyzer are normally indicated in relation to the input and not to the output, while
    for most other processes the costs are related to the main output. This exception has to be given as follows:
    
    | parameter          | process           | input     | output |
    |--------------------|-------------------|-----------|--------|
    | cost_fix_capacity_p| x2x_p2gas_aec_1   | sec_elec  |        |


