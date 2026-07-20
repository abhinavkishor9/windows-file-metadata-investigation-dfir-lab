# Troubleshooting Notes

## Issue 1 — Modified Timestamp Does Not Change

### Cause

The file was opened but not saved.

### Resolution

Make a change to the document and save it before comparing metadata.

---

## Issue 2 — Last Access Time Does Not Update

### Cause

Modern versions of Windows may limit Last Access updates for performance.

### Resolution

This behavior is expected. Focus primarily on Created and Modified timestamps during basic investigations.

---

## Issue 3 — PowerShell Displays Different Time Format

### Cause

PowerShell uses system regional settings.

### Resolution

Compare timestamps rather than formatting.

---

## Issue 4 — File Hash Changes

### Cause

Any modification to file contents produces a new SHA256 hash.

### Resolution

This is expected behavior and demonstrates file integrity validation.

---

## Issue 5 — File Properties Do Not Refresh

### Cause

Properties window remained open during editing.

### Resolution

Close and reopen the Properties window after saving the file.

---

# Lessons Learned

- MAC Times are foundational forensic artifacts.
- File hashes verify integrity, not authorship.
- Metadata should always be validated using multiple evidence sources.
- Native Windows utilities provide reliable introductory forensic capabilities.
