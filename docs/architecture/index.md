---
title: Architecture
permalink: /architecture/
has_children: true
nav_order: 2
has_toc: true
---
# Architecture
At ParsePort the most important is: XBRL made simple - this is also reflected in the architecture. Furthermore, the mantra is to make it as simple as possible for the end users, the struggle about understanding XBRL is the task for ParsePort.

The architecture for the ParsePort solution is scalable, flexible and secure. The applied design principles are to have isolated services, where sharing between services uses the same formats as expected from the API entry points. Overall the architecture is a service-oriented architecture, which is explained in the following section.


## Service-Oriented Architecture
The ParsePort solution has a service-oriented architecture, with a simple service bus with minimal influence on the business logic. The service-oriented architecture, provides a large flexibility and at the same time it is possible to handle security requirements from a central place (e.g. wrapping messages, provide timeouts for data and so on). The architecture follows and supports the process of converting a financial report in e.g. Excel to a XBRL filing report. One of the benefits here, is that the process of converting can be started at any state, if you for example already have the XBRL, then the solution can render the document to XHTML.

The overall architecture is present here, and each of the services are described in the following sections.

![Overall architecture for ParsePort solution](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/ParsePort/ArchitecturalDocumentation/master/architectural-overview/XBRL-high-level-simple.txt?token=ANLMBL5XEQKOGDQBSPR2ZDK57HKIO "Overall architecture for ParsePort solution")

The architecture is built to be able to scale, therefore no data is stored to physical files, as it would not be possible to share between multiple nodes. If there is a need for files, it is handled as blob storage, which can be shared in memory. The persistence in the system is used to store settings, user accounts and for the automatically mapping between your labels and the correct XBRL element. No customer data is persisted in the database.

### API Controllers
The API controllers are responsible for handling the input data and add requests to the service bus.

### Service bus
To be able to have a central mechanism for scaling our solution, the solution is built around a service bus. The solution can then be scaled for each of our services, if there is a huge load on a specific part of the solution. The service bus implementation service bus is built upon [MassTransit](https://masstransit-project.com/). With a service bus implementation, it is possible to spin up arbitrary producers in the network, thereby minimize waiting time due to a filled queue.

With respect to the [data handling](../security/datahandling.md) in the ParsePort solution, the service bus is used to signal when data should be deleted. In the same way, this also makes it possible to postpone the deletion in a simple way.




### Data Extract
The task for the service is to disassemble your financial data, this can be from JSON, Excel, CSV or even Word. The service split all relevant data and transform it into the [JSON format](../services/inputjson.md) used by the ParsePort API.

### Parsing
The task for this service is to analyse the input and provide a structure on the input received. This service is used by data extraction, an example is that ParsePort have created simplified tagging, therefore a need to parse the tagging, so the data extraction has easier processing. Another usage is the way calculations are found in Excel sheets, where the parsing service extract all information about formulas in Excel, and transform it to calculations that can be used in e.g. the ESEF taxonomy.

### Conversion
The task for this service is to add meta data to your financial data (which we disassembled via Data Extraction or from the [JSON format](../services/inputjson.md)) and translate your values into XBRL.


### Validation
This service is responsible for validation of any XBRL against a given taxonomy. The result of this service is a set of warnings and errors, if the XBRL does not follow the ruleset of the given taxonomy.

### Render
This service is responsible for transforming valid XBRL into either XHTML, JSON or any other format which the XBRL should have. Also, if there is any postprocessing that needs to be handled, it will be in this service. If there are any special requirements from your local authorities with respect to reporting, please contact us, then we might be able to handle your special case in the render service.
