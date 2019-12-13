---
title: Security
permalink: security/
has_children: true
nav_order: 3
has_toc: true
---
# Security
This section collects the security information public avaliable for the ParsePort solution and ParsePort organisation. The security documentation is split into multiple parts:

* [Security policy](securitypolicies.md) - ParsePort security policy (public part).
* [Technical security](technicalsecurity.md) - Techincal security for e.g. integration towards ParsePort.
* [Data handling](datahandling.md) - Flow for how data is handled and time to live for data at ParsePort.

## Measures
ParsePort is on the process of getting the ISO 27001 certificate. Therefore all measures are or will be aligned with the ISO27001 ISMS.
Access to data center and hosting environemnts follows the least privilleged principles. Access is limited to only a very limited set of developers, and the access is reassessed on a yearly basis.

Access to the ParsePort environment is monitored with **TODO**, and counter measures are evaluated on a monthly basis.

All environments are centrally managed and updated. Development follows Secure Software Development Life Cycle [S-SDLC](https://resources.infosecinstitute.com/intro-secure-software-development-life-cycle), and all requirements to new features are analysed with respect to security risks.

## Policies
ParsePort security polices can be found here: [Security policies](securitypolicies.md). Please contact us, if you as a partner have any security related questions, which are not answered in the policies or in [Technical security](technicalsecurity.md).

## Hosting providers
At ParsePort we have two suppliers to host our solutions. The primary hosting provider is Global Connect (located in Denmark), and the secondary hosting provider is Azure (all services running in the area of North Europe).

### IaaS from Global Connect
The primary data center for the ParsePort solutions is located in Denmark. We have three similar and dedicated server setups for `Test`, `PreProd` and `Prod`, where `Prod` is the environment exposed publicly and `PreProd` is a fallback, if anything happens to `Prod`. All servers are managed by Global Connect, to ensure correct patching and regular updates of the OS. To access the server setups, ip-whitelisting is used in combination with MFA.

The three server setups are fully decoupled, and have their own networks. All servers are behind a firewall with active intrusion prevention.

**TODO** Deployments are fully automated, which minimizes the access to the data center, and minimizes error prone manual tasks.

### IaaS in Microsoft Azure
Services that cannot be solely run with Windows in a HyperV environment, are hosted at Azure. At the current state the following services run in Azure:
* Service to build iXBRL viewer
* Service to convert PDF to HTML
* Service to supervise the health of all environments
* Integration test of all environemnts

All hosting from Azure are located in North Europe (Ireland). All integration towards Azure uses TLS 1.2, and the same policies are applied in Azure as for the IaaS from Global Connect.

Deployments are fully automated, which minimizes error prone manual tasks.
