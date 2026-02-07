Project: Multi-Asset Vulnerability Assessment
Tools: Tenable Nessus Essentials, Nmap

Environment: Mixed-OS Home Lab Network (Linux/QNAP, Windows, IoT)

1. Project Overview
This repository documents the vulnerability management lifecycle across a segmented network environment. The goal is to identify security flaws in different classes of devices (Storage, Compute, Network), prioritize them based on CVSS scores, and apply vendor-specific hardening.

2. Asset Assessments
🟢 Asset A: Network Attached Storage (QNAP NAS)
Status: ✅ Complete | Risk Level: Low-Medium

Device Role: Centralized file storage and backup server.

Scan Type: Credentialed Advanced Scan.

Key Findings:

SMB Signing Disabled: Permitted unauthenticated MitM attacks.

SSL Trust Issues: Default self-signed certificates triggered trust warnings.

Remediation: Enforced SMBv3 signing and deployed Let's Encrypt certificates.

📄 View Full Analysis (Link this to your case study)

🟡 Asset B: Windows Workstation (Windows 10/11)
Status: 🚧 In Progress

Device Role: Primary workstation and virtualization host.

Scan Focus: Patch management and unquoted service paths.

Notes: Currently configuring credentialed access for deep scanning.

🔵 Asset C: Network Infrastructure (Router/Switch)
Status: 📅 Planned

Device Role: Network gateway and firewall.

Scan Focus: Open ports, weak SSH ciphers, and firmware vulnerabilities.
