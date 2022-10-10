# Ontological annotation of data

## Basic annotation knowledge with OEM 

Ontological annotation of data means that data is linked to ontological concepts in the metadata. 

In SEDOS we use the [oemetadata v.1.5.1](metadata.md) (OEM) as metadata standard. For more context about the OEM-keys in oemetadata v.1.5.1, see [here](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#metadata-keys-with-a-description-and-example).

In energy systems modelling, data is fed into a model via parameters and their associated values. In the following, when we speak about ontological annotation, we, therefore, speak of parameter names, which are linked to an ontological concept for definition.


The linkage of parameter name and ontological concept in OEM has three elements:

1. _user-defined parameter name_
2. _human-readable ontological concept name_
3. _Internationalized Resource Identifier (IRI)_ 

Below the general section of the oemetadata v1.5.1 is shown, [relevant for the ontological annotation of the table content itself](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#general-keys).

* The general content of the table is annotated in the `subject` key

```
    "name": null,
    "title": null,
    "id": null,
    "description": null,
    "language": [
        null
    ],
    "subject": [
        {
            "name": null,
            "path": null
        }
    ],
    "keywords": [
        null
    ],
    "publicationDate": null,
```
Below the resource section of the oemetadata v1.5.1 is shown, [relevant for ontological annotation of parameter names](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#resource-keys---schema).

## Link a parameter name to a suitable ontology concept

### Background know-how

Parameters can occur in the column header or as column value when dealing with tabular data.  

* A) Parameters in the column headers are annotated in the `isAbout` key.
* B) Parameters occurring within a column are annotated in the `valueReference` key.

```
"resources": [
        {
            "profile": null,
            "name": null,
            "path": null,
            "format": null,
            "encoding": null,
            "schema": {
                "fields": [
                    {
                        "name": null,
                        "description": null,
                        "type": null,
                        "unit": null,
                        "isAbout": [
                            {
                                "name": null,
                                "path": null
                            }
                        ],
                        "valueReference": [
                            {
                                "value": null,
                                "name": null,
                                "path": null
                            }
                        }
                    ]
                }
            } 
        ]
```



**A) Parameters in the column headers** - using `isAbout`:

1. _user-defined parameter name_ is put in _name_ (OEM-key 15.6.1.1), 
2. a suitable  _human-readable ontological concept name_ is put in _name_ (OEM-key 15.6.1.5.1),
3. _Internationalized Resource Identifier (IRI)_ is put in _path_ (OEM-key 15.6.1.5.2)

**For example: A column with values for the rotor diameter of a wind turbine:**
```
"resources": [
        {
            "profile": null,
            "name": null,
            "path": null,
            "format": null,
            "encoding": null,
            "schema": {
                "fields": [
                    {
                        "name": "ro_diam",
                        "description": null,
                        "type": null,
                        "unit": null,
                        "isAbout": [
                            {
                                "name": "rotor diameter",
                                "path": "http://openenergy-platform.org/ontology/oeo/OEO_00020144"
                            }
                        ],
                        "valueReference": [
                            {
                                "value": null,
                                "name": null,
                                "path": null
                            }
                        }
                    ]
                }
            } 
        ]
```


**B) Parameters within a column** - using `valueReference` and `isAbout`:

_`valueReference`_<br>

1. _user-defined parameter name_ is put in _value_ (OEM-key 15.6.1.6.1), 
2. a suitable  _human-readable ontological concept name_ is put in _name_ (OEM-key 15.6.1.6.2),
3. _Internationalized Resource Identifier (IRI)_ is put in _path_ (OEM-key 15.6.1.6.3)

_`isAbout`_<br>

When annotating using `valueReference`, don't forget to annotate the column itself in `isAbout`, as described in A).

**For example: A column containing various types of fuels:** 


```
"resources": [
        {
            "profile": null,
            "name": null,
            "path": null,
            "format": null,
            "encoding": null,
            "schema": {
                "fields": [
                    {
                        "name": "various_types_of_energy_carriers",
                        "description": null,
                        "type": null,
                        "unit": null,
                        "isAbout": [
                            {
                                "name": "portion of matter",
                                "path": "http://openenergy-platform.org/ontology/oeo/OEO_00000331"
                            }
                        ],
                        "valueReference": [
                            {
                                "value": "coal_HCV",
                                "name": "anthracite",
                                "path": "http://openenergy-platform.org/ontology/oeo/OEO_00000058"
                            },
                            {
                                "value": "green_diesel",
                                "name": "biodiesel",
                                "path": "http://openenergy-platform.org/ontology/oeo/OEO_00000071"
                            },
                            {
                                "value": "coal_LCV",
                                "name": "lignite",
                                "path": "http://openenergy-platform.org/ontology/oeo/OEO_00000251"
                            }
                        }
                    ]
                }
            } 
        ]
```

### With oemetadata builder

![wf](https://user-images.githubusercontent.com/7637364/191807277-712057b8-153c-4178-94a2-341ad8f010fd.gif)

## Annotation conventions for automatic data processing

In SEDOS, automatic data reasoning and processing are based mainly on ontological annotations in the metadata. 
Thus, thorough annotation and following the conventions are important for frictionless data processing.

* A) technology and technology_type (oem-key 6.1-2)
* B) for MiMo technologies the input and output energy vectors (oem-key 15.6.1.5.1-2)
* C) parameter names (oem-key 15.6.1.6.1-3)

### A) technology and technology_type

The technology and technology_type columns from the oedatamodel-concrete are filled with the information from the `subject` key.

### B) input and output energy vectors for MiMo technologies

The input and output energy vectors of technologies in SEDOS' reference energy system are defined in an external table.

For technologies with multiple input and/or output energy vectors it is not clear to which energy vector a parameter column refers.
To account for this the energy vector shall be annotated as a second concept in the `isAbout` key.

For example: A CHP plant table entailing two efficiency columns - for the electrical and thermal efficiency.

### C) parameter names

#### Case1 
**_In cases where there is a single suitable ontology concept in the OEO_** we'll use the keys `isAbout`, `valueReference` as explained above.

#### Case2 
**_In cases where there are multiple ontology concepts in the OEO that are suitable by using them in composition_** we'll use them as list in the `name` key.

For example: _thermal efficiency_ of a heat power plant (as column in a tabular data set)

The concept _thermal efficiency_ is not (yet, as of 23.09.22) available in the OEO, but the concepts:

- 'heat generation process' <http://openenergy-platform.org/ontology/oeo/oeo-physical/OEO_00010248>
- 'energy conversion efficiency' <http://openenergy-platform.org/ontology/oeo/OEO_00140049>

```
"resources": [
        {
            "profile": null,
            "name": null,
            "path": null,
            "format": null,
            "encoding": null,
            "schema": {
                "fields": [
                    {
                        "name": "thermal efficiency",
                        "description": "The column holds the values of the thermal efficiency of a heat power plant",
                        "type": null,
                        "unit": null,
                        "isAbout": [
                            {
                                "name": "['heat generation process' <http://openenergy-platform.org/ontology/oeo/oeo-physical/OEO_00010248>, 'energy conversion efficiency' <http://openenergy-platform.org/ontology/oeo/OEO_00140049>]",
                                "path": null
                            }
                        ],
                        "valueReference": [
                            {
                                "value": null,
                                "name": null,
                                "path": null
                            }
                        ]
                    },
```

todo: @JH-rli check with oemetadata builder functionalities

#### Case3
**_In cases where there is NO suitable ontology concept in the OEO_** we'll copy the term used in the data directly to the `name`key for further data processing in SEDOS.

!!! Note

        This is SEDOS-specific and needed for data processing. Normally one would leave the annotation in `isAbout` empty.

For example: _fantasy power plant parameter_

```
"resources": [
        {
            "profile": null,
            "name": null,
            "path": null,
            "format": null,
            "encoding": null,
            "schema": {
                "fields": [
                    {
                        "name": "fantasy power plant paramter",
                        "description": "The column holds values of a parameter, whose concept is not yet available in the OEO, of a fantasy power plant ",
                        "type": null,
                        "unit": null,
                        "isAbout": [
                            {
                                "name": "fantasy power plant parameter",
                                "path": null
                            }
                        ],
                        "valueReference": [
                            {
                                "value": null,
                                "name": null,
                                "path": null
                            }
                        ]
                    },
```




## Link a parameter name to multiple related ontology concepts
todo: decide on workflow, considering oemetadata builder yet limited functionality

### Via oemetadata builder
todo: decide on workflow, considering oemetadata builder yet limited functionality

``

