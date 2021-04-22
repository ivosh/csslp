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
- Legal - Privacy, Secrecy (IP), Uptime, Accuracy. Issues - location of data storage, processing, backup; data ownership.
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
- Logs - storage, retention, compliance - support certification and audits

## Data Classification Requirements
Data must be protected according to risk, legal requirements and business needs.

Risk based classification:
- Sensitive data
- Critical data

Types of data:
- Structured
- Unstructured

Data classification requirements:
- Legal requirements
- Business needs: Operations (criticality, backups, proximity, bandwidth, response time, storage type)

### Data Recovery
Disaster Recovery Planning - recovery of IT services after a major outage.
Recovery Point Objective (RPO) - what amount of data we can afford to loose. Drives the type and amount of backups.
Recovery Time Objective (RTO) - how long it takes to restore IT services.

### Data Protection
Randomization, Tokenization, Masking, Encryption.

Data Labeling - based on sensitivity, retention, ownership; electronic and physical labels; codes instead of names.

#### Privacy and Secrecy
Secrecy - military, government, IP
Privacy - protect information sensitive to an individual

Need to Know (NTK) - access to private data based on business need to know.
Restrict access to sensitive data.
Ensure training of staff (clearance, review of access).

#### Privacy Requirements
Legal or Industry Standards (such as payment card industry - compliancy benchmarks).

Hardware, Software, Storage, Display (reports and receipts), Communications.

### Data Ownership
Data owner - legally recognized, accountable for proper data protection; liable.
Sets policy and approved procedures.

Data classification roles:
- Data Subject - such as customer
- Data Custodian - possesses data at a point in time (takes phone call), not data owner
- Data Processor
- Data Controller - responsible for backups and protection
- Data Protection Officer (DPO) - Under article 37 of GDPR is responsible for educating the company and its employees about compliance, training staff involved in data processing, and conducting regular security audits. Also serves as the point of contact between the company and any Supervisory Authorities (SAs) that oversee activities related to data.

Data Lifecycle - Generation, Processing, Storage, Retention, Disposition (the right to be forgotten), Disposal.

### Cross Border Data Requirements
Most laws and regulations only protect data of their citizens. Different laws of different countries may not agree in all the cases.

General laws (GDPR). Industry-specific laws (HIPAA).

Even if an organization outsources the processing and storage of its data, the accountability for the protection of the data remains [primarily] with the data owner, not the processor.

Treaties:
- GDPR in Europe, and also many other countries GDPR-compliant
- Safe Harbor, Privacy Shield - validation
- GDPR-compliance: Binding Corporate Rules (BCP) and Standard Contractual Clauses (SCC)

Cloud and Third Party worries:
- Deletetion of data in the Cloud: bit splitting, crypto-erasure
- Data Ownership: ownership and policies
- Backups: disaster recovery - location and encryption
- Test data for 3rd party
- Intellectual property when code written by 3rd party - Jurisdiction (ownership of IP for outsourced functions, dispute resolution agreements, Non-disclosure Agreements NDA)

## Data and Software Protection Requirements
Documentation benefits:
- Baseline
- Compliance measure
- Consistency
- Ensure items are not forgotten
- Standardized documentation format
- Requirements Traceability Matrix (RTM)
  -- tracking
  -- status

Documentation: version control, ownership, access control.

Software Protection:
- Authentication (distribution, patches)
- Digital Signatures
- Shrink-wrap
- Watermarks

What to document:
- Risk, Threat and Vulnerability Assessments
- Assumptions
- Reasons for choice of controls (considered alternatives)

### Data Protection Controls
Controls are selected to address risk:
- Identify risk
- Select most appropriate control

Control Selection Criteria = Cost of control to implement, operate and maintain.
Effects on performance, legal obligations, integration.

Data Protection Controls - in all forms, in all places, at all times.
Often done by encryption and deletion (crypto erasure = crypto shredding, defensible destruction).

User Consent:
- opt-in or opt-out (such as cookies)
- right to be forgotten (erase or anonymize)
- Privacy policy - always in place; what data is collected, why and what it is used for

#### Data Retention
Legal requirements (ability to retrieve), business needs, historical/cultural aspects.

### Data Protection
Anonymization:
- Tokenization
- Obfuscation
- Randomization - irrecoverable
- Pseudo-randomization - recoverable

### Third Party Agreements
Software development:
- Ownership of source code
- Escrow - if developer is unable to provide support then purcharser can obtain source code from a trusted party

Support:
- Software
- Security

Storage (cloud). Processing (cloud). Distaster recovery.

Infrastructure security - suppliers should not be a single point of failure:
- physical security (fire, access, power)
- hardware disposal
- transportation

Legal considerations:
- Jurisdiction (enforcement, dispute)
- Protection of IP
- Patents
- Location of data
- Clearance of staff

Managed Security Service Providers
- appoint Liaison
- Non-disclosure agreements (NDAs)
- clear communications channels
- escalation procedures

#### Contract and Statement of Work
Well written contract often prevents misunderstandings and expensive changes.

- Document all functionality and security requirements.
- Define terms.
- Set Key Performance Indicators (KPI) - hours of work, support staff.
- Security - initially included Request for Proposal (RFP), addressed in RFP Response, included in Contract and actually delivered.
- Compliance
  -- such as PCI-DSS or PA-DSS for payment cards
  -- Federal Information Security Management Act (FISMA) or other governmental compliance
  -- ISO/IEC 27001 certification
  -- Secure Development Lifecycle methodology
  -- Certified staff
- Use only secure components (tested and proven) - FIPS 140-2, FIPS 140-3

#### Quality control
Review products to ensure that they are delivered according to the document specifications.
Warranty and ongoing support.

#### Audit and Compliance
- Right to audit (by me)
- Third party audits (by trusted 3rd party) - SSAE 18, SSAE 20 standards
  -- SOC 1 report - financial strength
  -- SOC 2 report - operational report, how they are following policies and security procedures
  -- SOC 3 report - high-level summary
  -- Point-of-time - Type I audit
  -- Period-of-time - Type II audit (for six months)
