---
title: Architecture
permalink: /architecture/
has_children: true
nav_order: 2
has_toc: true
---
# Architecture
Intro...
**TODO** add text here - what can be found in this chapter
**TODO** add eg network diagram here - simplified

## Service Oriented Architecture
__TODO add text here__
Why SOA
How
What does it mean for the end user

![Overall architecture for ParsePort solution](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/ParsePort/ArchitecturalDocumentation/master/architectural-overview/XBRL-high-level-simple.txt?token=ANLMBL5XEQKOGDQBSPR2ZDK57HKIO "Overall architecture for ParsePort solution")

### Service bus
To be able to have a central mechanishm for scaling our solution, the solution is build around a service bus. The solution can then be scaled for each of our subprocesses, if there is a huge load on a specific part of the solution. The service bus implementation service bus is built upon [MassTransit](https://masstransit-project.com/).

### ServiceX
Purpose of ServiceX
Reponsibility

Overall the [ParsePort API](https://xbrlapi.parseport.com) has four services to offer, and then one service for providing inputs to the other four services. The four services can be used  independently or in steps starting with: **[Extract]** - the service for disassamble your financhial data, this can be from JSON, Excel, CSV or even Word. Then **[Conversion]** which adds meta data to your finansial data and translate your values into XBRL. **[Validation]** validates the XBRL against the given taxonomy, to make sure that the correct rules are followed. The last step if to **[Render]** the validated XBRL, and transform it to either XHTML or JSON, which then can be used to report your data to your local authorities. **[Taxonomies]** provides a set of taxonomies support by ParsePort. Furthermore, **[Taxonomies]** provides generel setttings you can use in your input to ParsePort API.

**TODO** Add a section pr service in architecture / pr service described in Services

 [Link to input json](../services/inputjson.md)
