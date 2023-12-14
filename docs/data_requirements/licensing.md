# Data Licencing

In the SEDOS project, Open Data is one of the main criteria for developing the Reference Energy System (RES) database. 
Open Data implies adequate licencing as a legal requirement, hence why this section aims to bring you up to speed regarding the nitty-gritty of licencing. 
By the end of this section, you'll be able to licence your input data adequately.

## Suitable data licences in SEDOS

??? note "How to document licences in OEMetadata?"
    
      
      If your data set has no licence, please **indicate the licence as "unknown"** in the licence-name field of the metadata. <br>
      <br>
      For example:      

      ```
      {
          "sources": [
              {
                  "title": "OEDatamodel-parameter",
                  "description": "Parameter data model for secondary input scalars and timeseries",
                  "path": "https://github.com/sedos-project/oedatamodel/tree/main/oedatamodel-parameter",
                  "licenses": [
                      {
                          "name": "CC0-1.0",
                          "title": "Creative Commons Zero v1.0 Universal",
                          "path": "https://creativecommons.org/publicdomain/zero/1.0/legalcode",
                          "instruction": "You are free: To Share, To Create, To Adapt",
                          "attribution": null
                      }
                  ]
              },
              {
                  "title": "Impact of electric vehicles on a future renewable energy-based power system in Europe with a focus on Germany",
                  "description": "Paper on novel modelling approach comprising a detailed representation of electric vehicles based on real driving patterns and interactions between the power systems of Germany and other European regions.",
                  "path": "https://doi.org/10.1002/er.4056",
                  "licenses": [
                      {
                          "name": "unknown",
                          "title": null,
                          "path": null,
                          "instruction": null,
                          "attribution": "Copyright © 2018 John Wiley & Sons, Ltd."
                      }
                  ]
              },
              {
                  "title": "Mobilität in Deutschland: Tabellarische Grundauswertung",
                  "description": "Mobilität in Deutschland (MiD) ist eine bundesweite Befragung von Haushalten zu ihrem alltäglichen Verkehrsverhalten im Auftrag des Bundesministeriums für Digitales und Verkehr (BMDV).",
                  "path": "https://bmdv.bund.de/SharedDocs/DE/Anlage/G/mid-2017-tabellenband.pdf?__blob=publicationFile",
                  "licenses": [
                      {
                          "name": "unknown",
                          "title": null,
                          "path": null,
                          "instruction": null,
                          "attribution": null
                      }
                  ]
              }
          ]
      }
      ```

1. For the data collection in WP3-8, you should choose data published under one of the listed licences below. 
2. Add the licence spdx-id and/or correct attribution for respective source in the metadata ([oem-key 12.4.1-5](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#source-keys)).
3. If your data is published under an open licence not listed below, please get in touch with *datenzentrum@rl-institut.de.*
> _Please note:_ non-conformant clauses such as <br> NC (non commercial) and ND (no derivates) <br>are **NOT** Open Data licences and must not be used. 

**Public Domain:** All rights granted.

- [CC0-1.0](https://creativecommons.org/licenses/by/4.0/legalcode) | recommended
- [PDDL-1.0](https://opendatacommons.org/licenses/pddl/1-0/) | recommended
- [dl-de/zero-2-0](https://www.govdata.de/dl-de/zero-2-0) | granted by German government
- [CC-PDDC](https://creativecommons.org/licenses/publicdomain/) | not recommended 

**Attribution/Permissive:** Use rights and relicensing granted. Proprietisation is possible. Correct attribution is required (see licence link).

- [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/legalcode)                            | recommended                             
- [ODC-By-1.0](https://opendatacommons.org/licenses/by/1-0/)                           | recommended                             
- [CDLA-Permissive-1.0](https://cdla.io/permissive-1-0/)                          
- [DL-DE-BY-2.0](https://www.govdata.de/dl-de/by-2-0) | granted only by the German   government
- [GeoZG ](https://www.gesetze-im-internet.de/geozg/index.html) (no official spdx-id)        | granted by German government            |

- [GeoNutzV](https://www.gesetze-im-internet.de/geonutzv/index.html)                             | granted by German government            

**Share-alike (Copyleft):** Use rights granted, propitiation impossible. 

- [ODbL-1.0](https://opendatacommons.org/licenses/odbl/1-0/)     | recommended   
- [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode) | not recommended

For further information on licences, see <br>
* [OEP Tutorial on Open-Data Licences](https://openenergy-platform.org/tutorials/jupyter/tutorial_open-data-licenses/) <br>
* [ifrOSS GitHub](https://github.com/ifrOSS/ifrOSS/blob/master/OpenDataLicenses.md) <br> 
* [Open Definition](https://opendefinition.org/licenses/)

## Missing licence? - Using data without an open licence

??? note "How to indicate missing licences in OEMetadata?"
    
      
      If your data set has no licence, please **indicate the licence as "unknown"** in the licence-name field of the metadata. <br>
      <br>
      For example:      

      ```
      {
          "sources": [
              {
                  "title": "Impact of electric vehicles on a future renewable energy-based power system in Europe with a focus on Germany",
                  "description": "Paper on novel modelling approach comprising a detailed representation of electric vehicles based on real driving patterns and interactions between the power systems of Germany and other European regions.",
                  "path": "https://doi.org/10.1002/er.4056",
                  "licenses": [
                      {
                          "name": "unknown",
                          "title": null,
                          "path": null,
                          "instruction": null,
                          "attribution": "Copyright © 2018 John Wiley & Sons, Ltd."
                      }
                  ]
              },
              {
                  "title": "Mobilität in Deutschland: Tabellarische Grundauswertung",
                  "description": "Mobilität in Deutschland (MiD) ist eine bundesweite Befragung von Haushalten zu ihrem alltäglichen Verkehrsverhalten im Auftrag des Bundesministeriums für Digitales und Verkehr (BMDV).",
                  "path": "https://bmdv.bund.de/SharedDocs/DE/Anlage/G/mid-2017-tabellenband.pdf?__blob=publicationFile",
                  "licenses": [
                      {
                          "name": "unknown",
                          "title": null,
                          "path": null,
                          "instruction": null,
                          "attribution": null
                      }
                  ]
              }
         ]
      }
      ```

If you want to use a data set without a licence or an open data licence, try the following steps: 

1. **Contact the authors of the data set** and ask for either the licence or send a request for user-and relicensing 
   rights. Templates in DE and EN can be found **[here](https://bwsyncandshare.kit.edu/f/2369369032>)**. Please **add 
   *datenzentrum@rl-institut.de* to the CC of the Email** and **store positive response [here](https://bwsyncandshare.kit.edu/f/2369341357)**. <br><br> 
2. **You can use the unlicensed data if you only extract a considerable small subset of a larger data set.** <br>

       - In Germany, the [Act on Copyright and Related Rights / Gesetz über Urheberrecht und verwandte Schutzrechte 
          (Urheberrechtsgesetz)](https://www.gesetze-im-internet.de/englisch_urhg/englisch_urhg.html) contains the paragraph [60c Scientific research (Copyright Act, § 60c Scientific Research)](https://www.gesetze-im-internet.de/englisch_urhg/englisch_urhg.html#p0479) that provides provisions specifically for non-commercial scientific research. According to this law:<br><br>
         * Up to **15 percent of a work** may be reproduced, distributed, and made publicly accessible **for** the purpose of 
           **non-commercial scientific research**. This can be done for a specific group of individuals conducting their own scientific research, as well as for individual third parties for the purpose of assessing the quality of scientific research.
         * Up to 75 percent of a work may be reproduced for one's own scientific research.


