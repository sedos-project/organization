# How to contribute data?

The following instructions will guide you through the process of contributing data in the SEDOS project. Hyperlinks direct you to more detailed information regarding the subject.

*An [example]() showing the final result of the individual steps is used to clarify the instructions.*

## 1. Create input data tables

* Collect and preprocess data into the tabular [oedatamodel-parameter](https://github.com/sedos-project/oedatamodel#oedatamodel-parameter) ([scalar](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_scalar.csv) or [timeseries](https://github.com/sedos-project/oedatamodel/blob/main/oedatamodel-parameter/oedatamodel-parameter-datapackage_timeseries.csv)) thereby following the [input data conventions](data_requirements/input_data.md#Input-data-conventions)
* Store data sources in [BIB-file](https://bwsyncandshare.kit.edu/f/2388204355) and fill Bibtex-keys in "source"-column of the data table.
* **Note** timeseries data and scalar data are stored in two different tables

*Result: [scalar]() & [timeseries]() csv*

## 2. Create metadata

* Create the metadata according to the [OEMetadata v.1.5.1](https://github.com/OpenEnergyPlatform/oemetadata#open-energy-family---open-energy-metadata-oemetadata) for each data table
* Use the [scalar meta template](https://raw.githubusercontent.com/sedos-project/oedatamodel/main/oedatamodel-parameter/datamodel_scalars.json) and the [timeseries meta template](https://raw.githubusercontent.com/sedos-project/oedatamodel/main/oedatamodel-parameter/datamodel_timeseries.json) to build your metadata
* Use the [oemetadata builder](https://openenergy-platform.org/dataedit/oemetabuilder/) to create and edit your metadata 
    * -> copy scalar/timeseries meta template
    * -> click on blue button "Edit JSON" 
    * -> click in opening window, with CTRL+A select all and paste scalar/timeseries meta template
    * -> click "save" to confirm
* Fill in as many keys as possible, but at least the minimum [required metadata information](../data_requirements/metadata/#required#metadata#information)
* Annotate the keys `subject`, `isAbout` and/or `valueReference` with useful ontological concepts using the oemetadata builder 
    * -> go to the column you want to annotate
    * -> click on blue button "Add isAbout" or "Add Value reference" or "Add Subject"
    * -> click into the `name` line 
    * -> type in the concept you're looking for
    * -> choose a suitable ontology concept from the dropdown menu
    * -> click to confirm
    * ![wf](https://user-images.githubusercontent.com/7637364/191807277-712057b8-153c-4178-94a2-341ad8f010fd.gif)
* List all data sources in the form of Bibtex-keys under the `sources` key
* Add necessary license information to the sources according to the [licensing guide](../data_requirements/licensing/#data-licencing)

*Result: [metadata]() for each csv table*

## 3. Initialize table on the OEP

In order to add data to an OEP table, the (empty) table must be initialized on the OEP in the first place.
In order to create the table, the resource from metadata is used, 
whereby the [name of the resource](data_requirements/metadata.md#resource#keys) (OEM-key 15.2) is used to define the 
OEP schema and the table name (table_name, to avoid spaces) in a pattern of ```"schema.table_name"``` (i.e. "name": 
"model_draft.sedos_tech_wind_turbine") 

The fields from [resource schema](data_requirements/metadata.md#resource#keys#-#schema) are used to create the 
columns of the table. Initializing OEP table is done via: 

* Visit [oedatamodel-API](https://modex.rl-institut.de/create_table/)
* Insert your OEP Username and Token 
* Select metadata file to create OEP table
* Submit 

*Result: empty [scalar]() and [timeseries]() tables on the OEP*

## 4. Publish datapackages

The following step-by-step guide will show how to store data on the OEP and make it publicly available.
As this guide is meant for developers of AP4-8, the **oedatamodel-parameter** will be used in the following.

!!! warning "Prerequisite for publishing on OEP"

        1. Data exists in **oedatamodel-parameter** format as CSV file
        2. Metadata exists with [mandatory set of metadata information](../data_requirements/metadata/#mandatory#set#of#metadata#information) filled
        3. OEP [user account](https://openenergy-platform.org/user/register)
        4. Databus [user account](https://energy.databus.dbpedia.org/) (Create account on "Login" button)
        5. Databus API Key (On Databus go to Profile -> Settings -> Scroll down to "Create New API Key" to generate key)
        6. Table has been created on OEP (3. Initialize table on the OEP)

### 4.1 Upload data to OEP with oedatamodel-API

The oedatamodel-API uploads CSV files to the OEP. While uploading, incoming data is checked against 
metadata schema from related table.
Thus, 

* Prepare upload data in CSV file according to metadata in related table
* Then open the [oedatamodel-API](https://modex.rl-institut.de/upload/)
* Insert your token, enter table name and schema (defaults to "model_draft") and select your CSV file
* Click `Datei absenden` to upload

In case upload data contains errors (format, naming, etc.) an error report is returned. 
Otherwise, data is appended to given table on the OEP.

*Result: [scalar]() and [timeseries]() tables on the OEP*

### 4.2 Release data on the databus

The oedatamodel-API can also register your datapackages on the databus. 
Registering data on the databus must be done everytime, a new version of the data is available on the OEP.
In doing so, other users will be able to query the most recent data from the OEP or to query for a specific data 
version.
In order to register your new data you have to:

* Open the [oedatamodel-API](https://modex.rl-institut.de/databus/)
* Enter your username (username is not email address) and API Token
* Enter table name and schema (defaults to "model_draft")
* Enter new version string (at least one row in your table must be present with given string in column "version")
* Submit

Now, your data should be registered and available on the databus. 
As the SEDOS pipeline regularly checks for updates on the databus, 
your new data version should be considered in next pipeline build.

*Result: OEP tables registered on the [databus]()*

## 5. Create output data tables
@HeHu & CM expand when process is clear 
