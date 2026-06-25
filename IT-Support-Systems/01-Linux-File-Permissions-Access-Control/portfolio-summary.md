# Portfolio Summary

## Project

Linux File Permissions Access Control

## Short Description

Completed a Linux permissions review in a simulated research team environment. I inspected files and directories with `ls -la`, identified excessive access, and used `chmod` to enforce least privilege.

## Work Performed

* Navigated the Linux file system using `pwd`, `ls`, and `cd`.
* Reviewed full file details with `ls -la`.
* Interpreted Linux permission strings for regular files, hidden files, and directories.
* Removed unauthorized write access from `project_k.txt`.
* Corrected archived hidden file permissions on `.project_x.txt`.
* Restricted the `drafts` directory so only the owner could access it.
* Validated each permission change after remediation.

## Key Commands

```bash
ls -la
chmod o-w project_k.txt
chmod u-w,g-w,g+r .project_x.txt
chmod g-x drafts/
```

## Skills Demonstrated

* Linux administration fundamentals
* Least-privilege access control
* File and directory permission analysis
* Hidden file review
* Command-line remediation
* Security-focused documentation

## Interview Talking Points

* I can explain Linux permission strings and how owner, group, and other permissions work.
* I understand why hidden files still need to be included in access reviews.
* I can use `chmod` symbolically to make targeted permission changes.
* I validate security changes with command output instead of assuming they worked.

## Disclaimer

This is a controlled lab project. It is included to demonstrate Linux access-control skills and security documentation, not to claim production system administration experience.
