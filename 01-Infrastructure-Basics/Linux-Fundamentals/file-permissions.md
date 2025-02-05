# Linux File Permissions 

## Table of Contents
1. [Introduction to File Permissions](#introduction-to-file-permissions)
2. [Types of Permissions](#types-of-permissions)
3. [Permission Representation](#permission-representation)
4. [Commands for Modifying Permissions](#commands-for-modifying-permissions)
5. [Special Permissions](#special-permissions)
6. [Practical Scenarios](#practical-scenarios)
7. [Key Takeaways](#key-takeaways)

---

## 1. Introduction to File Permissions
In Linux, **file permissions** control the ability of users to read, write, and execute files. They are essential for securing files and managing access on multi-user systems.

Each file or directory has three sets of permissions:
- **User (Owner)**: The file’s owner.
- **Group**: Other users who belong to the file's group.
- **Others**: Everyone else who is not the owner or part of the group.

---

## 2. Types of Permissions
Linux permissions are categorized into three main types:

1. **Read (r)**: Grants permission to view the contents of the file.
2. **Write (w)**: Grants permission to modify the contents of the file.
3. **Execute (x)**: Grants permission to run the file as a program or script.

These permissions can be applied individually or in combination to each of the user categories: **Owner**, **Group**, and **Others**.

---

## 3. Permission Representation
Permissions can be represented in two ways: **Symbolic** and **Numeric**.

### Symbolic Representation:
Permissions are displayed as a string of 10 characters:
- **File type** (first character)
- **Owner** permissions (next three characters)
- **Group** permissions (next three characters)
- **Others** permissions (last three characters)

Example:
```
-rwxr-xr-x  1 user group  12345 Jan  1 12:00 filename
```

- `-` indicates it's a regular file (directories have `d`).
- `rwx` for **User (Owner)**: read, write, and execute.
- `r-x` for **Group**: read and execute.
- `r-x` for **Others**: read and execute.

### Numeric Representation:
Each permission has a numeric value:
- **Read (r)** = 4
- **Write (w)** = 2
- **Execute (x)** = 1

Permissions are represented by three digits, corresponding to **User**, **Group**, and **Others**. 

For example:
- `rwx` = 4 + 2 + 1 = **7**
- `rw-` = 4 + 2 + 0 = **6**
- `r--` = 4 + 0 + 0 = **4**

So, `rwxr-xr-x` becomes `755`.

---

## 4. Commands for Modifying Permissions

### 1. `chmod` (Change Mode):
The `chmod` command is used to modify file permissions.

- **Syntax**: `chmod [permissions] [file]`
- **Example**: `chmod 755 myfile.txt` (Sets permissions to `rwxr-xr-x`)

You can also use symbolic representation:
- **Example**: `chmod u+x myfile.txt` (Adds execute permission to the owner)

### 2. `chown` (Change Owner):
The `chown` command changes the owner or group of a file.

- **Syntax**: `chown [user]:[group] [file]`
- **Example**: `chown john:dev myfile.txt` (Changes owner to `john` and group to `dev`)

### 3. `chgrp` (Change Group):
The `chgrp` command changes the group of a file.

- **Syntax**: `chgrp [group] [file]`
- **Example**: `chgrp dev myfile.txt` (Changes the group to `dev`)

---

## 5. Special Permissions
In addition to basic read, write, and execute permissions, Linux provides three special permissions that control specific behaviors:

1. **Setuid (s)**:
   - When applied to an executable file, it allows the file to be executed with the privileges of the file owner, rather than the current user.
   - **Example**: `chmod u+s /path/to/executable`

2. **Setgid (g)**:
   - When applied to a directory, new files and subdirectories created within the directory inherit the group of the directory, not the user's group.
   - **Example**: `chmod g+s /path/to/directory`

3. **Sticky Bit (t)**:
   - When applied to a directory, it allows only the file owner, the directory owner, or root to delete or rename files within that directory.
   - **Example**: `chmod +t /path/to/directory`

---

## 6. Practical Scenarios

Here are a few practical scenarios to help you understand when to use specific permissions:

### Scenario 1: Shared Directory for Read and Execute Access
A shared directory where users can read and execute files but not modify them.

- **Permissions**: `r-xr-xr-x` (755)
- **Command**:
  ```sh
  chmod 755 /path/to/directory
  ```

### Scenario 2: Script File for All Users to Execute
A script that needs to be executable by all users, but only the owner should be able to modify it.

- **Permissions**: `rwxr-xr-x` (755)
- **Command**:
  ```sh
  chmod 755 /path/to/script.sh
  ```

### Scenario 3: File Accessible Only by the Owner
A private file where only the owner has access to read and modify the file.

- **Permissions**: `rw-------` (600)
- **Command**:
  ```sh
  chmod 600 /path/to/file
  ```

### Scenario 4: Group Write Permissions for a Directory
A directory where the owner has full access, and the group can read and write files, but others cannot access the directory.

- **Permissions**: `rwxrwx---` (770)
- **Command**:
  ```sh
  chmod 770 /path/to/directory
  ```

---

## 7. Key Takeaways
- Understand the three categories of users: **User**, **Group**, and **Others**.
- Familiarize yourself with the different types of permissions: **Read**, **Write**, and **Execute**.
- Master both **symbolic** and **numeric** representations for permissions.
- Learn how to use the **`chmod`**, **`chown`**, and **`chgrp`** commands to modify file permissions.
- Understand the application of **special permissions** like **Setuid**, **Setgid**, and **Sticky Bit**.
- Practice real-world scenarios to solidify your knowledge.