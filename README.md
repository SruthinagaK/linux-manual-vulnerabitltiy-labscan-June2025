# 🧪 Linux Vulnerability Scanning Lab Report

## 🎯 Purpose of the Lab
This lab is designed to teach how to identify, simulate, and fix security vulnerabilities in a Linux virtual machine (VM). Using Tenable Vulnerability Management :

- Created a secure Linux VM in a cyber range.
- Scanned it using a DISA/STIG-based template.
- Introduced known vulnerabilities (like Telnet and weak passwords).
- Performed multiple scans to observe and fix issues.

## 🛠️ Lab Setup
- **VM Provisioning**: A Linux VM was created in a cyber range.
- **Scanner Configuration**: Authenticated scans were run using Tenable with internal or cloud scanners.
- **Vulnerability Simulation**: Weak configurations were added (e.g., Telnet, root password).
- **Remediation**: Vulnerabilities were removed step-by-step, with scans after each change.

## 📊 Scan Summary Table

### ✅ Scan 1 [Baseline scan](https://github.com/SruthinagaK/linux-manual-vulnerabitltiy-labscan-June2025/blob/main/Linux-scan-manual-vul-test-June-Naga_Scan%201.pdf)
| Description | Details |
|-------------|---------|
| **Actions Taken** | Created Linux VM and performed initial authenticated scan using DISA/STIG template. |
| **Vulnerabilities Found** | Critical: 3, High: 3, Medium: 15, Low: 2, Info: 61 |
| **Remediation Status** | Baseline vulnerabilities identified before any changes. |

#### ✅ Scan 1 (Baseline): Established the initial security posture of a freshly provisioned Linux VM. Identified multiple critical and high vulnerabilities, including outdated OpenSSL and libcurl packages

### 🧪 Scan 2 [Simulated attack surface](https://github.com/SruthinagaK/linux-manual-vulnerabitltiy-labscan-June2025/blob/main/Linux-scan-manual-vul-test-June-Naga_Scan2.pdf)
| Description | Details |
|-------------|---------|
| **Actions Taken** | Enabled Telnet and root login with default password to simulate vulnerabilities. |
| **Vulnerabilities Found** | Critical: 4, High: 3, Medium: 16, Low: 2, Info: 63 |
| **Remediation Status** | New vulnerabilities (Telnet, root password) introduced for testing. |

### 🧪 Scan 2 (Simulated Attack Surface): Deliberately weakened the system by enabling Telnet and setting an insecure root password. This increased the critical vulnerability count, simulating a real-world misconfiguration scenario.


### 🔧 Scan 3 [Initial remediation](https://github.com/SruthinagaK/linux-manual-vulnerabitltiy-labscan-June2025/blob/main/Linux-scan-manual-vul-test-June-Naga_Scan%203.pdf)
| Description | Details |
|-------------|---------|
| **Actions Taken** | Removed Telnet and changed root password to secure the system. |
| **Vulnerabilities Found** | Critical: 3, High: 3, Medium: 15, Low: 2, Info: 62 |
| **Remediation Status** | Some vulnerabilities removed, others persisted. |

### 🔧 Scan 3 (Initial Remediation): Reversed the insecure changes by removing Telnet and securing root access. This reduced the critical count but left deeper issues like OpenSSL unresolved.

### 🛡️ Scan 4 [Deep remediation](https://github.com/SruthinagaK/linux-manual-vulnerabitltiy-labscan-June2025/blob/main/Linux-scan-manual-vul-test-June-Naga_Scan%204.pdf)
| Description | Details |
|-------------|---------|
| **Actions Taken** | Addressed OpenSSL and other critical vulnerabilities. |
| **Vulnerabilities Found** | Critical: 0, High: 1, Medium: 1, Low: 2, Info: 61 |
| **Remediation Status** | Most critical vulnerabilities resolved. |

### 🛡️ Scan 4 (Deep Remediation): Focused on patching OpenSSL and other core packages. Successfully eliminated all critical vulnerabilities, leaving only one high (libcurl DoS) and one medium (urllib3).

### 🔄 Scan 5 [Final cleanup](https://github.com/SruthinagaK/linux-manual-vulnerabitltiy-labscan-June2025/blob/main/Linux-scan-manual-vul-test-June-Naga_Scan%205.pdf)
| Description | Details |
|-------------|---------|
| **Actions Taken** | Attempting to remediate libcurl 7.81.0 DoS vulnerability (CVE-2024-7264). |
| **Vulnerabilities Found** | Critical: 0, High: 2, Medium: 6, Low: 3, Info: 62 |
| **Remediation Status** | Final scan completed with remaining curl-related issues. |

### 🔄 Scan 5 (Final Cleanup): Targeted remaining curl-related vulnerabilities. While no criticals remained, a few high and medium issues persisted, reflecting the complexity of fully remediating third-party library vulnerabilities.


## ⏱️ Scan Timeline and Vulnerability Summary

| **Scan** | **Start Time** | **End Time** | **Duration** | **Critical** | **High** | **Medium** | **Low** |
|----------|----------------|--------------|--------------|--------------|----------|------------|---------|
| Scan 1 | 06/29/2025 at 7:16 AM | 06/29/2025 at 7:28 AM | 12min | 3 | 3 | 15 | 2 |
| Scan 2 | 06/29/2025 at 7:58 AM | 06/29/2025 at 8:24 AM | 26min | 4 | 3 | 16 | 2 |
| Scan 3 | 06/29/2025 at 8:37 AM | 06/29/2025 at 8:49 AM | 12min | 3 | 3 | 15 | 2 |
| Scan 4 | 06/29/2025 at 9:24 AM | 06/29/2025 at 9:47 AM | 23min | 0 | 1 | 1 | 2 |
| Scan 5 | 06/29/2025 at 11:06 AM | 06/29/2025 at 11:28 AM | 22min | 0 | 2 | 6 | 3 |

---

This repository documents the full lifecycle of vulnerability management: identification, simulation, remediation, and verification.

