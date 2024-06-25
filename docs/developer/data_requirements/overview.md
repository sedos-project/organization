# Overview of the SEDOS data architecture

This section provides an introductory overview of SEDOS' data architecture and its elements, which you will find 
explained more detailed in this documentation.

In the SEDOS project, data is collected, preprocessed and published by its partners in five work packages (WPs) 4 
to 8 representing five energy sectors (electricity, heat, ptx, transport, industry). Each WP is managed by one 
partner, who contributes its energy sector expertise. 
WPs 4-8 each create multiple input data data packages and upload them to the [OEP](https://openenergy-platform.
org/dataedit/view/model_draft?query=sedos&tags=246) via the [OEDatamodel-API](https://modex.rl-institut.de/create_table/).

The project's data architecture follows the [frictionless data](https://specs.frictionlessdata.io/data-package/) 
conventions. Everytime new data is uploaded to the OEP, partners also need to register the new data version on 
the databus via the OEDatamodel-API.
Thus, the latest data versions from all WPs are available on the databus - ready for further processing in the 
SEDOS data pipeline.

Input data packages generated and published by WP 4-8 will be automatically checked for updates.
The partners in WP9 will then download the input datapackages from the OEP and use it to set up, parameterize and 
solve their energy system model. 
The modelling results will be post-processed and uploaded to the OEP by the partners of WP9. 

A generalized representation of a datapackage is shown in the figure below. A datapackage consists of:

* **data** - containing parameters and values for modelling, and
* **metadata** - describing the structure of the datamodel, and providing context to the data. 


![datapackage](../../graphics/datapackage.jpg)


