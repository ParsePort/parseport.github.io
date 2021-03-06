---
title: Standard level agreements
permalink: architecture/sla
parent: Architecture
nav_order: 2
has_toc: false
---

# Standard SLA
The Supplier’s standard service targets for availability of infrastructure (all timestamps are GMT+1):

| SLA (service target)                                      |                          |
|:----------------------------------------------------------|:-------------------------|
| Guaranteed availability in the operation’s business hours | 99.6 %                   |
| Operation’s business hours                                | Mon-Thursday 8:30-16:30, Friday 8:30-16:00  |
| Platform monitoring                                       | 24/7                     |



The above shall be calculated according to availability of server infrastructure.

## Service targets for availability of server instances (standard service targets)
ParsePort's standard responsibility for availability (operational responsibility) shall include matters up to and including the application described in the Agreement. Thus, the guaranteed availability on server instances shall be calculated at application level.

*Availability at application level shall be measured as follows:*

On an external cloud server, an agent is installed which at fixed intervals connects to and reports status on selected services to operations personnel. The agent reports on services which run on individual server instances. If the server, or just one of the services which are being monitored, becomes unavailable and thus does not send a message to the agent, an alarm will immediately be activated to make the operations personnel react.

As the server itself reports status through the agent, an alarm will also be activated if the network connection in ParsePort’s data centres is not available (and the server is thus not available).

Availability (uptime percentage) - per server instance – is calculated as follows:

_Available Operating Time (Measurement Period -Planned Downtime -Downtime)/Agreed Operating Time (Measurement Period -Planned Downtime))*100 % = Uptime per server instance_

The calculation does not include effects from data communication lines measured from ParsePort’s edge router to the Customer, the Customer’s network or units owned by the Customer.

### Total Availability (uptime percentage).
The total Availability (uptime percentage) shall determine compliance with,
”Guaranteed availability at application level in the operations business hours”. This shall be calculated as below:

_The sum of uptime per server instance for all server instances/Number of server instances = Total availability /Uptime percentage_

The availability (the uptime percentage) shall be calculated as an average of Availability/Uptimes for all server instances.
The following conditions shall not be viewed as downtime:

* Downtime solely caused by the Customer’s circumstances, including errors in the Customer’s software or data transmission lines.

* Downtime due to errors solely caused by a third-party supplier not having published an error in Software used by ParsePort.  ParsePort shall document to the Customer that the error had not been published.

* Downtime because of errors where the Customer has chosen to postpone the error correction.

* Downtime caused by other circumstances for which ParsePort is not responsible.

* Downtime caused by software and hardware components owned/licensed/leased/rented by the Customer for which no maintenance agreements with ParsePort have been made.


Additional operational responsibility – other than the above – shall be agreed separately. Service targets for infrastructure, in addition to standard operational responsibility, will be specified in the next section.

### Service targets, in addition to standard service targets
No other service targets for infrastructure except the above standard service targets have been agreed cf. previous section.

## Service targets for Operations support and Service Desk
The Supplier’s Service Desk and operations support services shall be supplied with the service targets which appear from the following section.

### Incidents – prioritisation and response times
Incidents requiring support shall be divided into priority levels by ParsePort. When reporting an incident, the Customer may request a priority level, but ParsePort shall make the final assessment and determine the priority. Prioritisation shall be determined based on impact (how many users or the type of users) and urgency.

| Priority     | Description              | Response time        |
|:-------------|:-------------------------|:---------------------|
| Priority 1   | A system-critical incident which causes complete system failure or unavailability of the Customer’s System.                   | If reporting is made in the period Monday-Thursday, 8:30-16:30 and Friday 8:30-16:00, problem solving is initiated within 60 minutes. If reporting is made outside the abovementioned period, problem solving is initiated within 120 minutes.|
| Priority 2   |	Incidents which have significant impact on the System’s functionality, reduce parts of the System’s functionality or cause significantly reduced performance.  In addition, incidents which cause risk of system failure. |	If reporting is made in the period Monday-Thursday, 8:30-16:30 and Friday 8:30-16:00, problem solving is initiated within 120 minutes.* If reporting is made outside the abovementioned period, problem solving is initiated within 240 minutes.*|
| Priority 3   |	Support-requiring incidents which comprise non-critical corrections to the System, like e.g. clean-up, moving data, cosmetic modifications and similar. Moreover, incidents in which the system is accessible for the users at the Customer, but where there are inconveniences or obstacles which prevent an error-free operation, or there is a risk that an incident will escalate to priority 2 if no measures are taken.| 	If reporting is made in the period Monday-Thursday, 8:30-16:30 and Friday 8:30-16:00, problem solving is initiated within 24 hours.*|

  * Calculated within Service Desk business hours.
