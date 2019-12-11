---
title: Architecture
permalink: /architecture/
has_children: true
nav_order: 2
has_toc: true
---
# Architecture
Intro...

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

 [Link to input json](../services/inputjson.md)
