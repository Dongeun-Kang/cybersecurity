# File Inclusion

## Overview

File Inclusion is a web security vulnerability that occurs when an application dynamically includes files based on user input without proper validation. This vulnerability allows attackers to manipulate file paths and force the application to load unintended files.

File Inclusion vulnerabilities can expose sensitive information or allow execution of malicious code, depending on how the application processes the included file.

---

## Vulnerability

The vulnerability occurs when an application uses user input to determine which file should be included or executed. If the input is not properly validated, attackers can modify the file path to include unauthorized files.

For example, applications may use functions that load files dynamically to display content or templates. When user input is directly used in these functions, attackers may gain access to internal system files or application resources.

---

## Types of File Inclusion

### Local File Inclusion (LFI)

Local File Inclusion occurs when an attacker includes files that exist on the same server as the vulnerable application.

This may allow attackers to:

* Access sensitive system files
* Read configuration files
* Retrieve application source code
* Leverage local files to execute malicious commands

---

### Remote File Inclusion (RFI)

Remote File Inclusion occurs when an attacker includes files hosted on an external server.

This allows attackers to:

* Load malicious files from remote locations
* Execute arbitrary code on the target system
* Establish unauthorized control over the application

---

## Common Attack Scenarios

Attackers may exploit File Inclusion vulnerabilities through various methods, including:

* Manipulating file path parameters
* Using directory traversal sequences to reach sensitive files
* Including log files that contain injected malicious code
* Uploading malicious files and forcing the application to include them
* Accessing system files stored on the server

These scenarios depend on how the application handles file inclusion and user input.

---

## Impact

Successful exploitation of a File Inclusion vulnerability may lead to:

* Unauthorized access to sensitive information
* Exposure of configuration or credential data
* Execution of malicious code on the server
* System compromise or service disruption
* Further exploitation of the application environment

The severity of the impact depends on the permissions of the application and the security controls in place.

---

## Mitigation

Recommended mitigation measures include:

* Validate and sanitize all user input
* Restrict file access to specific directories
* Use allowlists for permitted file names
* Disable remote file inclusion features when not required
* Apply proper access control and least privilege principles

---

## References

Bright Security. (n.d.).
*LFI attack: Real-life attacks and attack examples.*
https://brightsec.com/blog/lfi-attack-real-life-attacks-and-attack-examples/

Inspirisys. (n.d.).
*File Inclusion.*
https://www.inspirisys.com/glossary/file-inclusion
