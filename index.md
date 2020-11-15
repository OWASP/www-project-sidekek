---

layout: col-sidebar
title: OWASP SideKEK
tags: SideKEK master key
level: 2
type: code
pitch: Simple tool to protect cryptographic master keys (key encryption keys, KEKs) in a way that is resistant to some of the most common remote file exfiltration attacks.

---

SideKEK provides inexpensive means to protect cryptographic master keys (key encryption keys, KEKs) in a way that is resistant to some of the most common remote file exfiltration attacks.

## Introduction

Development teams often have to store sensitive information encrypted with a series of hierarchical encryption keys culminating with a Key Encryption Key (KEK). This key has to be stored
somewhere, and the best place for it is an HSM. However, in some projects HSM is not available, and KEKs have to stored in the local file system, where they can fall prey to 
a number of possible file exfiltration vulnerabilities (Path Traversal, XXE, LFI, etc).

SideKEK is a tool that helps secure KEKs in such cases.

It is a small Java library that stores them in a local file systems in a way that is resistant to most file exfiltration methods. 
This is done in such a way that the application can retrieve encryption keys easily, but the attacker would need to achieve Remote Code Execution (RCE) privileges on the system 
to be able to do the same (at which point HSM could become insecure as well).

If this approach fits the needs of your product feel free to use the library and modify it to your needs. We also welcome contributions, bug fixes, and implementations in other languages.

For more details see our [GitHub repository](https://github.com/OWASP/SideKEK) or reach out to the authors.