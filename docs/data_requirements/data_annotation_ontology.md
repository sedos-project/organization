## Ontological annotation of parameters 

Ontological annotation of parameters means that parameter names are linked to ontological concepts in the metadata. 

In SEDOS we use the [oemetadata v.1.5.1](metadata.md). For more context about the metadata fields see [here](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#metadata-keys-with-a-description-and-example)

The linkage of parameter names and ontological concepts has three elements:
1. _user-defined parameter name_
2. _human-readable ontological concept name_
3. _Internationalized Resource Identifier (IRI)_ 

_todo: expand conncetions of metadata fields and 1.2.3._

Column headers are annotated in the _"isAbout"_ field. \
Values within a column are annotated in the _"valueReference"_ field.

Below the resource section of the oemetadata v1.5.1, [relevant for ontological annotation of parameter names](https://github.com/OpenEnergyPlatform/oemetadata/blob/develop/metadata/latest/metadata_key_description.md#resource-keys---schema), is shown:

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
                        ]
                    },

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

