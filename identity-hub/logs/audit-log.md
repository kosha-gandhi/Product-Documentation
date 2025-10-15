# Audit Log

In Cymmetri, the Audit Logs serve as a vital tool to maintain transparency, accountability, and security in your identity and access setup. This feature meticulously records a detailed account of various activities, ensuring a comprehensive overview of critical events and system changes.

Cymmetri uses a high performance columnar database management system designed for online analytical processing (OLAP). Its architecture and features make it well-suited for maintaining audit logs with strong protection and tamper resistance.

Below are key capabilities that contribute to these aspects:

## **Protection  from alteration of logs data**

Audit logs are critical in any security framework as they provide a reliable trail of all activities within a system. Ensuring that these logs are tamper-proof is vital to maintaining the integrity, accountability, and transparency of the data. Cymmetri, a robust identity management platform, implements several best practices and technological safeguards to ensure that audit logs remain tamper-proof. Here’s how Cymmetri achieves this:&#x20;

### 1. Immutable Log Storage

Cymmetri uses immutable storage for audit logs, meaning once data is written, it cannot be altered or deleted. This ensures that even privileged users or attackers cannot manipulate the logs. The immutable nature of the storage ensures that records are permanent and always available for audits.&#x20;

### 2. Cryptographic Hashing

Each audit log entry in Cymmetri is hashed using cryptographic algorithms, such as SHA-256, before being written to the storage. Hashing creates a unique digital fingerprint of the log entry, making any changes immediately detectable. If the contents of an entry were altered in any way, the hash would no longer match, thus providing tamper-evident logs.&#x20;

### 3. Chain-Based Logging

To add an extra layer of tamper-proofing, Cymmetri leverages chain technology for audit logs. Each log entry is chained to the previous one using cryptographic hashes. This makes it impossible to alter any individual log without breaking the entire chain. chain ensures both immutability and accountability since every change or addition to the log becomes part of a transparent, verifiable sequence.&#x20;

### 4. Role-Based Access Control (RBAC)

Cymmetri strictly enforces role-based access controls to restrict who can view and interact with the audit logs. Only authorized personnel have the rights to access the logs, and the system records all accesses, creating an additional layer of oversight. This minimizes the risk of tampering from internal threats or misconfigurations.&#x20;

### 5. Logging Redundancy and Backup

Cymmetri ensures that audit logs are stored in multiple secure locations using distributed databases or cloud storage. This redundancy guarantees that even if one storage instance is compromised, the logs in other locations remain intact. Regular backups further protect the integrity of logs by ensuring that a historical record is always available.&#x20;

### 6. Time-Stamping

Each audit log entry is time-stamped with a high degree of precision to ensure traceability and integrity. The timestamps are included in the cryptographic hashes, making it impossible to modify both the content and the timing of the log entries. This creates a reliable chain of events that can be used to track down and investigate suspicious activities.

&#x20;Cymmetri’s tamper-proof audit logs combine state-of-the-art technologies like cryptographic hashing, immutable storage, and chain to ensure that the integrity of the audit trail remains intact. With features like RBAC, redundancy, time-stamping, and real- monitoring, Cymmetri offers a highly secure logging framework that prevents any unauthorized modifications, ensuring full accountability across its systems.

For administrators looking to review system-related logs in Cymmetri, the process is simple. Just head to the "Audit Logs" tab within the Logs section. Here, you'll find a wealth of information, covering everything from user logins to requests for accessing applications.

### Audit References

Cymmetri Audit Log maintains all events processed via Cymmetri. The events are tracked based on per object event log as per the Cymmetri logging framework. Events that become part of the the log are-

1. Human driven events processed by the system. Example- a Cymmetri Admin changing an application configuration.&#x20;
2. Scheduled events processed by the system. Example- Deprovisioning job to disable Cymmetri users.
3. Events triggering associated processes as set up in the system. Example- Authentication service will verify the authentication rule to check for Passwordless or MFA based login journey.&#x20;

Cymmetri goes the extra mile by capturing each and every system event, offering administrators a thorough understanding of what's happening within the platform.

<figure><img src="../../.gitbook/assets/image (436).png" alt=""><figcaption></figcaption></figure>

For a closer look at a specific log entry, administrators can click on the eye icon next to it. This action provides a detailed response, offering insights into the exact activities that took place.

<figure><img src="../../.gitbook/assets/image (437).png" alt=""><figcaption></figcaption></figure>

The admin can also filter the logs based on:

1. The actor who performed the event
2. The performed event
3. Start and end date of the events&#x20;
4. Target and target type
5. Status of the event - all, success, and failed

<figure><img src="../../.gitbook/assets/image (438).png" alt=""><figcaption></figcaption></figure>

Cymmetri provides a reference view for the changes occurred during an audit event.

<figure><img src="../../.gitbook/assets/image (84).png" alt=""><figcaption><p>Artefact - Audit log indicating a value updated in the log with time timestamp</p></figcaption></figure>



In essence, Cymmetri's Audit Logs empower administrators with the tools they need to keep a close eye on system activities, ensuring a secure and well-documented identity and access management environment.
