# Overview of the SEDOS data architecture

This section provides an introductory overview of SEDOS' data architecture and its elements, which you will find 
explained more detailed in this documentation.

In the SEDOS project, data has been collected, preprocessed and published by its partners in five work packages (WPs) 4 
to 8 representing five energy sectors (electricity, heat, ptx, transport, industry). Each WP is managed by one 
partner, who contributes its energy sector expertise. Data can be uploaded each process for itself or in so named artifacts, 
which can contain multiple processes with a similar table structure.
Multiple input data packages have been created and uploaded onthe [OEP](https://openenergy-platform.
org/dataedit/view/model_draft?query=sedos&tags=246) via the [OEDatamodel-API](https://modex.rl-institut.de/create_table/).

The project's data architecture follows the [frictionless data](https://specs.frictionlessdata.io/data-package/) 
conventions. A generalized representation of a datapackage is shown in the figure below. A datapackage consists of:

* **data** - containing parameters and values for modelling, and
* **metadata** - describing the structure of the datamodel, and providing context to the data. 


![datapackage](../../graphics/datapackage.jpg)


Everytime new data is uploaded to the OEP, partners also need to register the new data version on 
the databus via the OEDatamodel-API. Thus, the latest data versions from all WPs are available on the databus - 
ready for further processing in the SEDOS data pipeline.

[//]: # (## TODO: Umfang der Daten beschreiben)