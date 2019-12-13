---
title: Security policy
permalink: security/policy/
parent: Security
nav_order: 1
has_toc: false
---

# Security policy

This document is a statement, addressed to ParsePort's IT department, suppliers and partners, about the obligations they make when dealing with ParsePort's data and IT systems. The document is also an information to people associated with ParsePort about the measures taken to secure the IT systems.

## Audience
This policy applies to any person who has been granted access to the systems in ParsePort, when employed by ParsePort or as an external partner. At the same time, these persons are responsible for any third parties being permitted access to the equipment to comply with this policy when using the equipment.

## Common techincal security measures
ParsePort's network must always be based on standard protocols. Protocol selection is made by the IT manager. When changing the protocol, the external adviser must give their recommendation as well as help elucidate fall groups, sources of error, etc.

The infrastructure must be up-to-date at all times and secured by the IT manager. The work is done under the direction of the Executive Board, and possibly through the assistance of an external competence advisor.

The infrastructure must be reviewed once a year, in the context of planning the annual IT strategy plan.

## Suppliers, service og repair
Servers and PCs should be installed with standard basic software that can be serviced by general IT vendors, unless there are significant reasons for otherwise.

In order to ensure the easiest possible approach to complaints cases and remedying errors, the number of suppliers should be limited as far as possible.

When equipment with built-in storage media such as PCs, servers and mobile devices is handed over to a third party, it must comply with ParsePort's IT security rules. If the device contains company data and the storage medium is not encrypted, this must be done or the storage media removed.

### Security requirements for suppliers
ParsePort sets security requirements for IT vendors that must be met.

Any IT vendor must comply with this IT security policy. At the same time, user rights management and control, physical security and regular backup routines of hardware and software are expected to be established. In addition, the systems must be protected by technologies and measures that limit the risk of attacks against systems operated on behalf of ParsePort. Technologies include, for example, firewall and antivirus, while measures can be active logging and policies enforced on the systems.

In addition, ParsePort assumes that the supplier proactively monitors the outsourced equipment and other systems that may affect the operation and stability of solutions provided by the supplier on behalf of ParsePort. The scope of requirements for the supplier may vary depending on the type of service being outsourced. As there may be different SLAs and terms, refer to the individual contracts signed with the supplier.

## IT-equipment
IT equipment must be approved by the IT manager and may only be used as long as the product continues to have an active life cycle in the form of software and hardware updates.

## Backups
All internal infrastructure components and customer-facing systems must be backed up on an ongoing basis.
The backup must be tested at least annually for possible restore of individual files, as well as of individual servers.

## Vira and hacking
All ParsePort servers are secured with antivirus software that automatically downloads new definitions on an ongoing basis. All viruses known by the program are scanned for all relevant files.

The log of the antivirus program is continuously monitored by the IT manager. Initially, it is impossible to provide adequate guidelines for viruses and virus attacks, but ParsePort continuously uses external IT security company with technical experience in incident and forensic handling to minimize damage and downtime and isolate the incident as quickly as possible. If, as an end user, it is suspected that the PC has received a virus, all tasks on the system must be canceled. The PC is isolated from the network and the IT manager is contacted.

All PCs and servers must have a valid antivirus program installed. ParsePort's internal network is protected by firewall and is isolated from other networks, only with access from the Global Connect internal zone from which the base infrastructure is operated. All zones at Global Connect are protected by both firewall and intrusion prevention system.

Apart from firewall protection, all infrastructure located at Global Connect is also protected with the Intrusion Prevention System for additional protection.

To ensure impartial testing of the systems, external penetration tests are performed at least once a year for all zones where ParsePort has equipment at Global Connect.

Software to bypass system and application controls may only be used by professional security consultants and solely for the purpose of securing the systems. Furthermore, these must not be used without the written consent of the Executive Board and the IT manager.

## Data persistence
There are two locations for data storage, depending on whether the data storage is for ParsePort's internal infrastructure or for ParsePort's customer-facing software (product).

Both ParsePort's internal and customer-facing IT systems are located at Global Connect in a professional ISAE 3402 approved as well as ISO 27001 and ISO 9001 certified data center on an IaaS platform. At Global Connect data is both physically and virtually secured against unauthorized access.

### Internally infrastructure
To ensure centralization of data, as well as having a smaller attack surface, all employees work on a Microsoft Remote Desktop solution which, besides the mail platform, is the only place that stores internal data.

**TODO** Office365 solution with MFA and audit trail

### Customer-facing infrastructure
The customer-facing infrastructure is used exclusively for data processing and conversion. A user is granted access with username and password, then the user uploads a file, that is being processed by the system. When the processing is complete, the user can retrieve the processed data. Afterwards both the uploaded and processed data are deleted.

## Updates of systemes
All IT systems must be regularly updated.

* At least once a month, critical software updates (Operating system, etc.)
* Critical updates of hardware components (firmware, etc.) must be made at least every six months.
* An internal vulnerability scan must be conducted at least annually to clarify internal risks.

The IT manager is responsible for keeping abreast of vulnerabilities and their potential risks, if they are relevant to ParsePort's infrastructure.

## Licenses
All software used in ParsePort must have a valid license attached.

All software purchases / registrations must either be made by or registered with the IT manager who then stands for documentation and asset management.

# Physical security
The foundation for securing IT equipment is good physical IT security.

## Physical security - data center
At ParsePort, all servers are outsourced to Global Connect.

In order to achieve proper physical security, Global Connect has the following physical measures:

* Air conditioning to protect against overheating and inappropriate humidity
* 24/7 access control with multiple lock types
* Alarm
* Fire resistant materials
* Automatic fire fighting system
* Servers that are lifted from the floor for protection against liquid liquids
* Power redundancy in the form of UPS plant and diesel generator
*	Video surveillance
* Perimeter protection in the form of confined areas

## Physical security - HQ
At ParsePort's head office, located at Roholmsvej 12 A, 2, 2620 Albertslund has the following physical measures:

* Key lock for entry. (shared with other tenants)
* Key lock for door, key protected
* Alarm connected to alarm center with personal code for each employee
* Video surveillance connected to alarm center
* Smoke cannon

## Cables
Cables used at ParsePort's address for IT equipment in the form of, for example, power cord, network cable, HDMI cables, etc. must be labeled so that they can be identified. Similarly, when using cross-fields at the address, it should be possible to identify the endpoints by marking.

## Wireless network
Wireless networks are about WiFi communication that is done to gain access to a network of resources from one or more devices.

All setup / modification / dismantling of wireless networks must be such that they are protected against intrusions by unauthorized persons.

Wireless networks must at least comply with the following requirements:

* Encryption minimum according to WPA2 standard
* Password must be used for setup and immediately changed from original
* SSID needs to be changed from factory default

## Data backup
The backup is taken by Global Connect and must comply with the following requirements:
* Backup daily
* The backup must be “application aware” - be able to backup data stored in applications where full disk backup cannot generate valid backup. If this is not possible, the application must make a data dump locally daily, so that the normal file backup takes care of this.
* Backup data must at all times be physically secured in the same way as the backup data
* Backup data must be physically located in a data center other than the backup source and at least 1 kilometer apart

## Data / media disposal
The IT manager is responsible for the disposal of all internal IT equipment, including the protection against data loss.

All storage media must be taken out of IT equipment and sent for professional destruction by a provider offering professional data destruction.

In case the storage media cannot be removed from the IT equipment, the entire IT equipment must be submitted for destruction.

If IT equipment is to be reused outside ParsePort, this must be sanitized for data using a method that at least complies with NIST Special Publication 800-88 Revision 1 - Purge.

## Labeling and delivery of equipment
The IT manager is responsible for the registration, labeling and delivery of IT equipment. As well as for registration in ParsePort's IT asset management documentation.

## Miscellaneous
All employees must always be aware of IT security in such a way that data is best protected and handled.

Employees in ParsePort must also be aware of any inconsistencies or actual breaches of the IT security policy. If you become aware of this, this must either be addressed directly to the individual colleague, communicated to the immediate superior or to the IT manager, depending on the nature of the case.

# E-mail og doument handling
Email is today one of the most widely used communication tools, both internally and externally. The handling of electronic mail and documents, henceforth referred to as e-mail, is therefore a central element in the daily work of ParsePort.

All employees will also have to deal with e-mail, and must therefore also be able to observe and comply with the security requirements associated with it.

With the introduction of electronic document management and digital signature, the legal effects of electronic documents have in many cases gradually been compared with ordinary hand-signed paper documents. Therefore, a set of common guidelines is needed for how e-mail should be received and answered.

## Definition of an e-mail
In this context, e-mail means: Any transmitted / sent document or message in electronic form from or to one of ParsePort's domains.

However, there is a distinction between internal and external e-mails, where internal e-mails are sent only over closed circuits where all communication with the mail server is encrypted, but external e-mails can be transported without encryption.

It goes without saying that the levels of security in handling them will vary depending on the nature and sensitivity of the document. For example, there is a difference between a regular meeting call and transfer of customer information.

## Legal validity of emails
In Denmark, there are pending cases to determine whether e-mails are legally binding in the same way as ordinary letter exchange, as judgments have so far been dropped on both sides.

Digitally signed emails are expected to be valid at least the same level as physical letters / contracts, as one can document the sender / signer.

When no digital signature is used, and in any case of doubt as to the validity, legal effects or other regulatory framework, e-mail should not be used.

However, for informal communication and regular correspondence, email remains one of the preferred tools.

## Handling incoming emails
Any company or individual should be able to make electronic contact with ParsePort in the form of e-mail, and receive an electronic response.

The processing of e-mail does not differ from the receipt of regular mail, and any valid inquiry should be answered promptly.

If there is processing time or waiting time for the inquiry, the sender should receive a receipt for receiving the inquiry.

In principle, ParsePort will not receive documents via email. If a customer wants to submit their accounting data, please refer to using [parseport.com](https://parseport.com) to upload their accounting data.

## Handling outgoing emails
Any reply to an electronic mail must include a signature indicating ParsePort as the sender of the message.

Email should contain information about expectation of recipient in case the message is sent to the wrong one.

## Mailboxes
All official electronic correspondence to ParsePort is initially based on the main address [info@parseport.com](mailto:info@parseport.com).

In connection with scheduled absence (holidays, holidays, or the like) of more than one business day, each employee must ensure that senders of e-mails that send to a personal mailbox are either notified via the "not present" function in Outlook, or that the email is redirected to a colleague(s) or a shared mailbox.

## SPAM and Mail antivirus
All emails to and from ParsePort are scanned by Fusemail for both spam and viruses. If messages contain one of these, they are quarantined at Fusemail for 90 days and then deleted.

If Fusemail identifies a virus in a mail that can be safely removed, the secure part of the email (message) will be delivered.

At the same time, the solution from Fusemail acts as a "backup" team for ParsePort's mail systems in that Fusemail holds mail for up to 14 days if there are problems delivering the message to ParsePort's Exchange server.

# Production system (customer-facing system)
ParsePort's primary business is the creation / generation of XBRL data.

## The system
ParsePort allows customers to create XBRL files using three different interfaces.

1. Graphic interface website that presents a login interface where the customer logs in to a TLS 1.2 secured page using a username and password. The customer can then upload a data file, after which ParsePort's system converts / processes it, and the customer can then download the XBRL data file.
2. Excel Add-in set up with customer's username / password. Using Add-in, the data file is transferred via TLS 1.2 to ParsePort's systems, after which the system converts / processes it and returns an XBRL file with data.
3. API interface, for use by customers' own programs / software. So that the customer can embed the logic of ParsePort into their own applications or API supporting software. The API interface is used by the customer's solution calling ParsePorts API via TLS 1.2 with a key, as well as data for conversion / processing. ParsePort's system then returns the XBRL file of data.

## System Availability
The system is accessible from all over the Internet and is protected according to the two sections "Technical safety" and "Physical security".

## Data security
All communication with the production system must be encrypted during transport over the internet minimum according to the TLS 1.2 standard (RFC 5246).

All data stored in the production system must be segmented in a way that it is not possible for customers on the platform to access each other's data.
