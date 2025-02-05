# Basic Linux Commands

This section covers the most commonly used Linux commands that every DevOps professional must know. Each command is explained with examples and real-time use cases to help you understand how to use them effectively in daily tasks.

## 1. **Use `man` for Help**
   - **Description**: The `man` command shows the manual page for any command. It's a great way to get more detailed information on how to use a command, including all available options and examples.
   - **Real-Time Use**: If you're unsure about how to use a command or need a quick reference for options, `man <command>` is your go-to tool.
   - **Example**:
     ```bash
     man ls
     ```

## 2. **Combine Commands with Pipes**
   - **Description**: You can combine multiple commands using pipes (`|`). This allows you to pass the output of one command directly as input to the next command, creating powerful workflows.
   - **Real-Time Use**: Combining commands with pipes helps you perform tasks more efficiently, such as filtering logs or sorting large data sets.
   - **Example**:
     ```bash
     ls -l | grep "project"
     ```
     This will list all files in the current directory and filter those that contain the word "project".

## 3. **Learn Redirection**
   - **Description**: Redirection is a method of sending the output of a command to a file or another location. The basic redirection operators are `>`, `>>`, and `<`.
     - `>`: Redirects output to a file, overwriting the file if it exists.
     - `>>`: Appends the output to the file.
     - `<`: Redirects input from a file.
   - **Real-Time Use**: Use redirection when you want to save the output of a command to a file, append logs, or even read input from a file.
   - **Example**:
     ```bash
     echo "Hello, world!" > hello.txt
     ```
     This command will save the string "Hello, world!" to a file named `hello.txt`.

## 4. **`ls` - List Directory Contents**
   - **Description**: The `ls` command lists all the files and directories in your current working directory. It also provides options to display file details and hidden files.
   - **Real-Time Use**:
     - Checking the contents of the current directory: `ls`
     - Displaying detailed information about files: `ls -l`
     - Viewing hidden files: `ls -a`
   - **Example**:
     ```bash
     ls -a
     ```

## 5. **`cd` - Change Directory**
   - **Description**: The `cd` command changes your current working directory. It's essential for navigating between different directories on your system.
   - **Real-Time Use**:
     - Moving to a project folder: `cd /home/user/project`
     - Returning to the home directory: `cd ~`
   - **Example**:
     ```bash
     cd /etc/nginx
     ```

## 6. **`pwd` - Print Working Directory**
   - **Description**: The `pwd` command prints the full path of the current working directory.
   - **Real-Time Use**: Use this to check where you are in the file system to ensure you're in the correct directory.
   - **Example**:
     ```bash
     pwd
     ```

## 7. **`cp` - Copy Files or Directories**
   - **Description**: The `cp` command copies files or directories from one location to another.
   - **Real-Time Use**:
     - Copying a file to another location: `cp file.txt /backup/`
     - Copying a directory and its contents: `cp -r /folder /backup/`
   - **Example**:
     ```bash
     cp /home/user/file.txt /backup/
     ```

## 8. **`mv` - Move or Rename Files/Directories**
   - **Description**: The `mv` command moves or renames files and directories. If the target location is a directory, the file is moved there; otherwise, it's renamed.
   - **Real-Time Use**:
     - Renaming a file: `mv oldname.txt newname.txt`
     - Moving files to a directory: `mv file.txt /path/to/directory/`
   - **Example**:
     ```bash
     mv file.txt /home/user/documents/
     ```

## 9. **`rm` - Remove Files or Directories**
   - **Description**: The `rm` command deletes files or directories. Be careful with `rm`, as deleted files are not easily recoverable.
   - **Real-Time Use**:
     - Removing a file: `rm file.txt`
     - Removing a directory and its contents: `rm -r directory/`
   - **Example**:
     ```bash
     rm -r old_folder/
     ```

## 10. **`echo` - Display Text or Variables**
   - **Description**: The `echo` command prints text or the value of variables to the terminal.
   - **Real-Time Use**: Use `echo` for debugging, displaying messages, or working with variables.
   - **Example**:
     ```bash
     echo "Hello, world!"
     ```

## 11. **`history` - Show Command History**
   - **Description**: The `history` command shows a list of previously executed commands. This can be useful for reviewing past commands or repeating them.
   - **Real-Time Use**:
     - Displaying the command history: `history`
     - Repeating a command from history: `!10` (executes the 10th command from the history list).
   - **Example**:
     ```bash
     history
     ```

## 12. **`man` - Display Manual Pages**
   - **Description**: The `man` command displays the manual for any other command. It's a powerful tool for getting detailed information on how to use a command.
   - **Real-Time Use**: If you're unsure about any command's functionality, use `man` followed by the command to get full documentation.
   - **Example**:
     ```bash
     man ls
     ```

## 13. **`chmod` - Change File Permissions**
   - **Description**: The `chmod` command modifies file permissions. It’s crucial for controlling access to files and directories.
   - **Real-Time Use**:
     - Giving execute permission: `chmod +x script.sh`
     - Changing file permissions to read-write for the user: `chmod 644 file.txt`
   - **Example**:
     ```bash
     chmod 755 script.sh
     ```

## 14. **`df` - Display Disk Space Usage**
   - **Description**: The `df` command shows the disk space usage of file systems.
   - **Real-Time Use**: Use this to monitor disk space on your servers or workstations.
   - **Example**:
     ```bash
     df -h
     ```

## 15. **`du` - Display Disk Usage**
   - **Description**: The `du` command shows the disk space used by files and directories.
   - **Real-Time Use**: Use `du` to track disk usage and manage disk space.
   - **Example**:
     ```bash
     du -sh /var/log
     ```

## 16. **`top` - Task Manager**
   - **Description**: The `top` command provides a real-time view of system resource usage, including CPU, memory, and processes.
   - **Real-Time Use**: Use `top` to monitor system performance or troubleshoot performance issues.
   - **Example**:
     ```bash
     top
     ```

## 17. **`ps` - Display Process Status**
   - **Description**: The `ps` command shows a snapshot of the current processes running on the system.
   - **Real-Time Use**: Use `ps` to check which processes are running and manage them.
   - **Example**:
     ```bash
     ps aux
     ```

## 18. **`kill` - Terminate Processes**
   - **Description**: The `kill` command terminates running processes by sending a signal to the process ID (PID).
   - **Real-Time Use**:
     - Stopping an unresponsive process: `kill <PID>`
     - Forcing a process to stop: `kill -9 <PID>`
   - **Example**:
     ```bash
     kill -9 1234
     ```

---

### Additional Tips for Efficiency:
- **Combine Commands**: Use pipes (`|`) to combine multiple commands and create efficient workflows.
- **Redirection**: Use `>`, `>>`, and `<` for redirecting output and input to/from files.
- **Use `man`**: Always refer to the manual page for in-depth information about any command.
- **Wildcard Characters**:
   - `*`: Matches zero or more characters. E.g., `ls *.txt` lists all `.txt` files.
   - `?`: Matches exactly one character. E.g., `ls file?.txt` matches `file1.txt`, `file2.txt`, etc.
   - `[]`: Matches a range of characters. E.g., `ls file[1-3].txt` matches `file1.txt`, `file2.txt`, and `file3.txt`.

### Shortcuts to Remember:
- **Ctrl+C**: Terminates a running command.
- **Ctrl+Z**: Pauses a running command and sends it to the background.
- **Ctrl+R**: Searches your command history.
- **Tab**: Auto-completes commands or file names.