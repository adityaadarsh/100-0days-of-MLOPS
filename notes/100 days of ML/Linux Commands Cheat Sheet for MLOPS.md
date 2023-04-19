#

Linux is a powerful operating system that provides users with a vast array of tools and commands to perform various tasks. Whether you are a beginner or an experienced user, it is essential to have a list of the most commonly used Linux commands to navigate and manage your system more efficiently.

## Basic command

-   `whoami`: This command displays the username of the current user.
    
    **Example:**
    
    ```
    (base) aadarsh-MacBook-Pro:~ aadarsh$ whoami
    aadarsh  ttys002  Apr 16 13:55
    ```
    

## Navigation Commands

Navigation commands are used to move around the file system and access different directories. Here are some of the most commonly used navigation commands:

-   `cd`: Change directory: This command allows you to change the current working directory to a specified directory. For example, `cd /home/user` will change the current directory to the user's home directory.
    
    `cd and cd~` both act as same in the mac terminal.
    
    **Example:**
    
    ```
    (base) aadarsh-MacBook-Pro:~ aadarsh$ cd ~
    (base) aadarsh-MacBook-Pro:~ aadarsh$
    ```
    
-   `pwd`: This will display the full path of the current working directory.
    
    ```
    (base) aadarsh-MacBook-Pro:~ aadarsh$ pwd
    /Users/aadarsh
    ```
    
-   `ls`: List contents of a directory: This command lists the files and directories in the current working directory. You can also use `ls` with options to display additional information such as file permissions, ownership, and size.
    
    **Example:**
    
    ```
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls
    example.txt
    ```
    
    -   `ls -a`: Lists all contents of a directory, including hidden files and directories.
    
    **Example:**
    
    ```
    ls -a
    ```
    
    -   `ls -l`: List contents of a directory: This command lists the files and directories in the current working directory with additional information such as file permissions, ownership, and size.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls -l
        total 0
        -rw-r--r--  1 aadarsh  staff  0 Apr 16 15:11 example.txt
        
        ```
        
    -   `ls -al:` This command lists all files and directories in the current working directory, including hidden files and directories, with additional information such as file permissions, ownership, size, and modification time.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls -al
        total 0
        drwxr-xr-x  3 aadarsh  staff  96 Apr 16 15:11 .
        drwxr-xr-x@ 3 aadarsh  staff  96 Apr 16 14:29 ..
        -rw-r--r--  1 aadarsh  staff   0 Apr 16 15:11 example.txt
        
        ```
        
        In this example, the `ls -al` command lists all files and directories in the current working directory, including hidden files and directories. The output shows that the current working directory contains a file called `example.txt`, along with information about the file's permissions, ownership, size, and modification time.
        
    -   `ls -R`: List contents of a directory and subdirectories: This command lists the files and directories in the current working directory and all its subdirectories recursively.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls -R
        .:
        docs		example.txt
        
        ./docs:
        
        ```
        
        In this example, the `ls -R` command lists the files and directories in the directory `aditya` and all of its subdirectories recursively. Since there is only one directory `docs` and it is empty, the output shows only the directory names.
        
-   `mkdir`: Create a new directory: This command creates a new directory with the specified name.
    
    **Example:**
    
    ```
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ mkdir docs
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls
    docs		example.txt
    ```
    
    -   `mkdir -p`: Create a new directory and its parent directories if they do not exist: This command creates a new directory with the specified name and its parent directories if they do not exist. This option is useful for creating directory trees with a single command.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ mkdir -p doc/newdoc/newnewdoc
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls -R
        doc		example.txt
        
        ./doc:
        newdoc
        
        ./doc/newdoc:
        newnewdoc
        
        ./doc/newdoc/newnewdoc:
        
        ```
        
        In this example, the `mkdir -p` command creates a new directory called `newnewdoc` inside the directory `newdoc`. If any of these directories do not exist, the `mkdir -p` command creates them as well.
        
-   `rmdir`: Remove an empty directory: This command removes an empty directory.
    
    **Example:**
    
    ```
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls
    docs		example.txt
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ rmdir docs
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls
    example.txt
    ```
    
    -   `rmdir -p` :The `rmdir -p` command is used to remove a directory and its parent directories if they are empty. This option is useful for removing entire directory trees with a single command.
        
        For example, the command `rmdir -p /home/user/testdir` will remove the directory `/home/user/testdir`, as well as any parent directories that are empty.
        
        Note that the `-p` option is not available in all versions of the `rmdir` command. If you are using a version that does not support this option, you can use the `rm` command with the `-r` option to remove a directory and its contents recursively.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls -R
        doc		example.txt
        
        ./doc:
        newdoc
        
        ./doc/newdoc:
        newnewdoc
        
        ./doc/newdoc/newnewdoc:
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ rmdir -p doc/newdoc/newnewdoc/ 
        (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls -R
        example.txt
        
        ```
        

## File Management Commands

File management commands are used to create, copy, move, rename, and delete files. Here are some of the most commonly used file management commands:

-   `touch`: Create a new file: This command creates a new file with the specified name.
    
    **Example:**
    
    ```
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ touch example.txt
    (base) aadarsh-MacBook-Pro:aditya aadarsh$ ls
    example.txt
    ```
    
-   `cp`: Copy a file: This command copies a file from one location to another. You can use `cp` with options to preserve file attributes such as ownership, permissions, and timestamps.
    
    **Example:**
    
    ```
    cp file1.txt backup/
    
    ```
    
    -   `cp -r directory1 directory2`: Copy a directory and its contents: This command copies a directory and all its contents to a new location. The `r` option is used to copy directories recursively.
        
        **Example:**
        
        ```
        cp -r directory1 directory2
        
        ```
        
        In this example, the `cp` command copies `directory1` and all its contents to a new directory called `directory2`.
        
    -   `cp -u file1.txt file2.txt`: Copy a file only if it is newer: This command copies `file1.txt` to `file2.txt` only if `file1.txt` is newer than `file2.txt`.
        
        **Example:**
        
        ```
        cp -u file1.txt file2.txt
        
        ```
        
        In this example, the `cp` command copies `file1.txt` to `file2.txt` only if `file1.txt` is newer than `file2.txt`.
        
    -   `cp -p file1.txt file2.txt`: Copy a file with permissions and timestamps preserved: This command copies `file1.txt` to `file2.txt` and preserves the file's permissions and timestamps.
        
        **Example:**
        
        ```
        cp -p file1.txt file2.txt
        
        ```
        
        In this example, the `cp` command copies `file1.txt` to `file2.txt` and preserves the file's permissions and timestamps.
        
-   `mv`: Move or rename a file: This command moves a file from one location to another or renames a file.
    
    -   `mv file1.txt directory`: Move a file to a directory: This command moves a file to a specified directory.
        
        **Example:**
        
        ```
        mv file1.txt docs/
        
        ```
        
        In this example, the `mv` command moves `file1.txt` to a directory called `docs`.
        
    -   `mv file1.txt newfile.txt`: Rename a file: This command renames a file.
        
        **Example:**
        
        ```
        mv file1.txt newfile.txt
        
        ```
        
        In this example, the `mv` command renames `file1.txt` to `newfile.txt`.
        
    -   `mv directory1 directory2`: Move a directory: This command moves a directory to a new location.
        
        **Example:**
        
        ```
        mv directory1 docs/
        
        ```
        
        In this example, the `mv` command moves `directory1` to a directory called `docs`.
        
    -   `mv -i file1.txt directory`: Move a file with confirmation: This command moves a file to a specified directory and prompts for confirmation before overwriting an existing file.
        
        **Example:**
        
        ```
        mv -i file1.txt docs/
        
        ```
        
        In this example, the `mv` command moves `file1.txt` to a directory called `docs` and prompts for confirmation before overwriting an existing file.
        
    -   `mv -u file1.txt file2.txt`: Move a file only if it is newer: This command moves `file1.txt` to `file2.txt` only if `file1.txt` is newer than `file2.txt`.
        
        **Example:**
        
        ```
        mv -u file1.txt file2.txt
        
        ```
        
        In this example, the `mv` command moves `file1.txt` to `file2.txt` only if `file1.txt` is newer than `file2.txt`.
        
    -   `mv -n file1.txt directory`: Move a file if it does not exist: This command moves a file to a specified directory only if a file with the same name does not already exist in the directory.
        
        **Example:**
        
        ```
        mv -n file1.txt docs/
        
        ```
        
        In this example, the `mv` command moves `file1.txt` to a directory called `docs` only if a file with the same name does not already exist in the directory.
        
    -   `mv -b file1.txt directory`: Move a file with backup: This command moves a file to a specified directory and creates a backup of any existing file with the same name.
        
        **Example:**
        
        ```
        mv -b file1.txt docs/
        
        ```
        
        In this example, the `mv` command moves `file1.txt` to a directory called `docs` and creates a backup of any existing file with the same name.
        
-   `rm`: Remove a file: This command removes a file. You can use `rm` with options to force deletion or prompt for confirmation.
    
    **Example:**
    
    -   `rm file1.txt`: Remove a file: This command removes the file `file1.txt`.
        
        **Example:**
        
        ```
        rm file1.txt
        
        ```
        
    -   `rm -i file1.txt`: Remove a file with confirmation: This command prompts for confirmation before removing the file `file1.txt`.
        
        **Example:**
        
        ```
        rm -i file1.txt
        
        ```
        
    -   `rm -r directory1`: Remove a directory and its contents recursively: This command removes the directory `directory1` and all its contents recursively.
        
        **Example:**
        
        ```
        rm -r directory1
        
        ```
        
    -   `rm -f file1.txt`: Remove a file without confirmation: This command removes the file `file1.txt` without prompting for confirmation.
        
        **Example:**
        
        ```
        rm -f file1.txt
        
        ```
        
    -   `rm -rf directory1`: Remove a directory and its contents recursively without confirmation: This command removes the directory `directory1` and all its contents recursively without prompting for confirmation.
        
        **Example:**
        
        ```
        rm -rf directory1
        
        ```
        
-   `nano`: Open a text editor: This command opens a text editor to create or edit a file.
    
    **Example:**
    
    ```
    nano file4.txt
    
    ```
    
-   `cat`: command in Linux is used to concatenate files and display the output on the terminal. Here are a few examples of using the `cat` command:
    
    -   `cat file.txt`: Display the contents of a file: This command displays the contents of a file on the terminal.
        
        **Example:**
        
        ```
        cat file.txt
        
        ```
        
        In this example, the `cat` command displays the contents of the file `file.txt` on the terminal.
        
    -   `cat file1.txt file2.txt`: Concatenate multiple files: This command concatenates the contents of multiple files and displays the output on the terminal.
        
        **Example:**
        
        ```
        cat file1.txt file2.txt
        
        ```
        
        In this example, the `cat` command concatenates the contents of `file1.txt` and `file2.txt` and displays the output on the terminal.
        
    -   `cat file1.txt > file2.txt`: Redirect output to a file: This command redirects the output of the `cat` command to a file.
        
        **Example:**
        
        ```
        cat file1.txt > file2.txt
        
        ```
        
        In this example, the `cat` command reads the contents of `file1.txt` and writes them to `file2.txt`.
        
    -   `cat file1.txt >> file2.txt`: Append output to a file: This command appends the output of the `cat` command to a file.
        
        **Example:**
        
        ```
        cat file1.txt >> file2.txt
        
        ```
        
        In this example, the `cat` command reads the contents of `file1.txt` and appends them to `file2.txt`.
        
    -   `cat -n file.txt`: Display line numbers: This command displays the contents of a file with line numbers.
        
        **Example:**
        
        ```
        cat -n file.txt
        
        ```
        
        In this example, the `cat` command displays the contents of `file.txt` with line numbers.
        
    -   `cat file1.txt | grep "pattern"`: Search for a pattern: This command searches the contents of a file for a specified pattern.
        
        **Example:**
        
        ```
        cat file1.txt | grep "pattern"
        
        ```
        
        In this example, the `cat` command reads the contents of `file1.txt` and pipes them to the `grep` command, which searches for the pattern "pattern" in the file.
        
        -   `cat file1.txt | grep -v "pattern"`: Display lines not containing a pattern: This command displays the lines of a file that do not contain a specified pattern.
            
            **Example:**
            
            ```
            cat file1.txt | grep -v "pattern"
            
            ```
            
            In this example, the `cat` command reads the contents of `file1.txt` and pipes them to the `grep` command with the `-v` option, which displays the lines of the file that do not contain the pattern "pattern."
            
        -   `cat file1.txt | head -n 10`: Display the first 10 lines of a file: This command displays the first 10 lines of a file.
            
            **Example:**
            
            ```
            cat file1.txt | head -n 10
            
            ```
            
            In this example, the `cat` command reads the contents of `file1.txt` and pipes them to the `head` command with the `-n` option, which displays the first 10 lines of the file.
            
        -   `cat file1.txt | tail -n 10`: Display the last 10 lines of a file: This command displays the last 10 lines of a file.
            
            **Example:**
            
            ```
            cat file1.txt | tail -n 10
            
            ```
            
            In this example, the `cat` command reads the contents of `file1.txt` and pipes them to the `tail` command with the `-n` option, which displays the last 10 lines of
            
-   `grep`: command is used to search for patterns within files. Here are some examples of using the `grep` command in Linux:
    
    -   `grep "pattern" file.txt`: Search for a pattern in a file: This command searches for the specified pattern in the file and displays the lines that contain the pattern.
        
        **Example:**
        
        ```
        grep "example" file.txt
        
        ```
        
        In this example, the `grep` command searches for the pattern "example" in the file `file.txt`.
        
    -   `grep -i "pattern" file.txt`: Search for a pattern in a case-insensitive manner: This command searches for the specified pattern in the file, ignoring case, and displays the lines that contain the pattern.
        
        **Example:**
        
        ```
        grep -i "example" file.txt
        
        ```
        
        In this example, the `grep` command searches for the pattern "example" in the file `file.txt`, ignoring case.
        
    -   `grep -r "pattern" directory`: Search for a pattern recursively in a directory: This command searches for the specified pattern in all files within the directory and its subdirectories, and displays the lines that contain the pattern.
        
        **Example:**
        
        ```
        grep -r "example" directory
        
        ```
        
        In this example, the `grep` command searches for the pattern "example" in all files within the directory `directory` and its subdirectories.
        
    -   `grep -v "pattern" file.txt`: Display lines not containing a pattern: This command displays the lines of a file that do not contain the specified pattern.
        
        **Example:**
        
        ```
        grep -v "example" file.txt
        
        ```
        
        In this example, the `grep` command displays the lines of the file `file.txt` that do not contain the pattern "example".
        
    -   `grep -c "pattern" file.txt`: Count the number of lines containing a pattern: This command counts the number of lines in a file that contain the specified pattern.
        
        **Example:**
        
        ```
        grep -c "example" file.txt
        
        ```
        
        In this example, the `grep` command counts the number of lines in the file `file.txt` that contain the pattern "example".
        
    -   `grep -n "pattern" file.txt`: Display line numbers: This command displays the lines of a file that contain the specified pattern, along with their line numbers.
        
        **Example:**
        
        ```
        grep -n "example" file.txt
        
        ```
        
        In this example, the `grep` command displays the lines of the file `file.txt` that contain the pattern "example", along with their line numbers.
        

## File Permissions Commands

File permission commands are used to manage file and directory permissions. Here are some of the most commonly used file permission commands:

![read, write and execute permissions](https://i.pinimg.com/originals/97/3c/49/973c49a69664f904d4bef3ae5de2a402.png)

```
  read, write and execute permissions 
```

-   `chmod`: Change file permissions: This command changes the permissions of a file or directory. You can use `chmod` with options to set permissions for owner, group, and other users.
    
    **Example:**
    
    ```
    chmod 755 file.txt
    
    ```
    
    In this example, the `chmod` command sets the file permissions of `file.txt` to `rwxr-xr-x`, which means that the **owner has read, write, and execute permissions, while the group and other users have read and execute permissions.**
    
    -   `chmod u+x file.txt`: This command adds execute permission for the owner of the file.
    
    **Example:**
    
    ```
    chmod u+x file.txt
    
    ```
    
    In this example, the `chmod` command adds execute permission for the owner of the file `file.txt`.
    
    -   `chmod g+w file.txt`: This command adds write permission for the group of the file.
    
    **Example:**
    
    ```
    chmod g+w file.txt
    
    ```
    
    In this example, the `chmod` command adds write permission for the group of the file `file.txt`.
    
    -   `chmod o-r file.txt`: This command removes read permission for other users of the file.
    
    **Example:**
    
    ```
    chmod o-r file.txt
    
    ```
    
    In this example, the `chmod` command removes read permission for other users of the file `file.txt`.
    
    -   `chmod -R 755 directory`: This command sets the permissions of all files and directories in the specified directory to `rwxr-xr-x`.
    
    **Example:**
    
    ```
    chmod -R 755 directory
    
    ```
    
    In this example, the `chmod` command sets the permissions of all files and directories in the directory `directory` to `rwxr-xr-x`.
    

## System Information Commands

System information commands are used to display information about the system's hardware and software. Here are some of the most commonly used system information commands:

-   `top`: Display system processes: This command displays the system processes' real-time status, including CPU and memory usage.
    
    **Example:**
    
    ```
    top
    
    ```
    
-   `du`: Estimate file space usage: This command displays the disk space used by files and directories. By default, `du` displays the disk space used by the current directory and its subdirectories.
    
    **Example:**
    
    ```
    du -h
    
    ```
    
    In this example, the `du` command displays the disk space used by the current directory and its subdirectories in a human-readable format. The `-h` option stands for "human-readable."
    
    -   `du -h file.txt`: This command displays the disk space used by the file `file.txt`.
    
    **Example:**
    
    ```
    du -h file.txt
    
    ```
    
    In this example, the `du` command displays the disk space used by the file `file.txt` in a human-readable format.
    
    -   `du -sh directory`: This command displays the total disk space used by the directory `directory` in a human-readable format.
    
    **Example:**
    
    ```
    du -sh directory
    
    ```
    
    In this example, the `du` command displays the total disk space used by the directory `directory` in a human-readable format.
    
-   `free`: Display system memory usage: This command displays the system's available, used, and free memory.
    
    **Example:**
    
    ```
    free
    
    ```
    
-   `df`: Display disk space usage: This command displays the disk space usage of the file system.
    
    **Example:**
    
    ```
    df
    
    ```
    
-   `uname`: Display system information: This command displays the system's kernel version, operating system, and processor architecture.
    
    **Example:**
    
    ```
    uname -a
    
    ```
    
    -   `uname -s`: This command displays the operating system name.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:~ aadarsh$ uname -s
        Darwin
        
        ```
        
    -   `uname -r`: This command displays the operating system release number.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:~ aadarsh$ uname -r
        20.3.0
        
        ```
        
    -   `uname -m`: This command displays the machine hardware name.
        
        **Example:**
        
        ```
        (base) aadarsh-MacBook-Pro:~ aadarsh$ uname -m
        x86_64
        
        ```
        
-   `history`: Display command history: This command displays the command history of the current user.
    
    **Example:**
    
    ```
    history
    
    ```
    

## Network Commands

Network commands are used to configure and troubleshoot network connections. Here are some of the most commonly used network commands:

-   `ping`: Test network connectivity: This command tests the network connectivity to a specified network host.
    
    **Example:**
    
    ```
    ping 8.8.8.8
    
    ```
    
-   `ifconfig`: Display network interface information: This command displays the network interface's configuration information.
    
    **Example:**
    
    ```
    ifconfig
    
    ```
    
-   `netstat`: Display network connections and statistics: This command displays the network connections and statistics.
    
    **Example:**
    
    ```
    netstat
    
    ```
    
-   `ssh`: Connect to a remote server: This command establishes a secure shell connection to a remote server.
    
    **Example:**
    
    ```
    ssh user@remote_host
    
    ```
    
-   `scp`: Copy files securely between servers: This command securely copies files between servers.
    
    **Example:**
    
    ```
    scp /path/to/file user@remote_host:/path/to/destination
    
    ```
    
    -   More examples
        
        **Example 1:**
        
        ```
        scp file.txt user@remote_host:/path/to/destination
        
        ```
        
        In this example, the `file.txt` is copied from the local machine to the remote server `remote_host` at `/path/to/destination`.
        
        **Example 2:**
        
        ```
        scp -r /path/to/directory user@remote_host:/path/to/destination
        
        ```
        
        In this example, the entire `directory` is copied recursively from the local machine to the remote server `remote_host` at `/path/to/destination`.
        
        **Example 3:**
        
        ```
        scp user@remote_host:/path/to/file.txt /path/to/destination
        
        ```
        
        In this example, the `file.txt` is copied from the remote server `remote_host` to the local machine at `/path/to/destination`.
        
        **Example 4:**
        
        ```
        scp -r user@remote_host:/path/to/directory /path/to/destination
        
        ```
        
        In this example, the entire `directory` is copied recursively from the remote server `remote_host` to the local machine at `/path/to/destination`. <insert-here/>
        

Remember, this is just a small selection of the many commands available in Linux. You can use the `man` command followed by the command name to display the command's manual page with detailed information about the command's usage, options, and examples. Learning these basics will help you navigate and manage your system more efficiently.

Linux is a powerful operating system that provides users with a vast array of tools and commands to perform various tasks. Whether you are a beginner or an experienced user, it is essential to have a list of the most commonly used Linux commands to navigate and manage your system more efficiently.

# Summary

This document provides a cheat sheet of Linux commands for managing files, file permissions, system information, and network connections. The document includes examples of commonly used commands.

## File Commands

File commands are used to manage files and directories. Here are some of the most commonly used file commands:

![[Pasted image 20230417165802.png]]

## File Permissions Commands

File permission commands are used to manage file and directory permissions. Here are some of the most commonly used file permission commands:

![[Pasted image 20230417165816.png]]

## System Information Commands

System information commands are used to display information about the system's hardware and software. Here are some of the most commonly used system information commands:

![[Pasted image 20230417165834.png]]

## Network Commands

Network commands are used to configure and troubleshoot network connections. Here are some of the most commonly used network commands:

![[Pasted image 20230417165858.png]]

## Try these Questions!

1.  Create a new directory called "testdir" using the `mkdir` command.
2.  Change the current directory to "testdir" using the `cd` command.
3.  Create a new text file called "testfile.txt" using the `touch` command.
4.  Open the text file "testfile.txt" in a text editor using the `nano` command.
5.  Write the following text in the file:

```
Hello, World!
This is a test file.

```

1.  Save and exit the text editor using the key combination `Ctrl+X`, `Y`, and `Enter`.
2.  Display the contents of the file "testfile.txt" using the `cat` command.
3.  Change the permissions of the file "testfile.txt" to read, write, and execute for the owner, and read-only for the group and others using the `chmod` command.
4.  Display the permissions of the file "testfile.txt" using the `ls -l` command.
5.  Copy the file "testfile.txt" to a new file called "testfile_copy.txt" in the same directory using the `cp` command.
6.  Rename the file "testfile_copy.txt" to "newfile.txt" using the `mv` command.
7.  Display the contents of the file "newfile.txt" using the `cat` command.
8.  Remove the file "newfile.txt" using the `rm` command.
9.  Remove the directory "testdir" using the `rmdir` command.

### Few more questions

1.  **File Management:** You need to copy a file named `data.txt` from `/home/user1/` directory to `/home/user2/` directory. Also, create a new directory named `backup` in `/home/user2/` directory and move the copied file to this new directory.
2.  **File Permissions:** You need to set the permissions of a file named `confidential.txt` to `rw-------` so that only the owner of the file can read and write to it.
3.  **System Information:** You need to find out the amount of free memory available on the system.
4.  **Network Connections:** You need to test the network connectivity to a remote server with IP address `192.168.1.10` using the `ping` command.