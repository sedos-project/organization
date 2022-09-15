## Ontological annotation of data

Ontological annotation of data means that data is linked to ontological concepts in the metadata. 

In SEDOS we use the [oemetadata v.1.5.1](metadata.md) (OEM) as metadata standard. For more context about the OEM-keys in oemetadata v.1.5.1, see [here](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#metadata-keys-with-a-description-and-example).

In energy systems modelling data is fed into a model via parameters and their associated values.  In the following, when we speak about ontological annotation, we therefore speak of parameter names, which are linked to an ontological concept for definition.


The linkage of parameter name and ontological concept in OEM has three elements:
1. _user-defined parameter name_
2. _human-readable ontological concept name_
3. _Internationalized Resource Identifier (IRI)_ 

Below the resource section of the oemetadata v1.5.1, [relevant for ontological annotation of parameter names](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#resource-keys---schema), is shown.

Parameters can occur in the column header or as column value, when dealing with tabular data.  

* A) Parameters in the column headers are annotated in the _"isAbout"_ field.
* B) Parameters occuring within a column are annotated in the _"valueReference"_ field.

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



**A) Regarding parameters in the column headers** - using "isAbout":
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


**B) Regarding parameters within a column** - using "valueReference":
1. _user-defined parameter name_ is put in _value_ (OEM-key 15.6.1.6.1), 
2. a suitable  _human-readable ontological concept name_ is put in _name_ (OEM-key 15.6.1.6.2),
3. _Internationalized Resource Identifier (IRI)_ is put in _path_ (OEM-key 15.6.1.6.3)

**For example: A column containing various types of fuels:** \
_(Note: The parameter describing the content of the column (column header), is linked using "isAbout")_
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

### Link a parameter name to a suitable ontology concept

#### Via MetaCreator

#### In local .json

### Link a parameter name to multiple related ontology concepts

#### Via MetaCreator

#### In local .json
```
{

"name": "CHP",

"path": "http://openenergy-platform.org/ontology/oeo/OEO_00000308"

},

{

"name": "small",

"path": null

}

```
``

