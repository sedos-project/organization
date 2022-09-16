# Contributing data


## Creating data set

todo: Add general text concerning APs

Data sets should be provided in a tabular data format following the [input data conventions](input_data.md#Input-data-conventions).

## Creating metadata
All data must be provided along with metadata. Metadata on the OEP is in the JSON format. 
In this project the metadata version v1.5.1 will be used.

Metadata can be created/edited using the [MetaCreator](https://meta.rl-institut.de/meta_creator/151) 
(in order to edit metadata, copy metadata JSON, click on button "Edit JSON" and paste your metadata there).

A metadata template already exists for [scalars](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_scalars.json) and [timeseries](https://github.com/sedos-project/oedatamodel/blob/main/extended_datamodel/datamodel_timeseries.json).
> **Note:** All necessary metadata fields are already present in the template. <br> Please visit the [required metadata information](metadata.md#Required-metadata-information) section for more information about which fields have to be filled and adapted.

Even though a minimum mandatory set of metadata information is required, please fill in as much additional metadata information as possible to improve the subsequent use of your submitted data.


## Publishing data

The following step-by-step guide will show how to store data on the OEP and make it publicly available.
As this guide is meant for developers of AP4-8, the **Extended datamodel** will be used in the following.

todo: mit @henhuy absprechen fpr die nächsten 3 Kapitel

### Creating a table on the OEP
Once the metadata is set up, the corresponding table(s) on the OEP can be created using the [OEDatamodel API](https://modex.rl-institut.de).

### Uploading data to the OEP

### Releasing data on the databus