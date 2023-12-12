# Frequently Asked Questions (FAQ)

# Data model usage

## **Scalar data**

1. ??? note "How to connect data points with sources?"

        **Question:** Can I simply enter 'investment_cost': {'Bibtex X', 'Bibtex Y', 'Bibtex Z'} in the "source" 
        column to achieve an assignment to the values [600, 700, 500-800]?

        **Answer:** Specify a dict in the source column with a list as value: {'investment_costs': 'Bibtex X, 
        Bibtex Y, Bibtex Z'} in the order of related data points. 

1. ??? note "Where is the difference between column type "float" and "float array"?"

        **Answer:** The table below shows the expected column formatting:
         
         | float | float array  |
         |-------|--------------|
         | 23.44 | [1.24, 3.44] |
         | 23    | [5.3, 100.5,10.4]  |
         | 10.3  | [10.5, 23]   |

         When a table on the OEP is created the column type cannot be changed anymore. <br>
         If you want to add data rows that contain bandwidths in the future, you should choose the column type 
         "float array".


## **Timeseries data**

# Other

1. ??? note "What do "f" and "p" mean in the commodities?"

        **Answer:** This distinguishes fuel-specific emissions ("f") from process-specific emissions ("p"). This is mainly relevant for some industrial processes.
