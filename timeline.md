# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 09:00 | Created investigation folder | PowerShell |
| 09:03 | Created InvestigationNotes.txt | Notepad |
| 09:05 | Recorded initial metadata | File Properties |
| 09:08 | Modified file contents | Notepad |
| 09:10 | Compared metadata | Windows Properties |
| 09:13 | Validated metadata | PowerShell Get-Item |
| 09:16 | Calculated SHA256 hash | Get-FileHash |
| 09:20 | Correlated findings | Documentation |

---

# Investigation Flow

Investigation Started

↓

File Created

↓

Metadata Recorded

↓

File Modified

↓

Metadata Compared

↓

PowerShell Validation

↓

SHA256 Hash Generated

↓

Evidence Correlated

↓

Investigation Completed

---

# Summary

The investigation successfully reconstructed the lifecycle of a Windows file using MAC Times and SHA256 hashing. Metadata correlation confirmed the sequence of file creation, modification, and validation while demonstrating how native Windows artifacts support forensic investigations.
