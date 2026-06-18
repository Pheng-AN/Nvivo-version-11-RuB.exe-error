# NVivo 11 Cross-Platform Guide (Windows ↔ macOS)

---

## Disclaimer

This repository is an **unofficial community guide** created for **academic and educational purposes only**.

The information provided is based on personal experience using **NVivo 11** across Windows and macOS environments and may not apply to all system configurations.

- These changes may affect your operating system or other applications if performed incorrectly.

```text
Proceed at your own risk.
```

---

### Common Issue

### RuB.exe Error During Import from Macos to Windows

When trying to Import a Project from Macos to Windows

- Navigate to:

   ```text
   File → Open Project → Select .nvpx file → Convert to Windows Project
   ```

Or when trying to Export a Project from Windows to Macos

- Navigate to:

   ```text
   File → Clone Project → Export to Mac Version
   ```

The `RuB.exe` utility is responsible for converting projects between NVivo for Windows and NVivo for Mac.

Possible causes:

- .NET Framework 3.5 is disabled
- TLS 1.2 is disabled
- Windows Security blocks the conversion process
- Project corruption
- Version mismatch between NVivo installations

### Screenshot

<img width="512" height="257" alt="Image" src="https://github.com/user-attachments/assets/3d04b523-ce9d-4f53-9209-6d454121a9a4" />

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

- A licensed installation of NVivo 11 for [Windows](https://ruppedukh-my.sharepoint.com/:f:/g/personal/thoeun_pisethta_2821_rupp_edu_kh/IgBfXd84yREFQ4lynyFpR5uZAbGsHVm3i5jnUchvOwXetEA?e=qOXyf9)
- .NET Framework 3.5 enabled
- .NET Framework 4.x installed
- TLS 1.2 enabled

### macOS

- A licensed installation of NVivo 11 for [Mac](https://ruppedukh-my.sharepoint.com/:f:/g/personal/thoeun_pisethta_2821_rupp_edu_kh/IgBfXd84yREFQ4lynyFpR5uZAbGsHVm3i5jnUchvOwXetEA?e=qOXyf9)
- Storage formatted as **Mac OS Extended (Journaled)** when possible
- Store and open `.nvpx` files from a dedicated partition or external drive formatted as **Mac OS Extended (Journaled)**.

### Tutorial

[Youtube](https://youtu.be/TkgLVC56rlo)

### Screenshot

<img width="864" height="623" alt="Image" src="https://github.com/user-attachments/assets/48e4717a-da99-4314-9cd4-c1e20297fd36" />

---

## Troubleshooting

### Enable .NET Framework 3.5

- Download [.NET](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-10.0.301-windows-x64-installer) For Windows if not yet installed

Press `Win + R` and run:

```text
optionalfeatures
```

Enable:

- .NET Framework 3.5 (includes .NET 2.0 and 3.0)
- .NET Framework 4.x Advanced Services

### Screenshot

<img width="418" height="370" alt="Image" src="https://github.com/user-attachments/assets/f74c67ce-bcbd-4565-a837-8700ca9bd1f6" />

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

<img width="476" height="655" alt="Image" src="https://github.com/user-attachments/assets/28016ab1-a8c2-46d9-ace3-65fd0da51752" />

---

### Configure .NET Registry Settings

Open Registry Editor:

```text
regedit
```

Add the following DWORD (32-bit) values and set them to `1`:

```text
SchUseStrongCrypto
```

### Screenshot

<img width="443" height="251" alt="Image" src="https://github.com/user-attachments/assets/6f5ffbe6-88ca-4a41-8cc9-57167868fb6b" />

Pathname:

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319
```

Repeat for:

```text
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319
```

### Screenshot

<img width="1422" height="731" alt="Image" src="https://github.com/user-attachments/assets/41fe41a4-7013-488e-b777-9578d5a5b94e" />

<img width="1428" height="735" alt="Image" src="https://github.com/user-attachments/assets/90752643-f89e-4736-a838-d647b204c711" />

---

## Restart Windows after making changes.

---

### G.G Successful Conversion Examples

Windows

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d9aa3ba6-dd79-4e4c-8862-dfd1009fc888" />

Macos

<img width="1266" height="761" alt="Image" src="https://github.com/user-attachments/assets/0695f7c8-b4bc-4ee8-8d23-2f03e0b6f9d4" />

---

## Best Practices

- Back up projects before conversion.
- Avoid cloud-sync folders during export.
- Use identical NVivo versions across all devices.
- Test project conversion using a small sample project first.
- Maintain a master project on one primary device (recommend Windows).

---

## Contributors

 - [Thoeun Pisethta](https://github.com/Pheng-AN)
 - [Kouy Pheakdeyoudom](https://github.com/Oudom0987)