# windows-file-metadata-investigation-dfir-lab
## Overview

This Digital Forensics and Incident Response (DFIR) lab demonstrates how Windows file metadata can be analyzed to reconstruct file activity using native Windows forensic artifacts.

Rather than examining the file contents, this investigation focuses on metadata such as creation time, modification time, last access time, ownership, and cryptographic hashes to determine how a file has changed over time.

---

# Executive Summary

This investigation demonstrates how file metadata serves as valuable forensic evidence during endpoint investigations. Using Windows Explorer, PowerShell, and native hashing utilities, a sample document was created, modified, analyzed, and validated to reconstruct its lifecycle.

The investigation highlights how metadata and cryptographic hashes can be correlated to determine whether a file has been altered while maintaining a structured forensic workflow.

---

# Learning Objectives

- Understand Windows file metadata.
- Learn the importance of MAC Times.
- Investigate file properties.
- Calculate and validate file hashes.
- Reconstruct a basic forensic timeline.
- Document forensic findings.

---

# Skills Demonstrated

- Windows DFIR Investigation
- File Metadata Analysis
- MAC Time Analysis
- File Integrity Verification
- SHA256 Hash Calculation
- Timeline Reconstruction
- PowerShell Forensics
- Evidence Correlation
- IOC Documentation
- Digital Evidence Validation
- MITRE ATT&CK Mapping

---

# Tools Used

- Windows Explorer
- File Properties
- Windows PowerShell
- Get-Item
- Get-FileHash
- Notepad

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 / Windows 11 |
| Investigation Type | Digital Forensics |
| Utilities | Native Windows Tools |
| File Type | Text Document |
| Hash Algorithm | SHA256 |
| Internet Required | No |

---

# Investigation Scenario

A user reports that an important document may have been modified after it was originally created.

As the DFIR analyst, your objectives are to determine:

- When the file was created
- Whether it was modified
- When it was last accessed
- Whether the file integrity changed
- Whether metadata supports the reported activity

---

# Investigation Workflow

1. Create investigation workspace.
2. Create sample file.
3. Examine file properties.
4. Modify file contents.
5. Compare metadata.
6. Enumerate metadata using PowerShell.
7. Calculate SHA256 hash.
8. Correlate evidence.
9. Document findings.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Collection | Data from Local System | T1005 |
| Discovery | File and Directory Discovery | T1083 |

### Why File Metadata Matters

File metadata often reveals user activity that is not immediately visible from the file contents. Investigators rely on timestamps and hashes to validate evidence, reconstruct timelines, and determine whether files were modified during an incident.

---

# Evidence Collected

- File Properties
- Creation Time
- Last Modified Time
- Last Access Time
- PowerShell metadata output
- SHA256 file hash
- Timeline of file activity

---

# Evidence Correlation

| Evidence Source | Information Obtained | Investigation Value |
|-----------------|---------------------|--------------------|
| Windows Properties | Created, Modified, Accessed | Initial metadata |
| PowerShell Get-Item | MAC Times | Metadata validation |
| PowerShell Get-FileHash | SHA256 Hash | Integrity verification |
| File Contents | Updated text | Explains Modified timestamp |

Correlating timestamps with file hashes allows investigators to validate file integrity and reconstruct user activity.

---

# Investigation Findings

- File was successfully created.
- File modification updated the Last Modified timestamp.
- Created timestamp remained unchanged.
- SHA256 hash uniquely identified the current file state.
- PowerShell output validated Windows file metadata.
- Metadata accurately reflected user activity.

---

# Key Takeaways

- File metadata provides valuable forensic evidence.
- Created, Modified, and Accessed timestamps form the basis of timeline reconstruction.
- File hashes verify integrity and detect changes.
- Metadata should always be validated using multiple forensic artifacts.
- Native Windows tools are sufficient for introductory file metadata investigations.

---

