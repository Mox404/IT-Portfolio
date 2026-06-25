# Permission Review

## Objective

The objective was to inspect the `/home/researcher2/projects` directory and verify whether each file and directory had appropriate permissions for a research team environment.

The review used:

```bash
pwd
ls
cd projects/
ls -la
```

`ls -la` was important because it displays long-format file details and includes hidden files. Without the `-a` option, the hidden file `.project_x.txt` would not appear in the normal directory listing.

## Permission String Interpretation

Linux permissions are displayed as a 10-character string, such as:

```text
-rw-rw-r--
```

| Position | Meaning |
| --- | --- |
| Character 1 | File type, such as `-` for a file or `d` for a directory |
| Characters 2-4 | Owner permissions |
| Characters 5-7 | Group permissions |
| Characters 8-10 | Other permissions |

Each permission group can include:

| Symbol | Meaning |
| --- | --- |
| `r` | Read |
| `w` | Write |
| `x` | Execute or directory traversal |
| `-` | Permission not granted |

## Initial Findings

| Target | Observed Permission | Finding |
| --- | --- | --- |
| `project_k.txt` | `-rw-rw-rw-` | Others had write access, which violated the requirement that others should not be able to write to files. |
| `project_m.txt` | `-rw-r-----` | Permissions were already restrictive. |
| `project_r.txt` | `-rw-rw-r--` | Others had read access but no write access. |
| `project_t.txt` | `-rw-rw-r--` | Others had read access but no write access. |
| `.project_x.txt` | `-rw--w----` | Hidden archived file allowed write access and needed to be read-only for user and group. |
| `drafts` | `drwx--x---` | Group had execute access, allowing directory traversal. |

## Risk Summary

The two main risks were excessive write access and unnecessary directory access. Write access can allow unauthorized users to alter research files, while execute access on a directory can allow users to enter or traverse a directory even when they should not have access.
