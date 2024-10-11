# Metadata

In SEDOS the metadata standard [OEMetadata v.1.5.1](https://github.com/OpenEnergyPlatform/oemetadata#open-energy-family---open-energy-metadata-oemetadata) is used.

In SEDOS a minimal mandatory set of metadata information is provided to:

1. automatically process the input data in the data pipeline,
2. to provide useful context for data interpretation, and
3. to fulfil legal requirements.

The following oem-keys have been provided in the metadata of our reference dataset.

## Mandatory set of metadata information

### General Keys

|  # |       Key       |                                                                   Description                                                                    |                               Example                                |                                             SEDOS convention                                             |
|:--:|:---------------:|:------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------:| 
|  1 |      name       |                                                       A file name or database table name.  <br/><br/>                                                      |              oep_metadata_table_example_v15                          |       <span style="color:red;">sector_process_name <br> <br> e.g. tra_road_mcar_bev_pass_0 </span>       |
|  2 |      title      |                                                  A human readable full title including author.                                                   |              RLI - OEMetadata - Metadata example table               | <span style="color:red;">sedos_sector_process_name <br> <br> e.g. sedos_tra_road_mcar_bev_pass_0 </span> |
|  4 |   description   | A description or abstract of the package. It should be usable as  summary information for the entire package that is described by the  metadata. | Example table used to illustrate the metadata structure and meaning. |                                                                                                          |
|  6 |     subject     |                                            An array of objects with topics of the data in OEO terms.                                             |                                                                      |                                                                                                          |
| 6.1 |      name       |                                                        The class label of the OEO terms.                                                         |                                energy                                |                                                                                                          |
| 6.2 |      path       |                                                              The URI of the class.                                                               |      https://openenergy-platform.org/ontology/oeo/OEO_00000150       |                                                                                                          |
|  8 | publicationDate |                               A date of publishing of the data or metadata. Date format is ISO 8601 (YYYY-MM-DD).                                |                              2019-02-06                              |                                                                                                          |

### Source Keys

Information about the individual sources the data stems from.

|    #   |     Key     |                                              Description                                             |                                                                                               Example                                                                                               |                                                         SEDOS convention                                                          |
|:------:|:-----------:|:----------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------:|
| 12     | sources     | An array of objects with the used and underlying sources of the data and metadata.                   |                                                                                                                                                                                                     |                                                                                                                                   |
| 12.1   | title       | A human readable title of the source, a document title or organisation name.                         | IPCC Fifth Assessment Report                                                                                                                                                                        |                                                                                                                                   |
| 12.2   | description | A free text description of the data set.                                                             | Scientific climate change report by the UN                                                                                                                                                          |                                                                                                                                   |
| 12.3   | path        | A URL to the original source.                                                                        | https://www.ipcc.ch/site/assets/uploads/2018/02/ipcc_wg3_ar5_full.pdf                                                                                                                               |                                                                                                                                   |
| 12.4   | licenses    | An array of objects under which the source is provided.                                              |                                                                                                                                                                                                     |                                                                                                                                   |
| 12.4.1 | name        | The SPDX identifier.                                                                       <br/>          | ODbL-1.0                                                                                                                                                                                            |  |
| 12.4.2 | title       | The official (human readable) title of the license.                                                  | Open Data Commons Open Database License 1.0                                                                                                                                                         |                                                                                                                                   |
| 12.4.3 | path        | A link to the license text.                                                                          | https://opendatacommons.org/licenses/odbl/1-0/index.html                                                                                                                                            |                                                                                                                                   |
| 12.4.4 | instruction | A short description of rights and restrictions. The use of tl;drLegal is recommended.                | You are free to share and change, but you must attribute, and share derivations under the same license. See https://tldrlegal.com/license/odc-open-database-license-(odbl) for further information. |                                                                                                                                   |
| 12.4.5 | attribution | The copyright owner of the source. If attribution licenses are used, that name must be acknowledged. | © Intergovernmental Panel on Climate Change 2014                                                                                                                                                    |                                                                                                                                   |

<!-- 
### License Keys

The license of your entire csv.

|   #  |     Key     |                                                                                                 Description                                                                                                 |                                                                                               Example                                                                                               | SEDOS convention |
|:----:|:-----------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:----------------:|
| 13   | licenses    | An array of objects of the license(s) under which the described  package is provided. It can depend on the licenses of the sources  (copyleft or share-alike) or can be granted by the creator of the data. |                                                                                                                                                                                                     |                  |
| 13.1 | name        | The SPDX identifier.                                                                                                                                                                                        | ODbL-1.0                                                                                                                                                                                            |                  |
| 13.2 | title       | The official (human readable) title of the license.                                                                                                                                                         | Open Data Commons Open Database License 1.0                                                                                                                                                         |                  |
| 13.3 | path        | A link to the license text.                                                                                                                                                                                 | https://opendatacommons.org/licenses/odbl/1-0/index.html                                                                                                                                            |                  |
| 13.4 | instruction | A short description of rights and restrictions. The use of tl;drLegal is recommended.                                                                                                                       | You are free to share and change, but you must attribute, and share derivations under the same license. See https://tldrlegal.com/license/odc-open-database-license-(odbl) for further information. |                  |
| 13.5 | attribution | The copyright owner of the data. If attribution licenses are used, that name must be acknowledged.                                                                                                          | © Reiner Lemoine Institut                                                                                                                                                                           |                  |
-->

### Provenience Keys

Information about changes on the metadata.

|   #  |      Key     |                                                                                                                       Description                                                                                                                       |           Example          | SEDOS convention |
|:----:|:------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------:|:----------------:|
| 14   | contributors | An array of objects of the people or organizations who contributed  to the data or metadata. Each object refers to one contributor. Every  contributor must have a title and property. The path, email, role and  organization properties are optional. |                            |                  |
| 14.1 | title        | A name of the contributor.                                                                                                                                                                                                                              | Ludwig Hülk                |                  |
| 14.2 | email        | A email address of the contributor or GitHub handle.                                                                                                                                                                                                    | @Ludee                     |                  |
| 14.3 | date         | The date of the contribution. If the contribution took more than a  day, use the date of the final contribiution. Date Format is ISO 8601.                                                                                                              | 2016-06-16                 |                  |
| 14.4 | object       | The target of the contribution. Which part of the package was  supplied or changed. Can be the data, metadata or both (data and  metadata).                                                                                                             | data and metadata          |                  |
| 14.5 | comment      | A free text commentary on what has been done.                                                                                                                                                                                                           | Fixed a typo in the title. |                  | 


### Resource Keys

Needed to process the csv-table for the OEP.

|                    #                     |                      Key                       |                                                                                                                                                                                                                                                                                   Description                                                                                                                                                                                                                                                                                    |                                 Example                                  |                                                                                                 SEDOS convention                                                                                                 |
|:----------------------------------------:|:----------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|                    15                    |                   resources                    |                                                                                                                                                                                                                                    An array of objects of the data. It describes the data resource as an individual file or (database) table.                                                                                                                                                                                                                                    |                                                                          |                                                                                                                                                                                                                  |
|                   15.1                   |                    profile                     |                                                                                                                                                                                 The profile of this descriptor according to the profiles  specification. This information is retained in order to comply with the  "Tabular Data Package" standard. Use "tabular-data-resource" for all  tables.                                                                                                                                                                                 |                          tabular-data-resource                           |                                                                                                                                                                                                                  |
| **<span style="color:red"> 15.2 </span>**  | **<span style="color:red"> name </span>**  | A name for the entire <br/>data package. The name must consist of only lowercase alphanumeric characters or underscore. It must not start with a number or underscore. In a database, this  will be the name of the table within the  schema containing it.  The name can correspond to the file name (minus the file-extension) of the data file describing the resource, if it complies with the naming convention above. Name also contains information about the [shema](https://openenergy-platform.org/dataedit/schemas) on the OEP, use "." to seperate shema from table name. |                                                                          |         **<span style="color:red"> Requiered for oedatamodel upload </span>**<br><br>**<span style="color:red"> model_draft.sector_process_name <br><br> e.g. model_draft.tra_road_mcar_bev_pass_0 </span>**          |
|                   15.3                   |                      path                      |                                                                                                                                                                                                                                         A URL that should be a permanent http(s) address or other path directly linking to the resource.                                                                                                                                                                                                                                         | https://openenergy-platform.org/dataedit/view/openstreetmap/osm_deu_line |                                                                                                                                                                                                                  |
|                   15.4                   |                     format                     |                                                                                                                                   The file extension. 'csv', 'xls', 'json' etc. would be expected to  be the standard file extension for this type of resource. When you  upload your data to the OEDB, in the shown metadata string, the format  will be changed accordingly to 'PostgreSQL', since the data there are  stored in a database.                                                                                                                                   |                                PostgreSQL                                |                                                                                                                                                                                                                  |
|                   15.5                   |                    encoding                    |                                                                                                                                                                       Specifies the character encoding of the resource's data file. The values should be one of the "Preferred MIME Names" for a character encoding registered with IANA. If no value for this key is specified then the default is UTF-8.                                                                                                                                                                       |                                  UTF-8                                   |                                                                                                                                                                                                                  |

### Resource Keys - Schema

Information about each column in the csv.

|      #     |       Key      |                                                                                                                                                      Description                                                                                                                                                       |                          Example                          |                                                                    SEDOS convention                                                                    |
|:----------:|:--------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|
| 15.6       | schema         |                                                                                An object that describes the structure of the present data. It  contains all fields (columns of the table), the primary key and optional  foreign keys.                                                                                 |                                                           |                                                                                                                                                        |
| 15.6.1     | fields         |                                                                                                                An array of objects describing a column and providing name, description, type and unit.                                                                                                                 |                                                           |                                                                                                                                                        |
| 15.6.1.1   | name           |                                                                                  The name of the field. The name must consist of only lowercase alphanumeric characters or underscore. It must not start with a number or underscore.                                                                                  |                           year                            |                                                                                                                                                        |
| 15.6.1.2   | description    |                                                                                                                                              A text describing the field.                                                                                                                                              |     Reference year for which the data were collected.     |                                                                                                                                                        |
| 15.6.1.3   | type           |                                                                                              The [data type](#datatypes) of the field. <br/>In <br/>case of a geom column in a database, also indicate the shape and CRS.                                                                                              |                        float array                        |                                                                                                                                                        |
| 15.6.1.4   | unit           |                                                                The unit, preferably SI-unit, that values in this field are mapped  to. If 'unit' doesn't apply to a field, use 'null'. If the unit is given  in a seperate field, reference this field.                                                                |                            MW                             |                                                                                                                                                        |
| 15.6.1.5   | isAbout        |                                                                                                                               An array of objects with describe the field in OEO terms.                                                                                                                                |                                                           | <span style="color:red;"> In case of [multiple concepts](ontology.md#annotation#conventions#for#automatic#data#processing) use <br>**C)Case2**</span>  |
| 15.6.1.5.1 | name           |                                                                                                                                           The class label of the OEO terms.                                                                                                                                            |                wind energy converting unit                |                                                                                                                                                        |
| 15.6.1.5.2 | path           |                                                                                                                                                 The URI of the class.                                                                                                                                                  | https://openenergy-platform.org/ontology/oeo/OEO_00000044 |                                                                                                                                                        |
| 15.6.1.6   | valueReference |                                                                                                               An array of objects for an extended description of the values in the column in OEO terms.                                                                                                                |                                                           |                                                                                                                                                        |
| 15.6.1.6.1 | value          |                                                                                                                                          The name of the value in the column.                                                                                                                                          |                          onshore                          |                                                                                                                                                        |
| 15.6.1.6.2 | name           |                                                                                                                                           The class label of the OEO terms.                                                                                                                                            |                     onshore wind farm                     |                                                                                                                                                        |
| 15.6.1.6.3 | path           |                                                                                                                                                 The URI of the class.                                                                                                                                                  | https://openenergy-platform.org/ontology/oeo/OEO_00000311 |             
|


## Optional set of metadata information


### Spatial and Temporal Keys

<table>
  <thead>
    <tr>
      <th>#</th>
      <th>Key</th>
      <th>Description</th>
      <th>Example</th>
      <th>SEDOS convention</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>10</td>
      <td><strong>spatial</strong></td>
      <td>An object that describes the spatial context of the data it contains.</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>10.1</td>
      <td>location</td>
      <td>A location of the data. In case of data where the location can be described as a point. May be specified as coordinates, URI, or addresses with street, house number, and zip code.</td>
      <td>52.433509, 13.535855</td>
      <td></td>
    </tr>
    <tr>
      <td>10.2</td>
      <td>extent</td>
      <td>A covered area. May be the name of a region, or the geometry of a bounding box.</td>
      <td>Europe</td>
      <td><span style="color:red">Germany</span</td>
    </tr>
    <tr>
      <td>10.3</td>
      <td>resolution</td>
      <td>Pixel size in case of a regular raster image. Reference to administrative level or other spatial division that is present as the smallest spatially distinguished unit size.</td>
      <td>1 ha</td>
      <td><span style="color:red">NUTS-0</span></td>
    </tr>
    <tr>
      <td>11</td>
      <td><strong>temporal</strong></td>
      <td>An object with the time period covered in the data. Temporal information should either contain a "referenceDate" or the keys describing a time series; in rare cases both.</td>
      <td></td>
      <td><span style="color:red"> For scalars:</span> <br> 
        ```
        "temporal": {
            "referenceDate": "2021",
            "timeseries": [
                {
                    "start": "2021-01-01",
                    "end": "2070-12-31",
                    "resolution": "yearly"
                }
            ]
        ```
        <span style="color:red"> For timeseries:</span>
        ```
        "temporal": {
		"referenceDate": "2021",
		"timeseries": [
			{
				"start": "2021-01-01",
				"end": "2021-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2024-01-01",
				"end": "2024-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2027-01-01",
				"end": "2027-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2030-01-01",
				"end": "2030-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2035-01-01",
				"end": "2035-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2040-01-01",
				"end": "2040-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2045-01-01",
				"end": "2045-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2050-01-01",
				"end": "2050-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2060-01-01",
				"end": "2060-12-31",
				"resolution": "hourly",
				"alignment": "left"
			},
			{
				"start": "2070-01-01",
				"end": "2070-12-31",
				"resolution": "hourly",
				"alignment": "left"
			}
		]
        ```

   </td>
    </tr>
    <tr>
      <td>11.1</td>
      <td>referenceDate</td>
      <td>The base year, month, or day. Point in time for which the data is meant to be accurate. The census data or a satellite image will have a reference date. Date Format is ISO 8601.</td>
      <td>2016-01-01</td>
      <td></td>
    </tr>
    <tr>
      <td>11.2</td>
      <td><strong>timeseries</strong></td>
      <td>An array that describes the time series.</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>11.2.1</td>
      <td>start</td>
      <td>The beginning point in time of a time series.</td>
      <td>2019-02-06T10:12:04+00:00</td>
      <td></td>
    </tr>
    <tr>
      <td>11.2.2</td>
      <td>end</td>
      <td>The end point in time of a time series.</td>
      <td>2019-02-07T10:12:04+00:00</td>
      <td></td>
    </tr>
    <tr>
      <td>11.2.3</td>
      <td>resolution</td>
      <td>The time span between individual points of information in a time series.</td>
      <td>30 s</td>
      <td></td>
    </tr>
    <tr>
      <td>11.2.4</td>
      <td>alignment</td>
      <td>An indicator of whether stamps in a time series are left, right, or middle.</td>
      <td>left</td>
      <td></td>
    </tr>
    <tr>
      <td>11.2.5</td>
      <td>aggregationType</td>
      <td>Indicates whether the values are a sum, average, or current.</td>
      <td>sum</td>
      <td></td>
    </tr>
  </tbody>
</table>

### Context Keys
<table>
  <thead>
    <tr>
      <th colspan="5"># Context Keys</th>
    </tr>
    <tr>
      <th>#</th>
      <th>Key</th>
      <th>Description</th>
      <th>Example</th>
      <th>SEDOS convention</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>9</td>
      <td><strong>context</strong></td>
      <td>An object that describes the general setting, environment, or project leading to the creation or maintenance of this dataset. In science, this can be the research project.</td>
      <td></td>
      <td>
 <span style="color:red">For example:</span>
```
"context": {
		"homepage": "https://sedos-project.github.io/.github/",
		"documentation": "https://sedos-project.github.io/.github/",
		"sourceCode": "https://github.com/sedos-project",
		"contact": "Hans-Christian.Gils@dlr.de",
		"grantNo": "03EI1040D",
		"fundingAgency": "Bundesministerium fÃ¼r Wirtschaft und Klimaschutz (BMWK)",
		"fundingAgencyLogo": "https://en.wikipedia.org/wiki/Federal_Ministry_for_Economic_Affairs_and_Climate_Action#/media/File:BMWi_Logo_2021.svg",
		"publisherLogo": "https://www.dlr.de/static/media/Logo-de.697a8e1f.svg"
	},
```



   </td>
    </tr>
    <tr>
      <td>9.1</td>
      <td>homepage</td>
      <td>A URL of the project.</td>
      <td>https://openenergy-platform.org/</td>
      <td></td>
    </tr>
    <tr>
      <td>9.2</td>
      <td>documentation</td>
      <td>A URL of the project documentation.</td>
      <td>https://openenergy-platform.org/about/</td>
      <td></td>
    </tr>
    <tr>
      <td>9.3</td>
      <td>sourceCode</td>
      <td>A URL of the project's source code.</td>
      <td>https://github.com/OpenEnergyPlatform</td>
      <td></td>
    </tr>
    <tr>
      <td>9.4</td>
      <td>contact</td>
      <td>A reference to the creator or maintainer of the data set. It can be an email address or a GitHub handle.</td>
      <td>contact@example.com</td>
      <td></td>
    </tr>
    <tr>
      <td>9.5</td>
      <td>grantNo</td>
      <td>An identifying grant number. In case of a publicly funded project, this number is assigned by the funding agency.</td>
      <td>01AB2345</td>
      <td></td>
    </tr>
    <tr>
      <td>9.6</td>
      <td>fundingAgency</td>
      <td>A name of the entity providing the funding. This can be a government agency or a company.</td>
      <td>Bundesministerium für Wirtschaft und Klimaschutz</td>
      <td></td>
    </tr>
    <tr>
      <td>9.7</td>
      <td>fundingAgencyLogo</td>
      <td>A URL to the logo or image of the funding agency.</td>
      <td>https://commons.wikimedia.org/wiki/File:BMWi_Logo_2021.svg#/media/File:BMWi_Logo_2021.svg</td>
      <td></td>
    </tr>
    <tr>
      <td>9.8</td>
      <td>publisherLogo</td>
      <td>A URL to the logo of the publishing agency of data.</td>
      <td>https://reiner-lemoine-institut.de//wp-content/uploads/2015/09/rlilogo.png</td>
      <td></td>
    </tr>
  </tbody>
</table>



### Review Keys

When using the provided templates above, the review keys are prefilled already.

|  # |       Key       |                                                                   Description                                                                    |                               Example                                |
|:--:|:---------------:|:------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------:|
|  17  |    @context     |                                       Necessary for registering Data on the Databus and to be SPARQL-able                                        |                             https://raw.githubusercontent.com/OpenEnergyPlatform/oemetadata/master/metadata/latest/context.json                          |


