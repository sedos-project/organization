# SEDOS Datamodel

Within the SEDOS project two datamodels are used:

1. **OEDatamodel** is used to represent input/output data for energysystem modelling. 
This datamodel will be used to gather input data from AP4-8, apply ontology from metadata to it and 
restructure it in order to make it available for simulation models. 
Further information about the OEDatamodel can be found in the documentation at [sedos-project/oedatamodel](https://github.com/sedos-project/oedatamodel).

2. **Extended Datamodel** is used for preprocessed input data. 
This datamodel is supposed to be used by AP4-8 in order to store data on the OpenEnergyPlatform (OEP).

## Publishing data
The following step-by-step guide will show how to store data on the OEP and make it publicly available.
As this guide is meant for developers of AP4-8, the **Extended datamodel** will be used in the following.

### Creating metadata
All data must be provided along with metadata. Metadata on the OEP is in the JSON format. 
In this project the metadata version v1.5.1 will be used.

Metadata can be created/edited using the [Metadata Creator](https://meta.rl-institut.de/meta_creator/151) 
(in order to edit metadata, copy metadata JSON, click on button "Edit JSON" and paste your metadata there).

There already exists a starting metadata for [scalars](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_scalars.json) and [timeseries](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_timeseries.json).
> **Note:** All necessary fields are already present - only _parameter_ fields at scalar metadata, respectively _series_ fields at timeseries metadata have to be changed!

Please fill in as much metadata as possible. 
Especially the ontology (OEO) terms for each resource field are needed for further processing (building the OEDatamodel; see above).

### Creating a table on the OEP
Once the metadata is set up, the corresponding table(s) on the OEP can be created using the [OEDatamodel API](https://modex.rl-institut.de).

### Uploading data to the OEP
### Releasing data on the databus

