# Command Evidence

These are the screenshots from the Linux permissions lab. I kept them at the same display width so the page stays readable. Clicking an image opens the full size version.

## Checking the directory

<a href="assets/evidence/01-home-directory-listing.png"><img src="assets/evidence/01-home-directory-listing.png" alt="Home directory listing" width="700"></a>

I used `pwd`, `ls`, and `ls -la` to confirm where I was and to make sure hidden files were included.

## Removing write access for others

<a href="assets/evidence/02-project-k-other-write-removed.png"><img src="assets/evidence/02-project-k-other-write-removed.png" alt="project_k permission remediation" width="700"></a>

```bash
chmod o-w project_k.txt
```

I ran `ls -la` again and checked that `project_k.txt` no longer gave write access to others.

## Fixing the hidden archived file

<a href="assets/evidence/03-hidden-file-permissions-fixed.png"><img src="assets/evidence/03-hidden-file-permissions-fixed.png" alt="Hidden file permission remediation" width="700"></a>

```bash
chmod u-w,g-w,g+r .project_x.txt
```

The result left the user and group with read access while removing write access.

## Restricting the drafts directory

<a href="assets/evidence/04-drafts-directory-restricted.png"><img src="assets/evidence/04-drafts-directory-restricted.png" alt="Drafts directory permission remediation" width="700"></a>

```bash
chmod g-x drafts/
```

I checked the final permissions and confirmed that the group could no longer enter the directory.
