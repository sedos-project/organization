# Frequently Asked Questions (FAQ)

# Data model usage

## **Scalar data**

1. ???+ note "How to connect data points with sources?"

        **Question:** Can I simply enter 'investment_cost': {'Bibtex X', 'Bibtex Y', 'Bibtex Z'} in the "source" 
        column to achieve an assignment to the values [600, 700, 500-800]?

        **Answer:** Specify a dict in the source column with a list as value: {'investment_costs': ['Bibtex X', 
        'Bibtex Y', 'Bibtex Z']} in the order of related data points. 


## **Timeseries data**

# Other

1. ???+ note "What do "f" and "p" mean in the commodities?"

        **Answer:** This distinguishes fuel-specific emissions ("f") from process-specific emissions ("p"). This is mainly relevant for some industrial processes.
