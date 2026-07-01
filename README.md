# wapf

This repository stores a backup of the `wenan` copy-scoring optimization skill.

## Backup

- Source folder: `C:\Users\Administrator\.codex\skills\wenan`
- Backup date: 2026-07-01
- Archive SHA256: `a86f008b2e0b38f3457d6a88e82158fa92ac41f1921a706f79e148d0a5528ec8`
- Archive is stored as Base64 split into 27 parts under `archive/base64-parts/`.

## Restore

Download all files named:

`archive/base64-parts/wenan-skill-backup-2026-07-01.zip.b64.part001` through `part027`.

Concatenate them in numeric order into one `.b64` file, then decode Base64 back into a zip file.

PowerShell example:

```powershell
$parts = Get-ChildItem .\archive\base64-parts\wenan-skill-backup-2026-07-01.zip.b64.part* | Sort-Object Name
$b64 = ($parts | ForEach-Object { Get-Content $_ -Raw }) -join ''
[IO.File]::WriteAllBytes('wenan-skill-backup-2026-07-01.zip', [Convert]::FromBase64String($b64))
Get-FileHash .\wenan-skill-backup-2026-07-01.zip -Algorithm SHA256
```

The hash should be:

`a86f008b2e0b38f3457d6a88e82158fa92ac41f1921a706f79e148d0a5528ec8`
