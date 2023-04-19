# Bash Scripting Cheat Sheet - Part 1

# What is Bash Scripting?

Bash scripting refers to the process of writing and executing a series of commands in the Bash shell, a command-line interface used in Unix-based operating systems. Bash scripts can automate tasks, perform system administration tasks, and manipulate files and directories. It is a powerful tool for developers and system administrators who want to streamline their work and increase productivity.

Different users can be configured to use different shells. But most users prefer to stick with the current default shell. The default shell for many Linux distros is the GNU Bourne-Again Shell (bash). Bash is succeeded by Bourne Shell (`sh`).

## Starting with bash

-   create a file with extension `.sh`. example, `script.sh`
-   Use Nano or any text editor to edit the `.sh` file

### Shebang in Bash

In Bash scripting, the shebang is the first line in a script that tells the shell which interpreter to use to execute the script. The syntax for a shebang in Bash is as follows:

```
#!/bin/bash

```

This line goes at the very beginning of the script and tells the shell to use the Bash interpreter to execute the commands in the script. It is important to include this line in your Bash scripts to ensure that they are executed correctly.

### Chmod -x

Before a Bash script can be executed, its permissions must be set to allow execution. This can be done using the `chmod` command. To give a script executable permissions, you can use the following command:

```
chmod +x script.sh

```

This command will give the file `script.sh` executable permissions, allowing you to run it as a script.

### Running a Bash Script

Once you have set the executable permissions on your script, you can run it using the following command:

```
./script.sh

```

This command will execute the script, assuming it is located in the current directory. If the script is located in a different directory, you will need to specify the path to the script.

### Comments in Bash

Comments are used in Bash scripts to add notes or explanations to the code. Comments are ignored by the shell when the script is executed. In Bash, comments start with the `#` symbol. Here is an example of a Bash script with comments:

```
#!/bin/bash

# This script prints "Hello, world!"
echo "Hello, world!" # This is a comment

```

In this example, the first line is the shebang, which specifies that the script should be run using the Bash interpreter. The second line is a comment that explains what the script does. The third line uses the `echo` command to print "Hello, world!" to the terminal. The fourth line is a comment that explains what the `echo` command does.

### Before getting into details, let’s see what a BASH shell can do

**Example block**

```
#!/bin/sh

echo "Current working directory: $(pwd)"
echo
echo "Today's date  &  time $(date)"
echo
echo  "DIST USAGE $(df -H)"
```

```
# output
root@ip-172-31-0-202:/home/ubuntu# ./shell.sh 
Current working directory: /home/ubuntu

Today's date  &  time Tue Apr 18 09:37:56 UTC 2023

DIST USAGE Filesystem       Size  Used Avail Use% Mounted on
/dev/root        8.2G  1.7G  6.5G  21% /
tmpfs            494M     0  494M   0% /dev/shm
tmpfs            198M  840k  197M   1% /run
tmpfs            5.3M     0  5.3M   0% /run/lock
/dev/nvme0n1p15  110M  6.4M  104M   6% /boot/efi
tmpfs             99M  4.1k   99M   1% /run/user/1000
```

This is a Bash script that prints the current working directory, the current date and time, and the disk usage for the file system using the `df` command with the `-H` option. The `$(pwd)` and `$(date)` commands are used to get the current working directory and the current date and time, respectively. The output of each command is printed to the terminal using the `echo` command.

## Defining a Variables

Variables in Bash are defined using the following syntax:

```
VARIABLE_NAME="value"

```

The correct way to assign a variable in shell scripting is without any whitespace on either side of the assignment operator(=) which is shown as follows

**Rules for naming a Variable**

In Bash, variable names are case-sensitive and must begin with a letter or underscore. They can contain letters, numbers, and underscores. Here are the rules for naming variable names in Bash:

-   Variable names must begin with a letter or underscore.
-   Variable names are case-sensitive.
-   Variable names can contain letters, numbers, and underscores.
-   Variable names should be descriptive and meaningful.
-   Variable names should not begin with a number.
-   Variable names should not contain spaces or special characters.

For example, valid variable names in Bash include `MY_VAR`, `_my_var`, and `myVar`. Invalid variable names include `123var`, `my var`, and `my-var`.

```
MY_VAR="Hello, world!"

```

You can **reference a variable i**n a Bash script by prefixing its name with a `$` symbol. Here is an example of how to print the value of a variable:

```
echo $MY_VAR

```

This will output `Hello, world!` to the terminal.

### System variables

System variables in Bash are pre-defined variables that hold information about the system environment. Here are some common system variables in Bash:

-   `HOME`: the home directory of the current user
-   `PATH`: the search path for commands
-   `USER`: the username of the current user
-   `SHELL`: the shell being used by the current user
-   `PWD`: the current working directory
-   `LANG`: the language setting for the system

You can reference a system variable in a Bash script using the `$` symbol followed by the variable name. For example, to print the current working directory, you can use the following command:

```
echo $PWD

```

**Q. How to capture the output of a command/system variable in a Bash script ?**

You can capture the output of a command in a Bash script by enclosing the command in backticks (```) or using the `$()` syntax. Here is an example:

```
#!/bin/bash

# This script demonstrates how to capture the output of a command and print it using echo

# Capture the output of the `date` command
DATE=$(date)

# Print the output using echo
echo "The current date and time is: $DATE"

```

This script captures the output of the `date` command using the `$()` syntax and assigns it to the `DATE` variable. It then prints the output using the `echo` command, including the value of the `DATE` variable in the message.

## Arithmetic Operations in Bash

Bash supports various arithmetic operations. Here is a table of arithmetic operators supported by Bash:

Operator

Description

Example

+

Addition

a=5; b=2; echo $((a + b))

-

Subtraction

a=5; b=2; echo $((a - b))

*

Multiplication

a=5; b=2; echo $((a * b))

/

Division

a=5; b=2; echo $((a / b))

%

Modulo

a=5; b=2; echo $((a % b))

**

Exponentiation

a=2; b=3; echo $((a ** b))

Here is an example block demonstrating the use of arithmetic operations in Bash:

```
#!/bin/bash

# This script demonstrates the use of arithmetic operations in Bash

# Declare some variables
a=10
b=3

# Perform some arithmetic operations
echo "Addition: $((a + b))"
echo "Subtraction: $((a - b))"
echo "Multiplication: $((a * b))"
echo "Division: $((a / b))"
echo "Modulo: $((a % b))"
echo "Exponentiation: $((a ** b))"

```

Double parenthesis are used in Bash to execute arithmetic operations. They allow you to perform arithmetic operations on variables and constants, and can be used to perform more complex calculations than the simple arithmetic operators. The double parenthesis are used to distinguish arithmetic evaluations from string evaluations.

This script declares two variables named `a` and `b` and performs various arithmetic operations using those variables. The `echo` command is used to print the result of each operation to the terminal. The output of the script will be:

```
Addition: 13
Subtraction: 7
Multiplication: 30
Division: 3
Modulo: 1
Exponentiation: 1000

```

### If Statement in Bash

In Bash scripting, the `if` statement is used to perform conditional execution of commands. The syntax for an `if` statement in Bash is as follows:

```
if [ condition ]
then
  # commands to execute if the condition is true
fi

```

The `condition` is a test that evaluates to true or false. If the condition is true, the commands between `then` and `fi` are executed.

Here is an example of an `if` statement in Bash:

```
#!/bin/bash

# This script demonstrates the use of an if statement

# Declare a variable
AGE=18

# Check if the person is old enough to vote
if [ $AGE -ge 18 ]
then
  echo "You are old enough to vote"
fi

```

This script declares a variable named `AGE` and assigns it the value `18`. It then uses an `if` statement to check whether the value of `AGE` is greater than or equal to `18`. If it is, the script prints the message `You are old enough to vote`.

### If Else Statement in Bash

In Bash scripting, the `if` statement is used to perform conditional execution of commands. The syntax for an `if` statement in Bash is as follows:

```
if [ condition ]
then
  # commands to execute if the condition is true
else
  # commands to execute if the condition is false
fi

```

The `condition` is a test that evaluates to true or false. If the condition is true, the commands between `then` and `else` are executed. If the condition is false, the commands between `else` and `fi` are executed.

Here is an example of an `if` statement in Bash:

```
#!/bin/bash

# This script demonstrates the use of an if statement

# Declare a variable
AGE=18

# Check if the person is old enough to vote
if [ $AGE -ge 18 ]
then
  echo "You are old enough to vote"
else
  echo "You are not old enough to vote"
fi

```

This script declares a variable named `AGE` and assigns it the value `18`. It then uses an `if` statement to check whether the value of `AGE` is greater than or equal to `18`. If it is, the script prints the message `You are old enough to vote`. If it is not, the script prints the message `You are not old enough to vote`.

**Q. How to find whether a number is even or not in BASH?**

```
#!/bin/bash

# This script demonstrates the use of an if-else statement to check if a number is even

# Declare a variable
NUM=4

# Check if the number is even
if [ $((NUM % 2)) -eq 0 ]
then
  echo "$NUM is even"
else
  echo "$NUM is odd"
fi

```

This script declares a variable named `NUM` and assigns it the value `4`. It then uses an `if-else` statement to check whether the value of `NUM` is even or odd. It does this by using the `%` operator to calculate the remainder when `NUM` is divided by `2`. If the remainder is `0`, the number is even and the script prints the message `4 is even`. If the remainder is `1`, the number is odd and the script prints the message `4 is odd`.

**Q. How do you find out if a file exists or not in Bash?**

```
#!/bin/bash

# This script demonstrates how to check if a file exists in Bash

# Declare a variable for the file name
FILE="example.txt"

# Check if the file exists
if [ -f $FILE ]
then
  echo "$FILE exists"
else
  echo "$FILE does not exist"
fi

```

This script declares a variable named `FILE` and assigns it the value `example.txt`. It then uses an `if` statement to check whether the file exists. It does this by using the `-f` flag with the `test` command (which is equivalent to using the `[` command). If the file exists, the script prints the message `example.txt exists`. If the file does not exist, the script prints the message `example.txt does not exist`.

### Some useful example of if else statement

**Q. Check if `htop` is installed, otherwise install the command.**

```
#!/bin/bash

# Check if the command file is available
if [ -f "/usr/bin/htop" ]
then
  echo "The htop command is available"
else
  echo "The htop command is not available"

  # Install the htop command using sudo
  echo "Installing htop command using sudo"
  sudo apt update && sudo apt-get install -y htop
fi

```

This script checks if the `htop` command is available by using the `-f` flag with the `test` command to check if the file `/usr/bin/htop` exists. If the file exists, the script prints the message `The htop command is available`. If the file does not exist, the script prints the message `The htop command is not available`, and then installs the `htop` command using `sudo apt-get install -y htop`.

### **Q: When you run a command in BASH, how do you know if it fails or not?**

### Exit Code

When you run a command in Bash, it returns an exit code that indicates whether the command succeeded or failed. An exit code of `0` indicates success, while any other exit code indicates failure. You can use the `$?` variable to get the exit code of the last command that was run.

Here is an example of how to use the exit code in Bash:

```
#!/bin/bash

# This script demonstrates how to use the exit code in Bash

# Run a command that will fail
ls /nonexistent-directory

# Check the exit code
if [ $? -ne 0 ]
then
  echo "The command failed"
else
  echo "The command succeeded"
fi

```

This script runs the `ls` command on a directory that does not exist, causing the command to fail. It then uses the `$?` variable to get the exit code of the last command that was run, and checks if the exit code is not equal to `0`. If the exit code is not equal to `0`, the script prints the message `The command failed`. Otherwise, it prints the message `The command succeeded`.

**Example** of using the **exit code** in Bash to install a package:

```
#!/bin/bash

# This script demonstrates how to use the exit code in Bash to install a package

# Install the package using apt-get
sudo apt-get install -y some-package

# Check the exit code
if [ $? -ne 0 ]
then
  echo "The package installation failed"
else
  echo "The package installation succeeded"
fi

```

This script installs the `some-package` package using `sudo apt-get install -y some-package`. It then uses the `$?` variable to get the exit code of the last command that was run, and checks if the exit code is not equal to `0`. If the exit code is not equal to `0`, the script prints the message `The package installation failed`. Otherwise, it prints the message `The package installation succeeded`.