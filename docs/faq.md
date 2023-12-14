# Frequently Asked Questions (FAQ)

This is the FAQ section. It will be updated from the Questions from the SEDOS Matrix Chat.

## Data model usage

This section centers around the data model usage.

1. ??? question "Why do I get an error when registering my OEP table with my metadata?"
 
         This can have many reasons. Please check, if:        

         * The last entry in a dictionary has no `,` behind the value. Try to format your JSON in Notepad++ before 
         uploading. If it passes the error will not occur.





### **Scalar data**

1. ??? question "How to connect data points with sources?"

        **Question:** Can I simply enter 'investment_cost': {'Bibtex X', 'Bibtex Y', 'Bibtex Z'} in the "source" 
        column to achieve an assignment to the values [600, 700, 500-800]?

        **Answer:** Specify a dict in the source column with a list as value: {'investment_costs': 'Bibtex X, 
        Bibtex Y, Bibtex Z'} in the order of related data points. 

1. ??? question "Where is the difference between column type "float" and "float array"?"

        **Answer:** The table below shows the expected column formatting:
         
         | float | float array  |
         |-------|--------------|
         | 23.44 | [1.24, 3.44] |
         | 23    | [5.3, 100.5,10.4]  |
         | 10.3  | [10.5, 23]   |

         When a table on the OEP is created the column type cannot be changed anymore. <br>
         If you want to add data rows that contain bandwidths in the future, you should choose the column type 
         "float array".


### **Timeseries data**

## Other

1. ??? question "What do "f" and "p" mean in the commodities?"

        **Answer:** This distinguishes fuel-specific emissions ("f") from process-specific emissions ("p"). This is mainly relevant for some industrial processes.


1. ??? question "If a document does not have a licence, does it automatically has a CC-BY licence or a copyright?"

        **Answer:** If no licence is given, copyright applies. Follow [this pattern](data_requirements/licensing.md#missing#licence#-#using#data#without#an#open#licence) for documentation.


 
1. ??? question "My process-table-name and parameter names contain hyphens `-`, is that allowed?"

        **Answer:** **No**, in neither process-table-name or parameter nameshyphens `-` are allowed. Please stick to the [naming conventions](data_requirements/input_data.md#naming#conventions#for#data#tables#and#parameters)


1. ??? question "In which form should the sources be entered in the CSV tables?"

        **Answer:** Please set your bibtexkey as the following pattern: <br><br>
         **[AP-number][author][year]** <br><br>
         ```
         {'capacity_e_inst': '8Kraft2021b, 8ADAC2023', 'capacity_tra_connection_flex_max': '8Kraft2021b, 8ADAC2023', 'capacity_tra_vehicles_inst': '8S&PG2023', 'cost_fix_tra': '8Kraft2023, 8ADAC2023, 8ADAC2023b', 'cost_inv_tra': '8Kraft2021b, 8ADAC2023', 'cost_var': '8Kraft2023, 8ADAC2023, 8ADAC2023b', 'efficiency_sto_in': '8Keil2017', 'efficiency_sto_out': '8Keil2017', 'efficiency_tra_electrical': '8Kraft2021b, 8ADAC2023', 'efficiency_tra_g2v': '8RuckeSchoe2022', 'efficiency_tra_v2g': '8RuckeSchoe2022', 'lifetime': '8Kraft2011', 'mileage': '8BaumeHautz2014, 8Progn2021', 'occupancy_rate': '8infas2018, 8AdolfBalze2014', 'sto_init': 'ownAssumption', 'sto_self_discharge': '8XuBehre2023'}
         ```
         When you have multiple sources within a bandwidth, just separate the source by comma, as shown above.


1. ??? question "Should the unit of percent be specified in the metadata as in the Parameter_Set sheet on BWSync with "%" or as described in the AP1-pad as "percent" ( 3. [E] "unit": "percent", [0,100])?"

        **Answer:** In the metadata you should use the symbol `%`. (Group decision -> more convenient)

