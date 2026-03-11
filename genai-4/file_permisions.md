# File Permissions Commands Guide

This guide explains **file permission commands used in Linux and macOS terminals**.  
File permissions control **who can read, write, or execute files and directories**.

---

# 1. Understanding File Permissions

Each file has **three permission levels**:

| Permission | Meaning |
|---|---|
| Read (r) | View file contents |
| Write (w) | Modify file |
| Execute (x) | Run file as program |

Permissions apply to **three groups**:

| Group | Description |
|---|---|
| User (u) | File owner |
| Group (g) | Users in the same group |
| Others (o) | Everyone else |

---

# 2. Viewing File Permissions

### List Files with Permissions

```bash
ls -l
```

Example Output

```
-rwxr-xr-- 1 user staff 1024 Mar 10 script.sh
```

Breakdown

```
-rwxr-xr--
│││ │ │
│││ │ └── Others permissions
│││ └──── Group permissions
│└─────── User permissions
└──────── File type
```

File types:

| Symbol | Meaning |
|---|---|
| - | File |
| d | Directory |
| l | Symbolic link |

---

# 3. Changing File Permissions (chmod)

`chmod` changes file permissions.

---

## Symbolic Method

Format

```
chmod [who][operator][permission] file
```

Example

```bash
chmod u+x script.sh
```

Meaning

```
u → user
+ → add permission
x → execute
```

---

### Common Examples

Add execute permission

```bash
chmod +x script.sh
```

Remove write permission

```bash
chmod u-w file.txt
```

Add read permission to group

```bash
chmod g+r file.txt
```

Give all permissions to owner

```bash
chmod u+rwx file.txt
```

---

# 4. Numeric Permission Method

Permissions can also be represented with numbers.

| Permission | Value |
|---|---|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

Total permission value is the **sum of values**.

Example

| Permission | Calculation | Value |
|---|---|---|
| rwx | 4+2+1 | 7 |
| rw- | 4+2 | 6 |
| r-- | 4 | 4 |

---

### Example

```bash
chmod 755 script.sh
```

Meaning

```
Owner → rwx (7)
Group → r-x (5)
Others → r-x (5)
```

---

### Common Permission Values

| Permission | Command |
|---|---|
| Full access | 777 |
| Owner full, others read | 744 |
| Owner full, group read | 754 |
| Owner read/write only | 600 |
| Public read-only | 644 |

Example

```bash
chmod 644 file.txt
```

---

# 5. Changing File Ownership (chown)

`chown` changes file owner.

---

### Change File Owner

```bash
chown username file.txt
```

Example

```bash
chown ashish file.txt
```

---

### Change Owner and Group

```bash
chown user:group file.txt
```

Example

```bash
chown ashish:developers file.txt
```

---

### Change Ownership Recursively

```bash
chown -R user:group folder
```

---

# 6. Changing Group Ownership (chgrp)

Changes only the file group.

```bash
chgrp groupname file.txt
```

Example

```bash
chgrp developers file.txt
```

---

# 7. Recursive Permission Changes

Apply permission changes to entire directories.

Example

```bash
chmod -R 755 project_folder
```

This changes permissions for all files and folders inside.

---

# 8. Making Scripts Executable

When working with scripts (Python, Bash), execution permission is required.

Example

```bash
chmod +x script.sh
```

Run the script

```bash
./script.sh
```

---

# Summary

Important file permission commands:

```
ls -l
chmod
chown
chgrp
```

Common permission examples

```
chmod +x script.sh
chmod 755 file
chmod 644 file
chown user file
```

Understanding file permissions is essential when working with **servers, deployment environments, and executable scripts**.
