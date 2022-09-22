# How to contribute data?

The following instructions will guide you through the process of contributing data in the SEDOS project. Hyperlinks direct you to more detailed information regarding the subject.

   
## 1. Create input data tables

* Collect and preprocess data into the tabular [oedatamodel-parameter](https://github.com/sedos-project/oedatamodel#oedatamodel-parameter) ([scalar](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_scalar.csv) or [timeseries](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_timeseries.csv)) thereby following the [input data conventions](input_data.md#Input-data-conventions)
* Store data sources in [BIB-file](https://bwsyncandshare.kit.edu/f/2388204355) and fill Bibtex-keys in "source"-column of the data table.
* **Note** timeseries data and scalar data are stored in two different tables


## 2. Create metadata

* Create the metadata according to the [OEMetadata v.1.5.1](https://github.com/OpenEnergyPlatform/oemetadata#open-energy-family---open-energy-metadata-oemetadata) for each data table
* Use the [MetaCreator](https://meta.rl-institut.de/meta_creator/151) to create and edit your metadata (in order to edit metadata, copy metadata JSON, click on button "Edit JSON" and paste your metadata there)
* Use the [scalar meta template](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/datamodel_scalars.json) and the [timeseries meta template](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/datamodel_timeseries.json).
* Fill in as many fields as possible, but at least a minimum of the [required metadata information](metadata.md#Required-metadata-information)
* Annotate the fields 'subject', 'isAbout' and/or 'valueReference' with useful ontological concepts by applying the Open Annotation Tool (OAT). [**TODO@CM: write step-by-step guide on how to do this**]
* List all data sources in the form of Bibtex-keys under the "sources" field
* Add necessary license information to the sources according to the [licensing guide](http://127.0.0.1:8000/data_requirements/licensing/#data-licencing)


## 3. Publish datapackages on the OEP

The following step-by-step guide will show how to store data on the OEP and make it publicly available.
As this guide is meant for developers of AP4-8, the **oedatamodel-parameter** will be used in the following.

!!! warning "Prerequisite for publishing on OEP"

        1. Data exists in **oedatamodel-parameter** format 
        2. Metadata exists with [mandatory set of metadata information](metadata.md#Mandatory-set-of-metadata-information) filled
        3. OEP [user account](https://openenergy-platform.org/user/register)        

### 3.1 Upload data to OEP with oedatamodel-API

**@HeHu-review&update** <br>
The oedatamodel-API uploads zipped datapackages to the OEP. 
Thus, 

* The first step is to create .zip file from the data, datapackage and metadata.
* Then open the [oedatamodel-API](https://modex.rl-institut.de/upload_datapackage/)
* Insert your token and select your zipped datapackage 
* Click `Datei absenden` to upload

### 3.2 Release data on the databus
**@HeHu-review&update** <br>
The oedatamodel-API can also register your datapackages in the databus. 

!!! Note

        Releasing your datapackage on the databus is only possible during the upload process in 3.1.

Before clicking `Datei absenden` to upload your data to the OEP

* Check the box `Release data on databus` in the [oedatamodel-API](https://modex.rl-institut.de/upload_datapackage/) for releasing your data on the databus


## 4. Create output data tables
**@HeHu & CM expand when process is clear** <br>

* Collect and postprocess modelling results into the tabular [OEDatamodel](https://github.com/sedos-project/oedatamodel) by following the output data conventions](input_data.md#Output-data-conventions)

