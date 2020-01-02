---
title: Technical security
permalink: security/technicalsecurity/
parent: Security
nav_order: 2
has_toc: false
---
# Technical security
Development at ParsePort follows the Secure Software Development Life Cycle [S-SDLC](https://resources.infosecinstitute.com/intro-secure-software-development-life-cycle). In the CI/CD pipeline, ParsePort makes use of static code analysis, the following are used:
* [SonarQube](https://www.sonarqube.org/) to scan our code for security vulnabilities, to ensure best pratises are followed. Furthermore, SonarQube is used to keep the maintainability high, which enable fast mitigations if any vulnability is found.
* [Dependabot](https://dependabot.com/) used to scan our dependencies and 3rd party libraries.
* **TODO** Update [PenTest]() On a yearly basis a penetration test is preformed against your environments. The result of the test, is used to update requirements cf. S-SDLC


## Identity provider
The ParsePort solution has its own identity server, which are built upon [identityserver.io](https://identityserver.io/).

As a partner you will get `clientId` and `clientSecret` generated in the ParsePort backend, to use for authentication towards the ParsePort API. The standard way for communication is then witht he use of JWT tokens.

### Protocol(s)
At the current point in time, the standard authentication is via SAML, which can seem old school, but in this way the full control of access is held in the ParsePort solution.

If there is a request for integration via SAML2.0, then take contact and it will be configured for you.

## Transport Layer Security
The transport layer security at https://xbrlapi.parseport.com grades [A+](https://www.ssllabs.com/ssltest/analyze.html?d=xbrlapi.parseport.com&hideResults=on), based on SSLlabs from Qualys. On a querterly basis the certificates are reviewed to ensure the grade can be held at A+.

All parseport.com domains are behind a [DNSSEC](https://www.internetsociety.org/deploy360/dnssec/basics/), which protects against attackers whom could intercept your DNS queries.

### Protocol(s)
At the moment, it is only TLS 1.2, which are accepted, until the TLS 1.3 is released.
