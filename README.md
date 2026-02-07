# Project: Multi-Asset Vulnerability Assessment
**Tools:** Tenable Nessus Essentials, Nmap  
**Environment:** Mixed-OS Home Lab Network (Linux/QNAP, Windows, Network Infrastructure)

## 1. Project Overview
This repository documents the vulnerability management lifecycle across a segmented network environment. The goal is to identify security flaws in different classes of devices (Storage, Compute, Network), prioritize them based on CVSS scores, and apply vendor-specific hardening.

## 2. Asset Assessments

### 🟢 Asset A: Network Attached Storage (QNAP NAS)
**Status:** ✅ Complete | **Risk Level:** Low-Medium
* **Device Role:** Centralized file storage and backup server.
* **Scan Type:** Credentialed Advanced Scan.
* **Date:** February 6, 2026
* **Vulnerability Summary:**
  * **Critical:** 0
  * **High:** 0
  * **Medium:** 4
  * **Low:** 1

**Key Findings:**
1.  **SMB Signing Not Required (CVSS 5.3):** The SMB server did not enforce message signing, allowing for potential Man-in-the-Middle (MitM) attacks.
2.  **SSL Trust Issues (CVSS 6.5):** The device was using a default self-signed certificate, triggering trust errors and preventing identity verification.
3.  **ICMP Timestamp Disclosure (CVSS 2.1):** The host exposed exact system uptime and date information to remote queries.

**Remediation Actions:**
* **SMB Hardening:** Configured Microsoft Networking advanced options to set SMB Signing to "Mandatory."
* **Encryption:** Replaced the default self-signed certificate with a valid Let's Encrypt certificate generated via the QNAP dashboard.
* **Information Control:** Added firewall rules to block ICMP Timestamp requests.

---

### 🟡 Asset B: Windows Workstation (Windows 10/11)
**Status:** 🚧 In Progress
* **Device Role:** Primary workstation and virtualization host.
* **Scan Focus:** Patch management, unquoted service paths, and third-party software vulnerabilities.
* **Current
