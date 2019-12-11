---
title: Technical security
permalink: /security/technicalsecurity/
parent: Security
nav_order: 2
has_toc: false
---
# Technical security
**TODO** Introduction about what to find here..

Development at ParsePort follows the Secure Software Development Life Cycle [S-SDLC](https://resources.infosecinstitute.com/intro-secure-software-development-life-cycle). In the CI/CD pipeline, ParsePort makes use of static code analysis, the following are used:
* [SonarQube](https://www.sonarqube.org/) to scan our code for security vulnabilities, to ensure best pratises are followed. Furthermore, SonarQube is used to keep the maintainability high, which enable fast mitigations if any vulnability is found.
* [Dependabot](https://dependabot.com/) used to scan our dependencies and 3rd party libraries.
* **TODO** Update [PenTest]() On a yearly basis a penetration test is preformed against your environments. The result of the test, is used to update requirements cf. S-SDLC


## Identity provider
**TODO** SAML 2.0

### Protocol(s)
**TODO**

#### Integration
**TODO**



## Transport Layer Security
The transport layer security at https://xbrlapi.parseport.com grades [A+](https://www.ssllabs.com/ssltest/analyze.html?d=xbrlapi.parseport.com&hideResults=on), based on SSLlabs from Qualys.

### Protocol(s)
At the moment, it is only TLS 1.2, which are accepted, untill the TLS 1.3 is released.
