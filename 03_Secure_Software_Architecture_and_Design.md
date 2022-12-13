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

Security Architecture is concerned with the implementation of controls to protect the operation of a system or buseness process and maintain confidentiality, integrity and availability.

Security Controls:
* Proactive (safeguards) - protect an asset from damage
* Reactive (countermeasures) - counter or respond to an incident

Types of controls (we need all the three following types):
* managerial or administrative
* technical / logical
* physical / environmental (operational)
* compensating = additional control to compensate for or address a weakness or lack of other controls (ex: administrator rights on a system => dual control)

Security Controls:
* Directive (ex: policy - safeguard)
* Deterrent (ex: CCTV - safeguard)
* Preventive (ex: password - safeguard)
* Detective (ex: audit - contermeasure)
* Corrective (ex: fire extinguisher - countermeasure)
* Restoration/recovery (ex: - countermeasure)

### Adequate Security
Security that is commensurate with a risk. Risk can be accepted only by the risk owner (in most cases the asset owner).
Demands and requirements placed on the security IT by the business (risk owner).
Adequate security must be:
 * effective
 * cost-effective
 * justifiable
 * aligned with business needs (goal: secure the business, not the system)

### Security Control Identification and Prioritization
List all security controls:
 * prioritization based on cost, other projects, technology
 * placement of controls (deployment)

Statement of Work - control requirements
 * Deliverable
 * Operation
 * Testing
 * Documentation

### Architecture Based Controls
Architectural Choices - the best solution depends on many factors. Understand the business.
The choice of architecture is often based on preference as all architectures have advantages and disadvantages.

Centralized computing:
 * one point of control (power, management) - also cloud today
 * one point of failure
 * consistency in processes and security
 * inflexibility

Decentralized computing:
 * flexible to business needs
 * less reliance on network connectivity
 * tailored solutions
 * local knowledge
 * inconsistency in processes and security
 * possible duplication of data
 * non-standard applications and tools
 * shadow IT
 * lack of local expertise
 * not suitable especially for small offices

Decentralized Security Risk:
 * consistency in access controls
 * legal compliance
 * monitoring
 * log collecting and deletion

Client Server Architecture
 * originally two-tiered architecture
 * central data storage
 * dependent on network connectivity

Peer to Peer (P2P) Architecture
 * Robust multi-point services
 * Each node may operate as a client and as a server - all nodes may be peers
 * Data replication is a challenge for consistency
 * Grater risk of remote access vulnerabilities 

Message Queuing
 * Synchronous and asynchronous messaging
 * Risk of insertion of bad code

Service Oriented Architecture (SOA)
 * Loose coupling of service available on demand
 * Instead of tight coupling based on pre-defined sequence
 * Provides interface for utilizing (reuse of) existing services (a highway for service functions) => Enterprise Security Bus (ESB)
 * Integration of separately deployed and maintained software components
 * Risk: interoperability and security of protocols

Web Services - protocols
 * UDDI (Universal Description, Discovery and Integration) - directory of available services
 * XML (eXtended Markup Language) - format of data and metadata
 * SOAP (Simple Object Access Protocol) - mechanism to transport data
 * WSDL (Web Service Definition Language) - available services
 * ESB (Enterprise Security Bus) - commonucations path between applications
 * REST (Representational State Transfer) - interoperability between web components


### Web-based Architecture Risk

Rich Internet Applications
 * user interface on client side
 * data manipulation on server side
 * runs inside a web application, ideally in a sandbox
   * isolation
   * control
   * virtualization
   * restrictions
 * risks: anything done at the client can be manipulated by the client
   * input validation => fix the errors when they happen
   * error handling
   * execution on untrusted device
   * remote (arbitrary) code execution: the ability of an attack to remotely access and take control of a victim's machine
   * privilege escalation: attacker may seek to elevate the user's privileges
   * continuos connectivity: makes devices valuable as part of a botnet or other malicious activity (cameras, TVs...)

#### Pervasive Computing
Ubiquitous computing - "every-ware". The use of computing technologies on all types of devices (home furnishings, cars, glasses...). The emerge of IoT.

SCADA (Supervisory Control and Data Acquisition Systems) - ex: monitoring and controling of water and power distribution. In the past connectivity ensured by leased dedicated lines.

Industrial Control Systems (ICS) - ex: building management systems (air conditioning connected to public internet and building management system as well)

Risks:
  * difficulty of patching (long lifespan...)
  * vulnerabilities (Stuxnet worm)
  * IoT - lack of separation between network and functional components (ex: medical devices => restart in the middle of the operation; vehicles - ex: breaks and radio)
  * Wireless communications may be intercepted and modified (=> confidentiality and integrity)
  * Wireless communication may be jammed (=> availability for remote access/administration)
 
The integration of computing devices into everyday devices and processes has created an entirely new risk landscape.
Wireless communications remain a 'soft' target for many attacks.
 
#### Feature-based Risk
Very often the addition of extra features to an application or an service has resulted in new compromises or breaches (new attack vectors).
New feature has not been assessed.
Risk:
  * system compromise
  * data disclosure

Examples:
  * Location-based services (ex: advertising, local attractions, coupons, marketing, tracks employees and company-owned vehicles). Privacy issue: disclose data on user locations and habits.
  * Radio Frequency Identifiers (RFID)
    * track products, devices and people
    * store entity-related data (RFID tag on clothing)
    * ease of use - installation and removal
    * avoid loss of, or interchanged cards (when used for tracking)
  * Near Field Communications (NFC)
    * Wireless, contactless communications between devices in close proximity to another (ex: exchange of files, payment systems)
    * risk: theft of payment data, unknown copying of data from a device
  * Embedded systems
    * Computing process built into a product (ex: automobile)
    * Usually performs a set function
    * Real-time computing (changing road conditions)
    * risk: difficult to patch, long lifespan, remote access
    * Microcontrollers (single purpose computation) ex: embedded medical devices (pacemaker), automotive; ruggedized for environment
  * Firmware - embedded onto ROM or flash
    * may be infected during the manufacturing process
    * need assurance of reputable vendors
  * Field Programmable Gate Arrays (FPGA)
    * may lose configuration if power failure
  * Hardware Platforms
    * Hardware Security Module (HSM)
    * Trusted Platform Module (TPM)
    * side-channel attacks (Spectre, Meltdown - speculative execution) leading to bypass account permissions and memory regions
    * firmware and software updates

#### Trusted Components
Common Criteria
 * Target of Evaluation (ToE)
 * Protection Profile
 * Security Target (security objective), defined by the vendor
 * Security functional requirements, described by the vendor
 * Evaluated assurance level (EAL), nowadays obsolete

#### Cognitive Computing
Mimics human reasoning, based on AI and ML.
  * Signal processing (self-driving cars)
  * Used in control systems. Ex: industrial machinery and operations, automobiles, medical devices, building management systems (HVAC)
  * Risk: incorrect or incomplete input data leads to incorrect result (ex: medical analysis, self-driving vehicles)
