# 3. Secure Software Architecture and Design

Software must be designed with the understanding that it WILL be attacked.
The software designed should be familiar with the various attack vectors and common threats to software.

## Categorize Threats to Software Applications

Types of Software:
* Operating system
* Utilities
* Drivers
* Applications
* Application Program Interface (APIs)
* Management plane
  * network (software-defined network)
  * storage (software-defined storage)
  * database (software-defined database)
  * legacy (middleware)

Software is just a part of an integrated system.
* Hardware
* Network
* Databases
* Physical (power, access, tamperproof). Physical security is very important to underpin logical security controls.

### Software Attack Surface
Software attack surface must consider all possible points of attack.

Typical attack surfaces:
* Implementation (vendor accounts, administrator accounts)
* Networks (wireless)
* Unused features
* Connected software (advertising)
* End point devices

#### Internal Software Threats 
* bugs
* flaws
* buffer overflows
* users (accidental, intentional)
* administrators

#### Externnal Software Threats
Human attacks:
* Hackers
* Criminals
* Espionage (APT)

Motivation:
* Financial
* Ego
* Ideology

Advanced Persisten Threats (APTs)
* State Sponsored (majority)
* Criminal organizations
* Professional, highly skilled
* Determined, highly motivated

Web Application Attacks - OWASP Top Ten \[Security Risks\].

Threat Intelligence:
* many sources for attack vectors and techniques
* severity
* mitigation

Malware (malicious software):
* Virus (first infects, then spreads)
* Worm (spreads without infecting)
* Logic bomb (triggers on an event or a date)
* Ransomware (critical infrastructure, healthcare...)
* Trojan horse (doing for example data exfiltration)
* Rootkit (infection in the root level, complete control over the system nearly impossible to detect and eradicate)
* Botnet (robotically controlled network)

Compromise of Operations
* Learning systems and virtual classrooms (via unauthorized entry)
* Social media (compromise of accounts and data)

Supplier Threat
* Failure to provide support (=> single point of failure and compromise)
* Delivery of faulty or insecure products (hardware, software)
* Ownership of intellectual property (=> which jurisdiction in case of dispute)
* Source code versus executable (Escrow)
* Ownership of test data


### Document Security Properties and Constraints

Security Requirements, gathered previously, needs to be addressed with the right solutions. Find the right balance between security and support of business.

Allocation of Controls:
* Based on risk
* Rule: don't pay more to protect something than it is worth
* Caveat: Access to any part of a networked integrated system may result in compromise of the whole system (weak link in the chain, such as unprotected untrusted connections upstream and downstream => zero-trust networks)

#### Common Controls:
* At a single location (power, HVAC, network firewall, physical security)
* At multiple locations (template for system configuration, access control)
* Allocate security requirements to external systems where possible
  * Leverage existing investment
  * Interoperability
  * Consistency
  * Compliance

#### Internal Controls
System-specific controls
* Customized
* Legal compliance
* High risk processes (sensitive data)

#### Document the Controls
Security requirements must be addressed and the chosen solutions documented. The documentation (SSP in many cases) provides the standard/baseline used for later compliance verification and system authorization.

* Each security requirement shall be allocated
  * Requirements Traceability Matrix (RTM)
  * System Security Plan (SSP) - how the security is setup, what are the security controls
  * Contracts with suppliers and third parties - interoperability and security constraints

#### Security Properties
* Confidentiality (privacy) =>
  * encryption (data-at-rest, data-in-use, data-in-transit, data displayed)
  * algorithm - agility
  * tokenization
  * masking/obfuscation
* Integrity =>
  * separation/segregation of duties (for example dual control or mutual exclusivity)
  * logging
  * authorization controls
  * reasonableness checks
  * input validation
* Availability =>
  * redundancy (based on criticality): data storage, networks, critical equipment, staff (administrators, support personnel)
* Monitoring
  * Logging - retention, access
  * Log and activity analysis => SIEM
* Performance
  * quantitional: throughput, transactions, users, bandwidth, storage, CPU
* Training for administrators and users
* Help Desk
* Auditor reports
* Testing
  * Test data
  * Test scripts
  * Test cases (possibly with data and scripts)
* Constraints:
  * Integration with legacy systems, hardware, browsers
  * Legal: data storage or data processing, protection of IPR, logs and records
* Reports:
  * format
  * frequency
  * retention
  * access controls

### Examine Architectural Risk Assessment
Risk Assessment is often done by another team. They need to verify, examine the risk assessment report.

Risk drives controls. Since risk is the justification for controls, an error in the risk assessment can result in the selection of incorrect controls.

Information systems must be designed to operate securely within their real-life environments, not just in a sterile, perfect lab. Risk assessments are used to select appropriate controls and to deliver adequate security, so the risk assessment should be carefully reviewed to ensure it is reliable.

Risk Assessment:
* Scope (the same as the project)
* Thorough
* Realistci
* Complete (all risk vectors examined)
* Review assumptions
* Operating Environment
   * network connectivity
   * network segmentation
   * DMZ or other perimeter network
   * shared database
   * configuration (inexperienced installers)
   * environmental issues (heat/freezing, dust, liquids. expertise of users)
 * Integrated Operations
   * Dependencies (job process flow, dependency on upstream inputs)
   * Input validation (header and trailer records to ensure completeness of the input) 
* Future Developments - Capacity to integrate security that is not currently required but may be necessary if the operating environment changes.



## Design Software Security Architecture
