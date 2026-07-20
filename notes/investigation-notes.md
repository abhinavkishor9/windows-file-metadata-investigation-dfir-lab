# Investigation Notes

## Lab Summary

This investigation focused on analyzing Windows file metadata using native Windows artifacts. A sample document was created, modified, and examined to understand how metadata changes throughout a file's lifecycle. File integrity was further validated using SHA256 hashing.

---

## Analyst Methodology

The investigation followed a structured DFIR workflow:

1. Create a sample investigation file.
2. Record initial metadata.
3. Modify the file contents.
4. Compare metadata before and after modification.
5. Validate timestamps using PowerShell.
6. Calculate SHA256 hash.
7. Correlate metadata with file activity.
8. Document investigative findings.

---

## Investigation Scenario

A user believes an important document was altered.

The investigation aimed to determine:

- Original creation time
- Modification time
- Last access time
- File integrity
- Whether metadata supported the reported activity

---

## Evidence Collected

### Evidence 1 – Windows File Properties

Collected:

- Creation Time
- Modified Time
- Last Access Time
- File Size

Finding:

Provided the initial metadata baseline.

---

### Evidence 2 – Modified File

After editing the document:

- Created timestamp remained unchanged.
- Modified timestamp updated.
- File size increased.

Finding:

Confirmed file content had been changed.

---

### Evidence 3 – PowerShell Metadata

Command Used

```
Get-Item InvestigationNotes.txt
```

Collected:

- CreationTime
- LastWriteTime
- LastAccessTime

Finding:

PowerShell validated Windows Explorer metadata.

---

### Evidence 4 – SHA256 Hash

Command Used

```
Get-FileHash InvestigationNotes.txt
```

Collected:

- SHA256 hash

Finding:

Generated a unique fingerprint for the file.

---

## DFIR Analysis

The metadata accurately reflected the file lifecycle.

Evidence demonstrated:

- File creation
- File modification
- Metadata validation
- Integrity verification

PowerShell and Windows Explorer produced consistent forensic evidence.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Collection | Data from Local System | T1005 |
| Discovery | File and Directory Discovery | T1083 |

---

## Analyst Observations

- Created timestamp remained constant throughout the investigation.
- File modification updated the Last Modified timestamp as expected.
- PowerShell confirmed metadata obtained from Windows Explorer.
- SHA256 hashing provided reliable file integrity verification.
- Metadata and hashing together produced a complete forensic picture of file activity.

---

## Conclusion

The investigation demonstrated how Windows file metadata and cryptographic hashes can be used to reconstruct file activity and validate evidence. Native Windows forensic artifacts provided sufficient information to understand the document lifecycle without requiring third-party forensic tools.
