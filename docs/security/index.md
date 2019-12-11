---
title: Security
permalink: /security/
has_children: true
nav_order: 3
has_toc: true
---
# Security
**TODO** Introduction - short intro and then point to each of the sub pages

* [Security policies](securitypolicies.md) - ParsePort security policies (public part)
* [Technical security](technicalsecurity.md) - Options for integration and which technologies that are applied
* [Data handling](datahandling.md) - Flow for how data is handled and time to live for data at ParsePort

## Measures (what do we do)
**TODO** Start the ISO ISMS part here - then when we have a correct system, we can merge

## Policies
ParsePort security polices can be found here: [Security policies](securitypolicies.md). Please contact us, if you as a partner have any security related questions, which are not answered in the policies or in [Technical security](technicalsecurity.md).

## Hosting providers
At ParsePort we have two suppliers to host our solutions. The primary hosting provider is GlobalConnect (located in Denmark), and the secondary hosting provider is Azure (all services running in the area of North Europe).

### IaaS from GlobalConnect
The primary data center for the ParsePort solutions is located in Denmark. We have three similar and dedicated server setups for `Test`, `PreProd` and `Prod`, where `Prod` is the environment exposed publicly and `PreProd` is a fallback, if anything happens to `Prod`. All servers are managed by GlobalConnect, to ensure correct patching and regular updates of the OS. To access the server setups, ip-whitelisting is used in combination with MFA.

The three server setups are fully decoupled, and have their own networks. All servers are behind a firewall with active intrusion prevention.

**TODO** Deployments are fully automated, which minimizes the access to the data center, and minimizes error prone manual tasks.

### IaaS in Microsoft Azure
Services that cannot be solely run with Windows in a HyperV environment, are hosted at Azure. At the current state the following services run in Azure:
* Service to build iXBRL viewer
* Service to convert PDF to HTML
* Service to supervise the health of all environments
* Integration test of all environemnts

All hosting from Azure are located in North Europe (Ireland). All integration towards Azure uses TLS 1.2, and the same policies are applied in Azure as for the IaaS from GlobalConnect.
