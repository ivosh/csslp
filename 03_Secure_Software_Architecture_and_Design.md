# 3. Secure Software Architecture and Design

Software must be designed with the understanding that it WILL be attacked.
The software designed should be familiar with the various vectors and common threats to software.

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

There are many different architectural models used to implement software. Each model has advantages and disadvantages, and the risks must be identified and addressed.

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

### The Cloud
"Cloud-first" strategy. But there is no 'one' cloud - there are many different implementations, each with their own security challenges.

"Cloud computing" is a model for enabling ubiquitous convenient, on-demand network access to a shared pool of configurable computing resources (ex: networks, computing, storage, applications, services) then can be rapidly provisiond and released with minimal management effort or service provider interaction. [NIST SP800-145]

The cloud is an excellent architecture for many organizations. Each cloud solution has unique security concerns. Security requirements must be included in contracts and service level agreements.

Essential characteristics:
  * on-deman self-service
  * broad network access
  * resource pooling
  * rapid elasticity
  * measured service (pay for what we use)

Cloud implementations:
  * software as a service (SaaS)
  * platform as a service (PaaS)
  * infrastructure as a service (IaaS)

Cloud implementations:
  * public cloud
  * private cloud (on-premises or remote)
  * community cloud (universities, government...)
  * hybrid cloud

Migration to the cloud:
  * move from CapEx (capital expenditure) to OpEx (operational expenditure); especially related to spikes in usage
  * availability of skilled staff
  * time to delivery
  * scalability
  * virtualization (=> flexibility and isolation)
  * reduced risk (backups, compliance, disaster recovery)

Advantages:
  * everyone works from the same software
  * patch management
  * efficiency
  * environmental footprint (HVAC, power plant, backup power...)
  * centralized administration
  * cheaper end-point equipment (economies of scale)

Risks:
  * cloud provider failure
  * cross-border data laws (GDPR)
  * loss of direct control over data
  * encryption keys
  * retired equipment => policies and procedures on secure destruction
  * leaving the cloud (data format, data volume, portability)

#### Mobile Applications
Applications designed to operate on mobile devices (smartphones, tablets...). The risk associated with mobile applications starts with the platform itself - as software designers we often have no control over the security of the device (=> build the app which is secure itself).

Mobile applications make the internet much more usable for everyone. Risks must be identified and mitigated.

Mobile Top 10 from OWASP
 * Improper Platform Usage: misuse of: TouchID, permissions, keychain
 * Insecure Data Storage: insecure data storage and leakage
 * Insecure Communication: poor handshaking, incorrect TLS/SSL versions, cleartext
 * Insecure Authentication: failure to identify user, weak session management
 * Insufficient Cryptography: poor implementation (weak, old)
 * Insecure Authorization: authorization decisions on client side
 * Client Code Quality: buffer overflow, format string vulnerabilities
 * Code Tampering: binary patching, memory modification
 * Reverse Engineering: analysis of core binary
 * Extraneous Functionality: hidden backdoors, breach internal security controls

Mobile Code Vulnerabilities [NDIS SP800-28 Rev2]
 * Active content (triggered automatically): pdf documents, java applets, ActiveX controls, Word macros, Flash and Shockwave media files
 * Untrusted software
 * Remote execution (ex: games have backdoors)
 * Unstructured and unverified content

Mobile Risk Safeguards:
 * Policies
 * Evaluated technology (use CYOD instead of BYOD)
 * Security audit
 * Version control and patch management
 * Isolation (sandbox)
 * Minimum functionality

Technical controls:
 * Filters (firewalls)
 * Sandboxing
 * Signatures of trusted source
 * Proofs of code properties (source code has not been altered)


## Design Secure Interfaces

### Interfaces
Interfaces have become an important attack vector against software components and modules.

Systen interfaces provide many benefits and numerous risks to the security of the application and its data.
Security of the network interfaces needs to be designed into the application.

Networking enables collaboration and sharing but also rasis the risk:
  * Interception and manipulation of data, including exposure of sensitive information
  * Loss of availability of critical data
  * Sharing and spread of malware

*Chained exploits* happen when a system is compromised and used as a foothold for attacking other networked systems.

*Trusted Path* is a strictly controlled interface, such as security and management interfaces used to monitor and perform administrative functions. Access must be designed into the solution, including audit/inspection hooks.

*Out of band* communication is a communication on a different band or channel than the one normal one. Required for monitoring, sensitive data, to prevent traffic analysis, to ensure confidentialy and integrity. Out of band could be set up on an alternate channel, via manual process, via encryption keys (DH, ECDH), negotiations.

Secure communications between systems requires:
 * Establishing trust between the parties
 * The exchange of keys to support encryption

#### Encryption Key Exchange
 * Diffie-Hellman key negotiation
 * RSA and ECC certificates
 * Internet Protocol Security (IPSec) - uses security association to establish secure communication

#### Protocols
Protocol = an agreed-on format for communication. Various protocol for various purposes (TCP, UDP, RTP - packet loss concealment, jitter).

Secure remote access. Protection from unauthorized access or configuration.

Consistency of data format: conversion to common language or encoding, error codes, file layouts, field definitions.

State = the condition an entity is in at a point in time. State can change. State needs to stay secure (communication between two secure systems must be over secured interface): policy and preservation of state.

Protocol choice:
  * resistant to data manipulation
  * encryption to protect data
  * entity authentication

Weak protocols these days which should be prohibited by policies and standards:
  * SSL
  * TSL v1.1
  * POP3
  * MD5
  * SHA1
  * SNMP v1 and v2c

*Application Program Interface* (APIs) are software building blocks (routines, protocols, tools) used as interfaces between various software components (ex: embed a map feature into a website). APIs enable developers to easily and quickly build code with incredible functionality.
The risks are:
  * false APIs
  * APIs using older code or weak encryption
  * false certificates
  * changes to functionality
  * insecure endpoints


#### Log Management
Logs shall be protected as they may contain sensitive information. They are required for legal compliance and management. Integrity may be required for legal issues and investigations (forensics), such as via Write-once Read-Many system, hashing, encryption.

Differentiate debug and audit messages. Non-verbose error messages, especially if they are returned to the client.

Log critical events - who, what, when.

#### Dependencies

Network of systems provides many advantages and introduces new risks: result of bad input (upstream liability) and result of bad output (downstream liability).

Communication channels should be monitored and managed.

Interface layers:
  * network
  * utilities
  * middleware
  * sub-processes
  * users

Upstream Liabilities (my system depends on an upstream system which sends me data):
  * invalid input
  * duplicated data
  * incomplete data
  * => input validation (allowable values, range of values, completeness of input)
  * => integrity (hash, sequence numbers)
  * => confidentiality (encryption, anonymization)
  * => secure access controls, especially for remote access

Downstream Liability (my system sends data to a downstream system):
  * infect other systems
  * unauthorized data sharing (DRM)

Interface Connectivity:
  * Bluetooth
  * RFID
  * NFC
  * 802.11

Interface Communication Risks:
  * Loss of connectivity
  * Unauthorized access
  * Accuracy of data (noise)
  * Jamming (interference)

Managing a Network Channel:
  * Procedures for approval for establishing the connection (CoC)
  * Process to monitor the channel and report on any problems
  * Defined process for disconnecting (do not leave half-open connection)
  * Encryption (for access control, authentication, confidentiality, proof of origin). Challenge is key management.



## Design and Evaluate Software Security Architecture

Concepts:
  * Build security into every component of the system: OS, utilities, networks, databases, middleware, applications, endpoints, interfaces
  * Mature design process in the organization: enterprise-wide. Choose one methodology and apply it consistently with continuous improvement.
  * System's design must address the requirements for security and efficient functionality and security.
  * Good practices include designing solutons that will reduct project problems and leverage known solutions.
 
Benefits of secure design:
  * control effectiveness
  * reduced costs for controls
  * better alignment with business and security needs (instead of hindering operations)
  * preparation and planning leads to fewer errors or re-work

Reusable Secure Design:
  * Many security solutions are already available for use by the systems and security architects
  * Prevents introducing new errors
  * Already proven technology and solutions
  * More supportive of audit
  * Based on commonly accepted practices
 
 Control Selection
   * Influenced by sensitivity and criticality (~ availability) of data
   * Influenced by sensitivity and criticality of system
   * Controls may be based on common standards and templates (NIST, PCI-DSS, COBIT)
   * Controls may be tailored to address unique requirements for each system

Design Documentation
  * in a consistent format across the organization
    * easier to maintain (version control)
    * easier to reference and read
    * easier to share with other integrated systems
  * should be kept up-to-date (as-designed vs as-built => update the documentation)
  * kept under version control
  * readily accessible

 
### Operating System Security
 * Isolation between security kernel and other less important functions - ring protection (layers)
 * Patching
 * Choice of Operating System: reliability, open source vs proprietary
 * Utilities - restrictions on access to privileged utilities
 * Use of trusted products (fake drivers, utilities, processes with back doors and compromises) => signed

### Network Security
 * Isolation (microsegmentation, VLANs, DMZ, Extranet...)
 * Layered Network Defense
   * avoid single points of failure (firewall, administrator) or compromise (wireless router)
   * proxies
   * firewalls
   * WAFs
   * IDS/IPS
   * redundancy

### Power and Environmental Controls
  * Uninterruptible Power Supply (UPS) - batteries, generators
  * Surge protectors
  * Heating, Ventilation and Air Conditioning (HVAC) - capacity
    * Humidity and temperature sensors - rapid changes can cause corrosion or electrostatic shock
  * Rack space
  * Physical access controls (data center)

### Credential Management
