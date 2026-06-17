# NVivo 11 Cross-Platform Guide (Windows ↔ macOS)

A practical guide for students and researchers using **NVivo 11** across **Windows and macOS** environments.

This repository documents common setup procedures, project conversion workflows, known compatibility issues, and solutions for exporting projects between platforms.

---

## Overview

NVivo 11 stores projects in different formats depending on the operating system:

- **Windows:** `.nvp`
- **macOS:** `.nvpx`

> **Important:** Projects cannot be transferred by simply renaming file extensions. Always use NVivo's built-in conversion tools.

---

## Supported Versions

| Component | Status | Notes |
|------------|--------|-------|
| NVivo 11 for Windows | ✅ Supported | Recommended master project platform |
| NVivo 11 for Mac | ⚠️ Limited Support | Legacy software |
| Windows 10 | ✅ Supported | Tested |
| Windows 11 | ✅ Supported | Requires .NET and TLS configuration |
| macOS Monterey (12) | ⚠️ Partial Support | Use Mac OS Extended (Journaled) storage when possible |
| macOS Ventura (13) | ⚠️ Limited Support | APFS-related issues reported |
| macOS Sonoma (14) | ⚠️ Partial Support | Frequent compatibility issues |
| macOS Sequoia (15) | ⚠️ Partial Support | Unsupported legacy software |
| macOS Tahoe (26) | ❌ Not Supported | Currently incompatible |

> **Note:** NVivo 11 for Mac has limited support on newer macOS versions using APFS.

---

## Requirements

### Windows

- NVivo 11 for [Windows](https://ruppedukh-my.sharepoint.com/:f:/g/personal/thoeun_pisethta_2821_rupp_edu_kh/IgBfXd84yREFQ4lynyFpR5uZAbGsHVm3i5jnUchvOwXetEA?e=qOXyf9)
- .NET Framework 3.5 enabled
- .NET Framework 4.x installed
- TLS 1.2 enabled
- Administrator privileges

### macOS

- NVivo 11 for [Mac](https://ruppedukh-my.sharepoint.com/:f:/g/personal/thoeun_pisethta_2821_rupp_edu_kh/IgBfXd84yREFQ4lynyFpR5uZAbGsHVm3i5jnUchvOwXetEA?e=qOXyf9)
- Storage formatted as **Mac OS Extended (Journaled)** when possible
- Sufficient free disk space

---

## Exporting a Project from Windows to macOS

1. Open the original `.nvp` project in NVivo for Windows.

2. Navigate to:

   ```text
   File → Clone Project → Export to Mac Version
   ```

3. Wait for the export process to complete.

4. Transfer the generated `.nvpx` file to the Mac.

5. Open the project using NVivo 11 for Mac.

> Do not interrupt the export process.

### Screenshot

```markdown
![Export to Windows Version](<img width="623" height="346" alt="Image" src="https://github.com/user-attachments/assets/e1f5e40a-9926-432d-9eb2-3e968338decd" />)
```

## Common Issues

### RuB.exe Error During Export

The `RuB.exe` utility is responsible for converting projects between Windows and macOS.

Possible causes:

- .NET Framework 3.5 is disabled
- TLS 1.2 is disabled
- Windows Security blocks the conversion process
- Project corruption
- Version mismatch between NVivo installations

### Screenshot

```markdown
![RuB.exe Error](./screenshots/rub-error.png)
```

---

### Failed to Open Project

Error message:

> "This project did not close successfully the last time it was open."

Possible causes:

- Incomplete export process
- Corrupted transfer
- Unsupported APFS storage
- NVivo crash during conversion

### Screenshot

```markdown
![Project Recovery Error](./screenshots/project-recovery-error.png)
```

---

### APFS Storage Error

Error message:

> "Cannot open or save projects on disk 'Macintosh HD'. The disk has an unsupported format (APFS) that prevents NVivo from saving changes."

### Screenshot

```markdown
![APFS Error](./screenshots/mac-apfs-error.png)
```

---

## Troubleshooting

### Enable .NET Framework 3.5

Press `Win + R` and run:

```text
optionalfeatures
```

Enable:

- .NET Framework 3.5 (includes .NET 2.0 and 3.0)
- .NET Framework 4.x Advanced Services

### Screenshot

```markdown
![Enable .NET Framework](./screenshots/optionalfeatures-dotnet.png)
```

---

### Enable TLS 1.2

Press `Win + R` and run:

```text
inetcpl.cpl
```

Navigate to:

```text
Advanced → Security → Use TLS 1.2
```

### Screenshot

```markdown
![Enable TLS 1.2](./screenshots/tls-12.png)
```

---

### Configure .NET Registry Settings

Open Registry Editor:

```text
regedit
```

Add the following DWORD values and set them to `1`:

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319

SchUseStrongCrypto
SystemDefaultTlsVersions
```

Repeat for:

```text
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319
```

Restart Windows after making changes.

### Screenshot

```markdown
![Registry Configuration](./screenshots/registry-strongcrypto.png)
```

---

## Collaboration Workflow for Research Teams

Recommended workflow:

1. Create a master project.
2. Define a shared node structure.
3. Distribute copies of the project to team members.
4. Each member codes different interview transcripts.
5. Merge projects into a single master project.
6. Verify coding references after merging.

> Always share the complete NVivo project file, not only the interview transcripts.

---

## Best Practices

- Back up projects before conversion.
- Avoid cloud-sync folders during export.
- Use identical NVivo versions across all devices.
- Test project conversion using a small sample project first.
- Maintain a master project on one primary device.

---

## Contributors

 - [Thoeun Pisethta](https://github.com/Pheng-AN)