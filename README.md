# Nessus Custom Audit Files

![Nessus](https://img.shields.io/badge/Nessus-Compatible-green.svg)
![Windows](https://img.shields.io/badge/Windows-Compatible-blue.svg)

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Usage Instructions](#usage-instructions)
- [Audit Scripts Documentation](#audit-scripts-documentation)
  - [1. `windows/Check_Windows_OS_and_Role.audit`](#1-windowscheck_windows_os_and_roleaudit)
    - When to Use
    - Purpose
    - Key Features
  - [2. `windows/Check_WMI_RemoteRegistry_access.audit`](#2-windowscheck_wmi_remoteregistry_accessaudit)
    - When to Use
    - Purpose
    - Key Features
- [Disclaimer](#disclaimer)


---

## Overview

**Nessus Custom Audit Files** is a repository of tailored Nessus audit scripts aimed at streamlining your security assessments. By automating the collection of essential server information, these scripts reduce the need for manual analysis, allowing you to utilize your time more efficiently and maintain a robust security posture.

## Features

- **Automated OS and Role Detection:** Quickly identify Windows server versions and roles within your network.
- **Service Accessibility Checks:** Verify the status of essential services like WMI and Remote Registry.
- **Seamless Nessus Integration:** Easily incorporate custom audit scripts into your existing Nessus scan policies.

## Usage Instructions

1. **Add Audit Scripts to Nessus:**
   - Navigate to your Nessus scan policy.
   - Go to **Compliance > Custom Windows**.
   - Add the desired `*.audit` scripts from this repository to the policy.

2. **Execute the Nessus Scan:**
   - Run the scan targeting the appropriate Windows servers.
   - Ensure that the scan has the necessary permissions to execute the audit scripts.

3. **Review the Results:**
   - Upon completion, analyze the scan results to gain insights into your server configurations and service statuses.

---

## Audit Scripts Documentation

Below are detailed notes for the audit scripts included in the **nessus-custom-audit-files** repository. These scripts are designed to enhance your security assessments by leveraging Nessus to gather necessary information about your servers.

---

### 1. `windows/Check_Windows_OS_and_Role.audit`


#### **When to Use**

Use this script alongside the Auth Scan or just before the HCR scan to verify that you have configured the correct server version and server role. This is a more detailed audit script compared to `Check_WMI_RemoteRegistry_access.audit`.


#### **Purpose**

This audit script retrieves essential information about the Windows operating system and the role of the server within the network. Specifically, it:

- **Windows Version Detection:** Identifies the exact version of Windows running on the target server, such as Windows Server 2025, 2022, 2019, 2016, 2012-R2, or 2012.
- **Server Role Identification:** Determines whether the server functions as a Domain Controller or a Member Server within the network infrastructure.

#### **Key Features**

- **Comprehensive OS Detection:** Accurately distinguishes between various Windows Server editions and versions to assist in compliance and compatibility assessments.
- **Role Classification:** Helps in understanding the server's role, which is crucial for configuring appropriate security policies.

---

### 2. `windows/Check_WMI_RemoteRegistry_access.audit`


#### **When to Use**

Use this script in conjunction with the Auth Scan to ensure that your target server has WMI and Remote Registry access. This is a shorter audit script compared to `windows/Check_Windows_OS_and_Role.audit`.

#### **Purpose**

This audit script assesses the accessibility and status of two critical Windows services: Windows Management Instrumentation (WMI) and Remote Registry. These services are mandatory for the Nessus Policy Compliance Scan (HCR Scan) of Windows servers, so verifying their access is essential to ensure the required prerequisites are in place.

- **WMI Access Check:** Determines whether WMI is enabled and accessible on the target server.
- **Remote Registry Access Check:** Verifies if Remote Registry is enabled and accessible on the target server.

---

## Disclaimer

*Ensure you have proper authorization to perform scans and audits on target systems. Unauthorized scanning may violate organizational policies or legal regulations.*
