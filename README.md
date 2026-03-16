# Apache Struts S2-052 XML Deserialization RCE

This repository demonstrates exploitation of **Apache Struts S2-052 (CVE-2017-9805)** using malicious XML deserialization.

The exploit was developed while solving the **INE eWPTX Practice Range – Struts XML Deserialization RCE lab**.

---

## Vulnerability Overview

Apache Struts REST plugin uses **XStream** to deserialize XML requests.

When the application processes XML with:

Content-Type: application/xml

An attacker can supply a malicious serialized object graph which triggers execution of arbitrary commands via:

java.lang.ProcessBuilder

This results in **Remote Command Execution (RCE)**.

---

## Vulnerable Flow

Client Request
     ↓
Struts REST Plugin
     ↓
XStream XML Deserialization
     ↓
Malicious Object Graph
     ↓
ProcessBuilder.start()
     ↓
Remote Code Execution

---

## Lab Environment

Platform: INE eWPTX Practice Range  
Challenge: Struts XML Deserialization RCE  

---
## Affected Versions

Struts 2.1.6 – 2.3.33
Struts 2.5 – 2.5.12

## Affected Versions

Struts 2.1.6 – 2.3.33
Struts 2.5 – 2.5.12
