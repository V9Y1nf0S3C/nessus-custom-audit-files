### 1. `windows/Check_Windows_OS_and_Role.audit`

Use this script alongside the Auth Scan or just before the HCR scan to verify that you have configured the correct server version and server role. This is a more detailed audit script compared to `Check_WMI_RemoteRegistry_access.audit`.

- **Comprehensive OS Detection:** Accurately distinguishes between various Windows Server editions and versions to assist in compliance and compatibility assessments.
- **Role Classification:** Helps in understanding the server's role, which is crucial for configuring appropriate security policies.

---

### 2. `windows/Check_WMI_RemoteRegistry_access.audit`

Use this script in conjunction with the Auth Scan to ensure that your target server has WMI and Remote Registry access. This is a shorter audit script compared to `windows/Check_Windows_OS_and_Role.audit`.

- **WMI Access Check:** Determines whether WMI is enabled and accessible on the target server.
- **Remote Registry Access Check:** Verifies if Remote Registry is enabled and accessible on the target server.
