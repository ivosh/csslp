# 2. Secure Software Requirements

## Gathering Software Requirements
The effort is essential to the success of the project.
Requirements gathering is not just about understanding current solutions but also about planning for the future.

Align with Business Requirements, Legal Requirements, Ethical Requirements.
Cost of Downtime: financial and reputational damage.

### Project Failure
Late delivery, overbudget, failure to meet user expectations.
Causes:
- Wrong, incomplete or changing requirements
  - Not talking to the right people
  - Not understanding the business problems that need to be solved (focus on problem, not on solution)
  - Lack of understanding technology
- New unproven technology
- Unrealistic expectations
- Lack of experienced staff

### Project Success
- Build security into the project
- Start early
- Gather security and functional requirements
- Security-Conscious Software Development

### Gathering Security Requirements
Discover and Integrate security into entire SDLC. Security Benchmarking.

Stakeholders:
 - Customer (Think like the customer)
 - User (Think like the user)
 - Management (Find the balanance between functionality and cost)
 - Legal counsel (privacy, compliance)
 - IT Operations (network, help desk, development system)
 - Security

Methods:
- Observation
- Interviews (PNE = Protection Needs Elicitation)
- Documentation review
- Standards (such as PCI-DSS)

CIA - _Confidentiality_ (privacy, safety), _Integrity_ (accuracy), _Availability_ (uptime, response time).

Document Requirements:
- Requirements Traceability Matrix (RTM)
- Formal acceptance of risk (management sign-off => agreed-on security requirements)

Meet current and future business needs
- Upgrade/Improve
- Redesign (leverage new opportunities)

#### Top Down Planning
Integrate systems and functions together with security.

- John Zachman framework - business first, describe business processes.
- TOGAF standard - Enterprise Architecture methodology and framework from Open Group
- SABSA model - focus on security

#### Functional Requirements
What the system will do. What are the primary data flows.
How the system will meet business requirements (+ compliance with law and regulations).

User perspective - interfaces, ease of use, good screen layouts, transparent security.

Use cases and mis-use cases.

Compliance Requirements:
- Legal - Privacy, Secrecy (IPR), Uptime, Accuracy. Issues - location of data storage, processing, backup; data ownership.
- Regulatory - rules by agencies (NERC = North American Electric Reliability Corporation, food...)
- Industry standards
  -- payments (PCI-DSS = Payment Card Industry - Data Security Standard, PA-DSS = Payment Application - Data Security Standard)
  -- security (OWASP - Open Web Application Security Project)
  -- safety - Industrial Control Systems (ICS), Real-time systems (automobiles), Supervisory Control and Data Acquisition (SCADA)

#### Non-functional requirements.
Error handling. Audit and compliance. (Security). Reporting.
Configuration (environment, deployment). Infrastructure. Capacity (network, storage, CPU). Physical Security (FIPS 140-2).

Systemic Qualities of the system:
- Agility - cryptographic algorithms, elasticity, portability, testability, usability/understandability
- Reliability - response time
- Availability
- Serviceability/Maintainability
- Installability
- Useability

Database Qualities:
- Reliability
- Availability
- Scalability
- Recoverability
- ACID = Atomicity, Consistency, Isolation, Durability

Security Requirements:
- Access control levels
- Encryption (masking, obfuscation)
- Logs - storage, retention, compliance - support certificatio and audits

## Data Classification Requirements

## Data and Software Protection Requirements
