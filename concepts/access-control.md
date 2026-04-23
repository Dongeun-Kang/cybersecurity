# Access Control

## Overview

Access Control is a security mechanism that restricts what authenticated users are allowed to do within an application. It ensures that users can only access resources and perform actions that are permitted for their role or privilege level.

Broken Access Control occurs when these restrictions are improperly enforced, allowing users to access unauthorized data or functionality.

---

## Vulnerability

The vulnerability occurs when an application fails to correctly verify whether a user is authorized to perform a specific action or access a particular resource. Even if a user is authenticated, insufficient authorization checks may allow access to restricted content or operations.

Access Control vulnerabilities commonly arise from missing or incorrect permission checks in application logic.

---

## Types of Access Control

### Horizontal Privilege Escalation

Horizontal Privilege Escalation occurs when a user can access resources belonging to another user with the same privilege level.

This may allow attackers to:

* View other users’ personal information
* Access unauthorized records
* Modify or delete data belonging to other users

---

### Vertical Privilege Escalation

Vertical Privilege Escalation occurs when a user gains access to functionality reserved for higher-privileged roles, such as administrators.

This may allow attackers to:

* Access administrative panels
* Modify system settings
* Perform restricted operations

---

### Context-Dependent Access Control

Context-Dependent Access Control refers to restrictions that depend on the current state of the application or workflow.

Improper enforcement of these rules may allow users to perform actions out of sequence or bypass intended restrictions.

---

## Common Attack Scenarios

Attackers may exploit Access Control vulnerabilities through various methods, including:

* Modifying identifiers in URLs or request parameters
* Accessing hidden or restricted endpoints directly
* Manipulating role or privilege values
* Repeating requests to bypass workflow restrictions
* Accessing resources without proper authorization checks

These scenarios depend on how the application validates permissions and enforces authorization rules.

---

## Impact

Successful exploitation of Access Control vulnerabilities may lead to:

* Unauthorized access to sensitive information
* Data modification or deletion
* Exposure of confidential records
* Privilege escalation within the application
* Compromise of system integrity

The severity of the impact depends on the level of access obtained and the criticality of the affected resources.

---

## Mitigation

Recommended mitigation measures include:

* Enforce authorization checks on every request
* Implement role-based access control mechanisms
* Use secure session management practices
* Restrict access to sensitive resources
* Apply the principle of least privilege

These controls help ensure that users can only perform authorized actions.

---

## References

PortSwigger. (n.d.).
*Access control vulnerabilities.*
https://portswigger.net/web-security/access-control

SecureLayer7. (n.d.).
*Understanding Broken Access Control.*
https://blog.securelayer7.net/understanding-broken-access-control/
