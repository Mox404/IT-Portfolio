# Linux File Permissions Lab

This was a controlled lab from the Google Cybersecurity course.

I had to inspect a small Linux file structure, find permissions that were too open, and fix them with `chmod`.

## What I did

I used `pwd`, `ls`, and `ls -la` to check the directory and permission strings.

| Target | Problem | Fix |
| --- | --- | --- |
| `project_k.txt` | others could write to it | `chmod o-w project_k.txt` |
| `.project_x.txt` | archived file still had write access | `chmod u-w,g-w,g+r .project_x.txt` |
| `drafts/` | group had directory access it did not need | `chmod g-x drafts/` |

I checked the permissions again after every change instead of assuming the command worked.

## Screenshots

[View the command evidence](./command-evidence.md)

The useful part for me was getting comfortable reading owner, group, and other permissions without guessing.

> Course lab only. Not production Linux administration.
