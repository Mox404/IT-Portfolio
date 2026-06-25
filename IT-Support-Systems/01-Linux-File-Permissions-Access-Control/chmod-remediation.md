# Chmod Remediation

## Remediation Goal

The remediation goal was to align the Linux file system permissions with least privilege. Users should only have the access needed for their role, and unauthorized write or directory access should be removed.

## File Permission Fix

`project_k.txt` allowed write access for others:

```text
-rw-rw-rw-
```

The command used was:

```bash
chmod o-w project_k.txt
```

This removed write permission from the `other` permission group. The updated file permission became:

```text
-rw-rw-r--
```

## Hidden File Permission Fix

The hidden file `.project_x.txt` represented an archived project file. Because it was archived, nobody should have write access. The user and group should be able to read it.

The command used was:

```bash
chmod u-w,g-w,g+r .project_x.txt
```

This command:

| Command Part | Effect |
| --- | --- |
| `u-w` | Removes write permission from the user |
| `g-w` | Removes write permission from the group |
| `g+r` | Adds read permission for the group |

The updated hidden file permission became:

```text
-r--r-----
```

## Directory Permission Fix

The `drafts` directory should only be accessible by the owner, `researcher2`. The initial permission allowed group execute access:

```text
drwx--x---
```

The command used was:

```bash
chmod g-x drafts
```

This removed group execute permission. The updated directory permission became:

```text
drwx------
```

## Validation

After each change, `ls -la` was run again to confirm the updated permission state. This validation step is important because permission changes should be verified immediately after remediation.
