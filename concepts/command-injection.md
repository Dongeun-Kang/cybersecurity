# Command Injection

## Overview

Command Injection is a security vulnerability that allows an attacker to execute arbitrary operating system commands on a server. This vulnerability occurs when an application passes user-controlled input directly to a system shell or command interpreter without proper validation or sanitization.

Attackers can exploit this vulnerability to gain control over the server, access sensitive information, or perform unauthorized actions.

---

## Vulnerability

The vulnerability occurs when user input is used as part of a system command without proper validation. If the application constructs commands dynamically using external input, attackers may inject additional commands into the execution flow.

For example, an application may execute a system command to perform network operations or file management tasks. If input is not properly validated, malicious commands may be appended to the intended command.

---

## Exploitation Techniques

Attackers may exploit Command Injection vulnerabilities using various techniques, including:

* Injecting additional commands into application input fields
* Using command separators to execute multiple commands
* Leveraging shell metacharacters to alter command execution
* Executing system utilities available on the target environment
* Accessing system information or modifying system files

Common command separators include characters such as:

```text id="sep1"
;
```

```text id="sep2"
&&
```

```text id="sep3"
|
```

These characters allow attackers to chain commands or execute unintended operations.

---

## Common Target Actions

Attackers may attempt to perform actions such as:

* Retrieving system information
* Reading or modifying files
* Creating or deleting system resources
* Establishing remote connections
* Executing malicious programs

The specific actions depend on the privileges of the application and the available system commands.

---

## Impact

Successful exploitation of a Command Injection vulnerability may lead to:

* Unauthorized command execution on the server
* Disclosure of sensitive system information
* Modification or deletion of files
* Service disruption or system compromise
* Further exploitation of the system

The severity of the impact depends on the permissions of the affected application and the system configuration.

---

## Mitigation

Recommended mitigation measures include:

* Validate and sanitize all user input
* Avoid passing user input directly to system commands
* Use parameterized or predefined command execution methods
* Implement proper input validation and escaping mechanisms
* Apply the principle of least privilege to application processes

---

## References

Imperva. (n.d.).
*Command Injection.*
https://www.imperva.com/learn/application-security/command-injection/

OWASP Foundation. (n.d.).
*Command Injection.*
https://owasp.org/www-community/attacks/Command_Injection
