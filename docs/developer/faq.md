# Frequently Asked Questions (FAQ)

This is the FAQ section. It will be updated from the Questions from the SEDOS Matrix Chat.

## Data model usage

This section centers around the data model usage.

1. ??? question "I am currently unsure what I should enter for OEP token. Have I overlooked any instructions?"

         * You can find your API-Token in your OEP profile -> in the top-right corner of the OEP website -> under your 
         name -> settings -> API-Token. See [**here**](how_to_contribute_data.md#3#initialize#table#on#the#oep)

### **Scalar data**


1. ??? question "Why do I get an error when uploading my CSV to OEP ?"

         * The double-quotes of the JSONs were unfortunately not correct 
         TODO: @FELIX - Was ist die solution hier???


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

## Metadata

1. ??? question "Why do I get an error when registering an OEP table with my metadata?"
 
         This can have many reasons. Please check, if:        

         * The last entry in a dictionary has no `,` (comma) behind the value. Try to format your JSON in Notepad++ 
         before uploading. If it passes the error will not occur.

         * "id": null, - The key wasn't there

         * "description" key wasn't there - every column needs a description key. It can be `null` though.

         * "name": "model_draft.hea_hh_heater_boil_dual_biomass", - it must be **"model_draft"** and **not 
         "model-draft"**. See [**here**](data_requirements/metadata.md#resource#keys) 

         * The double-quotes of the JSONs were unfortunately not correct

         * "type": "string", - string with small s; and not "type": "String"

1. ??? question "Do the resources/schema/fields have to be in the correct order, or does it not matter?"

        **Answer:** The order of the fields must be the same as the order of the columns in the CSV.


1. ??? question "If a document does not have a licence, does it automatically has a CC-BY licence or a copyright?"

        **Answer:** If no licence is given, copyright applies. Follow [this pattern](data_requirements/licensing.md#missing#licence#-#using#data#without#an#open#licence) for documentation.



## Other

1. ??? question "What do "f" and "p" mean in the commodities?"

        **Answer:** This distinguishes fuel-specific emissions ("f") from process-specific emissions ("p"). This is mainly relevant for some industrial processes.

 
1. ??? question "My process-table-name and parameter names contain hyphens `-`, is that allowed?"

        **Answer:** **No**, in neither process-table-name or parameter nameshyphens `-` are allowed. Please stick to the [naming conventions](data_requirements/input_data.md#naming#conventions#for#data#tables#and#parameters)


1. ??? question "In which form should the sources be entered in the CSV tables?"

        **Answer:** Please set your bibtexkey as the following pattern: <br><br>
         **(AP-number)(author)(year)** <br><br>
         ```
         {'capacity_e_inst': '8Kraft2021b, 8ADAC2023', 'capacity_tra_connection_flex_max': '8Kraft2021b, 8ADAC2023', 'capacity_tra_vehicles_inst': '8S&PG2023', 'cost_fix_tra': '8Kraft2023, 8ADAC2023, 8ADAC2023b', 'cost_inv_tra': '8Kraft2021b, 8ADAC2023', 'cost_var': '8Kraft2023, 8ADAC2023, 8ADAC2023b', 'efficiency_sto_in': '8Keil2017', 'efficiency_sto_out': '8Keil2017', 'efficiency_tra_electrical': '8Kraft2021b, 8ADAC2023', 'efficiency_tra_g2v': '8RuckeSchoe2022', 'efficiency_tra_v2g': '8RuckeSchoe2022', 'lifetime': '8Kraft2011', 'mileage': '8BaumeHautz2014, 8Progn2021', 'occupancy_rate': '8infas2018, 8AdolfBalze2014', 'sto_init': 'ownAssumption', 'sto_self_discharge': '8XuBehre2023'}
         ```
         When you have multiple sources within a bandwidth, just separate the source by comma, as shown above.


1. ??? question "Should the unit of percent be specified in the metadata as in the Parameter_Set sheet on BWSync with "%" or as described in the AP1-pad as "percent" ( 3. [E] "unit": "percent", [0,100])?"

        **Answer:** In the metadata you should use the symbol `%`. (Group decision -> more convenient)

1. ??? question "Is it problematic that all data uploaded there can be viewed without restriction before our publication?"

        **Answer:** When uploading your data to the OEP it is still listed as a "draft". This means that although they are already available for viewing, they are not prominently displayed (this only happens after a peer review). As long as the data is not published by us, nobody will accidentally come across it. But it is not impossible.


1. ??? question "Do the SEDOS-gits runs on an RLI or a German server?"

        **Answer:** Our [SEDOS repos](https://github.com/sedos-project) are all on GitHub.com right now. <br>
        The data is stored on the [OpenEnergyPlatform](https://openenergy-platform.org/dataedit/view/model_draft?query=sedos&tags=246), the website only takes the data and forwards it to the OEP and also registers it on the [Databus](https://databus.openenergyplatform.org/) (the data is only linked there). The OEP itself is located on a server at the University of Magdeburg.



