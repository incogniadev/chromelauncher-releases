# ChromeLauncher Releases

Public releases repository for ChromeLauncher binaries.

## ⚠️ Important

**This repository is automatically managed** by GitHub Actions from the private source repository.

**Do NOT modify files manually** - all changes will be overwritten on next automated sync.

## Structure

```
.
├── version.json          # Current version metadata
├── 142/                  # Version 142 binaries
│   ├── ChromeLauncher-142-*.exe
│   └── checksums.txt
├── 143/                  # Version 143 binaries
│   └── ...
└── README.md
```

## Usage

### For end users

Download the appropriate executable for your location from the latest version folder.

### For ChromeLauncher auto-update system

The `version.json` file contains metadata for automatic updates:

```json
{
  "latestVersion": 143,
  "releaseDate": "2025-11-15T10:00:00Z",
  "downloads": {
    "Reynosa-PROD": {
      "url": "https://raw.githubusercontent.com/incogniadev/chromelauncher-releases/main/143/ChromeLauncher-143-Reynosa-PROD.exe",
      "sha256": "abc123...",
      "size": 1234567
    }
  },
  "mandatory": false,
  "changelog": "Update flags for Chrome 143"
}
```

## Verification

Verify download integrity using SHA256 checksums in `{version}/checksums.txt`:

```powershell
# PowerShell
$hash = (Get-FileHash .\ChromeLauncher-143-Reynosa-PROD.exe -Algorithm SHA256).Hash
if ($hash -eq (Get-Content .\checksums.txt | Select-String "Reynosa").Line.Split()[0]) {
    Write-Host "Checksum verified"
}
```

## License

Binaries are proprietary software © 2025 Promad Business Solutions.

## Contact

- **Technical issues**: Open issue in private source repository
- **Corporate contact**: ralvarez@promad.com.mx
