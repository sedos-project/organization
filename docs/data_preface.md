# Data preface

The SEDOS Reference Dataset (SRD) entails technology data across five sectors (power, heat, PtX, industry, mobility) 
and various aggregation levels.

This *data preface* provides additional information about the syntax of parameters and units in SRD.

??? note "Monetary value"
    
    If not further specified the base year for the monatary value is 2021.

    If monatary conversion were performed, the following logic was applied: <br>
    _currency_A(year_x) -> currency_B(year_x) -> currency_B(year_z)_ <br><br>
    e.g. USD2010 -> EUR2010 -> EUR2021 
    

## Units

| Symbol | Name     | Range   | Description                                       |
|-----|----------|---------|---------------------------------------------------|
| `%` | `Percent` | [0,100] | A number or ratio expressed as a fraction of 100. |
