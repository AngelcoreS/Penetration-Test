# <h1>Penetration-Test Report for Rekall Corporation by AngelSecurity LLC</h2>

- Contact Information

Company Name: AngelSecurity, LLC

Contact Name: Angel Perez

Contact Title: Penetration Tester

Contact Phone: 555.224.2411

Contact Email: blue_cyberangel@proton.me


- Document History

Version: 001

Date: 03/07/2024

Author(s): Angel Perez

<h2>Introduction</h2>

- In accordance with Rekall policies, our organization conducts external and internal penetration tests of its networks and systems throughout the year. The purpose of this engagement was to assess the networks’ and systems’ security and identify potential security flaws by utilizing industry-accepted testing methodology and best practices.

For the testing, we focused on the following:

Attempting to determine what system-level vulnerabilities could be discovered and exploited with no prior knowledge of the environment or notification to administrators.
Attempting to exploit vulnerabilities found and access confidential information that may be stored on systems.
Documenting and reporting on all findings.

- Penetration Testing Methodology

Reconnaissance: Passive and active data gathering using tools like Nmap.

Identification of Vulnerabilities and Services: Using tools like Metasploit, hashcat, and Nmap.

Vulnerability Exploitation: Manual and automated exploitation of identified vulnerabilities.

Reporting: Documentation of findings after exploitation.

- Scope
  
Assessment was conducted on predefined IP addresses controlled by Rekall.

- Grading Methodology

Critical: Immediate threat.

High: Indirect threat.

Medium: Partial threat.

Low: No direct threat.

Informational: No threat, but data may be used in future attacks.

- Summary of Strengths

Effective input validation on many input fields.

Effective user access controls on Rekall’s Linux servers.
- Summary of Weaknesses

Several critical vulnerabilities on the TotalRekall website, including sensitive data exposure, command injection, XSS, LFI, and SQL injection.

Weak user passwords.

Outdated services with vulnerabilities on Linux and Windows machines.

Sensitive data exposure via OSINT and public GitHub repositories.

- Vulnerability Overview

Reflected XSS (High)
Affected Pages: Welcome, Memory-Planner
Remediation: Implement input validation.

Stored XSS (Critical)
Affected Page: Comments
Remediation: Implement input validation.

Local File Inclusion (Critical)
Affected Page: Memory Planner
Remediation: Restrict file types allowed in the database.

SQL Injection (Critical)
Affected Page: Login
Remediation: Implement input validation.

Command Injection (Critical)
Affected Page: Networking
Remediation: Implement input validation.

Open Source Data Exposure (High)
Found using OSINT tools.
Remediation: Remove sensitive information from public access.

Multiple Vulnerabilities in Linux Services (Critical)
Affected Hosts: Multiple
Remediation: Upgrade services to the latest versions.

Sudo Security Bypass (Critical)
Exploited weak password for Alice user.
Remediation: Change passwords and enforce security training.

Sensitive Data Exposure on GitHub (Critical)
Public GitHub repository exposed credentials.
Remediation: Remove sensitive data and enforce strong password policies.

FTP Anonymous Login (Critical)
Allowed access to sensitive data.
Remediation: Disable anonymous access or close port 21 if not in use.

SLMail Pop3d Exploit (Critical)
Gained access via vulnerability.
Remediation: Switch to IMAP and close port 110.

Credential Dumping with Kiwi (Medium)
Extracted and cracked weak passwords.
Remediation: Enforce strong password policies and security training.

Weak Password for Admin (Critical)
Compromised Windows server with weak admin password.
Remediation: Enforce strong password policies and security training.

- Conclusion
  
The assessment identified critical and high-severity vulnerabilities that need immediate remediation. Recommendations include implementing input validation, upgrading services, enforcing strong password policies, and providing security training for employees
