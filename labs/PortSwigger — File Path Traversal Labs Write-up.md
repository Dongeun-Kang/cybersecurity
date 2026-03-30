# PortSwigger — File Path Traversal Labs Write-up

## Lab 1 — File path traversal, simple case

### Description

The application retrieves files from the server using a user-controlled parameter without proper validation. This allows direct traversal outside the intended directory.

### Exploit Method

```text
../../../etc/passwd
```

The payload uses directory traversal sequences (`../`) to move outside the web root and access a sensitive system file.

---

## Lab 2 — File path traversal, traversal sequences blocked

### Description

The application attempts to block traversal sequences such as `../` by removing them from user input.

### Exploit Method

```text
....//....//....//etc/passwd
```

The payload bypasses the filter by using alternative traversal patterns that are not properly sanitized.

---

## Lab 3 — File path traversal, absolute path bypass

### Description

The application restricts relative traversal sequences but fails to prevent access to files using absolute file paths.

### Exploit Method

```text
/etc/passwd
```

The payload directly specifies the absolute path of the target file, bypassing relative path restrictions.

---

## Lab 4 — File path traversal, validation bypass

### Description

The application validates user input but performs validation before normalizing the file path, allowing traversal after validation.

### Exploit Method

```text
../../../etc/passwd
```

The payload exploits improper validation order, where traversal sequences are still processed after input checks.

---

## Lab 5 — File path traversal, double URL encoding bypass

### Description

The application blocks traversal sequences but fails to handle double URL encoding correctly.

### Exploit Method

```text
..%252f..%252f..%252fetc/passwd
```

The payload uses double encoding so that decoding occurs after filtering, restoring the traversal sequences.

---

## Lab 6 — File path traversal, null byte bypass

### Description

The application appends a file extension to user input but does not properly handle null byte characters.

### Exploit Method

```text
../../../etc/passwd%00.jpg
```

The null byte terminates the file path string, causing the server to ignore the appended extension and access the target file.

---

## Key Learning Points

* Path traversal vulnerabilities occur due to insufficient input validation.
* Filtering mechanisms can often be bypassed using encoding or alternate path formats.
* Absolute paths and null byte characters can be used to bypass file restrictions.
* Proper normalization and validation of file paths are essential to prevent exploitation.

## Related Concept

- [Path Traversal Concept](../concepts/path-traversal.md)
