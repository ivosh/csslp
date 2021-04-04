# 1. Core Concepts of Security Design Principles
Security must be designed into: applications, networks, hosts, databases.

## Implementation of Security Concepts
Enforced through the use of Controls:
- Designed
- Developed
- Implemented
- Configured
- Operated
- Improved

Justification for Controls: RISK (tradeoffs).

Types of Controls:
- Managerial/Administrative (policies, audits)
- Technical/Logical (firewalls, IDSs, IPSs)
- Physical/Environmental/Operational (power, heating, ventialtion, air conditioning, patching)

### Security-Conscious Software Development
Deliver a secure working product through the SDLC.

## Confidentiality
Protect sensitive data from improper disclosure (intentional or accidental).
- Privacy
- Secrecy

Overt (obvious) and Covert (hidden, such as timing or storage) channels.

Preservation of Confidentiality
- Masking
- Obfuscation
- Tokenization
- Encryption

## Integrity
Protection of data and processes from accidental or intentional alterations or modifications.
- Accuracy
- Completeness
- Precision
- Reliability

Input validation: format, range, value limits, access levels (RO, RW)

Integrity implementations: symmetric cryptography (HMAC), asymmetric cryptography (digital signature)

Authenticity of: downloads, patches, source, APIs, drivers & utilities, logs, hard drives...

## Availability
Systems, information, networks, personnel and software are available when *required*.

Depends on the criticality of the resource: Fault tolerance, Redundancy, Failover, Backups.

Requirements: Resilience, Error handling, Scalability (elastic).

Reliable Supporting Infrastructure: storage, memory, operating environment (HVAC, dust, liquids, electromagnetic fields).

### Distributed Computing
Remove single point of failure:
- Multiple Operating Locations
- Disaster Recovery Planning

Replication
- Hardware (cluster, terminals)
- Software (backups, operating systems)
- Data (mirrorring, RAID, database shadowing)


## Security Access Design Principles
Access Control is the core of information security (AAA).

Identification
- Accountability (unique ids)
- Associated with activity

### Reference Monitor
Subject (user) tries to gain access to object (resource). Monitors and manages these accesses through ACL/security kernel database. Audit logs.

### Authentication
Validate, verify or prove the identity provided.

Internally or externally.

#### Authentication Methods
- Knowledge - something I know (password, passphrase, rules, PIN, secret questions)
- Ownership - something I have (token, smartcard, key fob, RFID)
- Biometrics - something I am (physiological: fingerprint, palmprint, vein, iris; behavioural: speech, typing, signature dynamics)

Multi-Factor Authentication = combination of two or more (different) authentication methods.

#### Node Authentication Methods
Device authentication - CPU serial number, IP address, MAC address, Key fob.

#### Identity and Access Management (IAM)
Cooperation between Information and System owner.

Implementation Type:
- Single Sign-on (SSO)
- Federated Identity Management (Single Sign-on on the web): SAML, OAuth
- Credentials

#### Credential Management
Changes in user accounts and permissions. Storage of passwords, secret questions, secret keys. Issuance of hardware tokens, smart cards, USB tokens. PKI, OTP, biometrics.
The most desirable target for attackers. Huge risk of compromise, credentials re-issuance is time expensive.

Works well with a lot of people working remotely. Can be managed remotely. Credentials may be re-issued when necessary.
Often provided by a third party - Credential Service Provider (CSP).

Policies and practices to support credential management.

#### Session Management
Clear screen. Clean desk. Timeouts. Invalid access attempts.

## Authorization
To permit authenticated and authorized entities (persons, processes) to perform authorized functions. Enable business operations and functions to operate.

### Entitlements
Granular access controls, often based on group membership.

### Restrictions
Separation (segregation) of duties:
- Mutual exclusivity
- Dual control - multi-party
- Split knowledge (secret sharing)

### Least Privilege
Time-based, Location-based, Role-based access.

### Need to Know
Masking, Obfuscation, Encryption, Substitution (tokenization, bit splitting, pseudo-random), Polyinstantiation.

(Resource/scope/role/permission.)

## Accountability/Auditing
Ability to associate all activity on a system with the entities that were involved. Requires unique identifiers. Legal and Compliance requirements. Provide evidence required for investigations.

Transactions
- Access to sensitive data
- Changes
Administrative functions
- Jobs or process initiation
- System start up or shutdown

Implementations:
- Hashing
- Header and Trailer records
- End of report notice (complete report, empty report)
- Non-repudiation (digital signature, blockchain)

### Logging
Who, when, what, comments - reason.

Log retention - time, volume, protection from access/modification/deletion.

Log Data Collection:
- Point of activity (error, modification, access)
- Analysis (problems, trends)
- Aggregation (Security Information and Event Management Systems - SIEM)

Runtime.
