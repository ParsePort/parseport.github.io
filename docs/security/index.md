---
title: Security
permalink: /security/
has_children: true
nav_order: 3
has_toc: true
---
# Security
**TODO** Introduction - short intro and then point to each of the sub pages

* [Technical security](technicalsecurity.md) - Options for integration and which technologies that are applied
* [Data handling](datahandling.md) - Flow for how data is handled and time to live for data at ParsePort

## Measures (what do we do)
**TODO** Start the ISO ISMS part here - then when we have a correct system, we can merge

## Policies (where to find / what to publish)
**TODO** Might be a page for itself

## Hosting providers
**TODO** Intro
### IaaS from GlobalConnect
**TODO** What security services do we have at GC?

### IaaS in Microsoft Azure
Services that cannot be soley run with Windows in a HyperV environemnt, are hosted at Azure. At the current state the following services run in Azure:
* Service to build iXBRL viewer
* Service to convert PDF to HTML
* Integration test of all environemnts

All hosting from Azure are located in North Europe (Ireland). All integration towards Azure uses TLS 1.2, and the same policies are applied in Azure as for the IaaS from GlobalConnect.
