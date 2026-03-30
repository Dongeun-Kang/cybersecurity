# Path Traversal (Directory Traversal)

## Overview

Path Traversal, also known as Directory Traversal, is a web security vulnerability that allows attackers to access files and directories outside the intended directory. This vulnerability occurs when an application does not properly validate user-supplied input used to access files on a server.

Attackers can manipulate file path parameters to access restricted files or sensitive system information.

---

## Vulnerability

The vulnerability occurs when a web application uses user input to construct file paths without proper validation or sanitization. By inserting special characters into input fields, attackers can navigate through directories and access files that should not be exposed.

A common technique involves using sequences such as:

```text
../
```

These sequences allow the attacker to move up directory levels and reach files outside the application's intended directory structure.

---

## Exploitation Techniques

Attackers may exploit Path Traversal vulnerabilities using various techniques, including:

* Using directory traversal sequences such as `../`
* Using absolute file paths to directly access system files
* Encoding traversal sequences to bypass input validation (e.g., URL encoding)
* Using double encoding to evade filtering mechanisms
* Appending null byte characters to terminate file paths
* Accessing files located outside the web root directory

These techniques are often used to bypass insufficient validation or filtering controls implemented by the application.

---

## Common Target Files

Attackers may attempt to access sensitive files stored on the server, including:

* System password files
* Application configuration files
* Source code files
* Log files
* Backup files

The specific files targeted depend on the operating system and application environment.

---

## Impact

Successful exploitation of a Path Traversal vulnerability may lead to:

* Unauthorized access to sensitive files
* Exposure of system configuration information
* Disclosure of application source code
* Access to credentials or confidential data
* Information disclosure that may support further attacks

The severity of the impact depends on the permissions of the application and the files accessible on the server.

---

## Mitigation

Recommended mitigation measures include:

* Validate and sanitize all user input
* Restrict file access to specific directories
* Use allowlists for permitted file names
* Implement proper access control mechanisms
* Normalize file paths before processing
* Avoid directly using user input in file system operations

---

## References

JSmon. (2023).
*What is Path Traversal (Directory Traversal)? Ways to exploit, examples and impact.*
https://blogs.jsmon.sh/what-is-path-traversal-directory-traversal-ways-to-exploit-examples-and-impact/

OWASP Foundation. (n.d.).
*Path Traversal.*
https://owasp.org/www-community/attacks/Path_Traversal
