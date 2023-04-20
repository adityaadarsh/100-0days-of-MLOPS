# Bash Scripting Cheat Sheet - Part 2
## While Loop

A while loop executes a set of commands repeatedly as long as a specified condition is true. The syntax of a while loop is as follows:

```
while [condition]
do
    [commands]
done

```

Here, `[condition]` is a test command that returns a status of 0 (true) or 1 (false). If the status is true, the `[commands]` will be executed. The `[commands]` can be a single command or a block of commands enclosed in `{}`.

### Example

Suppose we want to print numbers from 1 to 5. We can use the following while loop:

```
i=1
while [ $i -le 5 ]
do
    echo $i
    i=$((i+1))
done

```

In this example, the `[condition]` is `[ $i -le 5 ]`, which means the loop will execute as long as the value of `$i` is less than or equal to 5. The `[commands]` in this case are two commands: `echo $i` and `i=$((i+1))`. The first command prints the value of `$i` to the screen, and the second command increments the value of `$i` by 1.

When we run this script, we get the following output:

```
1
2
3
4
5

```

## For Loop

A `for` loop is used to iterate over a sequence of values. The syntax of a `for` loop is as follows:

```
for var in [sequence]
do
    [commands]
done

```

Here, `[sequence]` is a list of values that `var` will take on successively. The `[commands]` will be executed for each value of `var`.

### Example

Suppose we want to print the numbers from 1 to 5 using a `for` loop. We can use the following script:

```
for i in 1 2 3 4 5
do
    echo $i
done

```

In this example, the `[sequence]` is the list of values `1 2 3 4 5`. The `[commands]` in this case is the command `echo $i`, which will print the value of `i` to the screen.

When we run this script, we get the following output:

```
1
2
3
4
5

```

### Simplify the for loop `[sequence]`

In bash, `{1...5}` is a brace expansion that generates a sequence of values from 1 to 5, inclusive. This is equivalent to writing `1 2 3 4 5`. You can use this syntax in a `for` loop to iterate over the sequence of values. For example, the following script will print the numbers from 1 to 5 using a `for` loop with brace expansion:

```
for i in {1..5}
do
    echo $i
done

```

When we run this script, we get the following output:

```
1
2
3
4
5

```

Note that the syntax `{1...5}` is incorrect and will result in an error. The correct syntax is `{1..5}`.

**Some practical example**

**Q. How do I zip all the files inside the `logfile` directory?**

Suppose we have a directory called `logfile` that contains several log files, and we want to compress all the files in the directory into a single archive. We can use the following script:

```
#!/bin/bash

for file in /path/to/logfile/*
do
        gzip "$file"
done

```

The above code is a bash script that compresses all the files in a directory called `logfile` into a single archive. It uses a `for` loop to iterate over all the files in the directory, and the `gzip` command to compress each file. The `*` wildcard is used to match all files in the directory, and the `$file` variable is used to refer to each file in turn. When the script is run, it will compress each file in the directory using the `gzip` command. The resulting compressed files will be stored in the same directory as the original files.

To write the text "hello" to a file named `output.txt` using bash, you can use the following command:

```
echo "hello" > output.txt

```

This will create a new file called `output.txt` in the current directory, and write the text "hello" to the file. If the file already exists, the command will overwrite the existing file with the new text.

## Functions

A function is a block of code that can be called repeatedly throughout a script. Functions are useful for encapsulating common tasks or operations that need to be repeated multiple times with different inputs.

### Defining a Function

To define a function in bash, you can use the following syntax:

```
function_name () {
    [commands]
}

```

Here, `function_name` is the name of the function, and `[commands]` is the block of code that defines the function. The function can take arguments, which are passed to it as positional parameters.

### Example

Here is an example bash function that checks the exit code of a command and prints an error message if the exit code is not zero:

```
check_exit_code () {
    if [ $? != 0 ]
    then
        echo "error"
    fi
}

```

This function uses the `$?` variable to check the exit code of the previous command. If the exit code is not zero, the function prints the error message "error" to the screen. You can call this function after running a command to check its exit code. For example:

```
ls /path/to/some/directory/
check_exit_code

```

In this example, the `ls` command is run to list the files in a directory. The `check_exit_code` function is then called to check the exit code of the `ls` command. If the command failed, the function will print the error message "error" to the screen.

Note that you can replace the `ls` command with any other command whose exit code you want to check.

### Another Example

Suppose we want to define a function that takes two arguments and returns their sum. We can use the following script:

```
#!/bin/bash

add () {
    sum=$(($1 + $2))
    echo $sum
}

result=$(add 2 3)
echo "The sum is: $result"

```

In this example, we define a function called `add` that takes two arguments and returns their sum. The function uses the `$1` and `$2` variables to refer to the first and second arguments, respectively. It then calculates the sum of the arguments and stores the result in the `sum` variable. Finally, the function uses the `echo` command to print the value of `sum` to the screen.

We then call the `add` function with arguments `2` and `3`, and store the result in a variable called `result`. Finally, we use the `echo` command to print the value of `result` to the screen.

When we run this script, we get the following output:

```
The sum is: 5

```

Note that the `add` function can be called with different arguments to calculate the sum of different numbers.

### Passing Arguments to a Function

To pass arguments to a function in bash, you can use the positional parameters `$1`, `$2`, `$3`, and so on. These variables refer to the first, second, third, and subsequent arguments passed to the function, respectively.

### Returning Values from a Function

To return a value from a function in bash, you can use the `return` command followed by a value. The value can be a string, a number, or any other data type that can be stored in a variable.

### Example

Suppose we want to define a function that takes two arguments and returns their product. We can use the following script:

```
#!/bin/bash

multiply () {
    product=$(($1 * $2))
    return $product
}

multiply 2 3
result=$?
echo "The product is: $result"

```

In this example, we define a function called `multiply` that takes two arguments and returns their product. The function uses the `$1` and `$2` variables to refer to the first and second arguments, respectively. It then calculates the product of the arguments and stores the result in the `product` variable. Finally, the function uses the `return` command to return the value of `product` to the calling program.

We then call the `multiply` function with arguments `2` and `3`. The function returns the product of the arguments, which is stored in the special variable `$?`. We then use the `echo` command to print the value of `$?`, which is the value returned by the `multiply` function.

When we run this script, we get the following output:

```
The product is: 6

```

Note that the `multiply` function can be called with different arguments to calculate the product of different numbers.

## Read input from the user

The `read` command is used to read input from the user and store it in a variable. The syntax of the `read` command is as follows:

```
read variable_name

```

Here, `variable_name` is the name of the variable to store the input in. When the `read` command is executed, it waits for the user to enter input, and then stores the input in the specified variable.

### Example

Suppose we want to write a script that prompts the user to enter their name and then prints a greeting. We can use the following script:

```
#!/bin/bash

echo "What is your name?"
read name
echo "Hello, $name!"

```

In this example, we use the `echo` command to print a message to the screen, and the `read` command to read the user's input. We then use the `echo` command again to print a greeting that includes the user's name.

When the user runs this script, they will be prompted to enter their name. After they enter their name, the script will print a greeting that includes their name.

Note that the `read` command can be used to read input other than text, such as numbers or filenames. To read a number, you can use the `-n` option to specify the number of characters to read, and the `-p` option to prompt the user for input. For example:

```
read -p "Enter a number: " -n 2 number

```

This command will prompt the user to enter a two-digit number, and store the number in the `number` variable. To read a filename, you can use the `-e` option to enable tab completion. For example:

```
read -e -p "Enter a filename: " filename

```

This command will prompt the user to enter a filename, and enable tab completion for file paths.

## Case Statement

A `case` statement is used to match a variable against a list of patterns, and execute the corresponding commands if a match is found. The syntax of a `case` statement is as follows:

```
case variable in
pattern1)
    [commands1]
    ;;
pattern2)
    [commands2]
    ;;
...
esac

```

Here, `variable` is the variable to match against the patterns, and `pattern1`, `pattern2`, and so on are the patterns to match. The `;;` symbols are used to separate the commands for each pattern.

### Example

Suppose we want to write a script that installs a Linux distribution based on user input. We can use a `case` statement to match the user input against a list of distributions, and execute the corresponding commands to install the selected distribution. Here is an example script:

```
#!/bin/bash

echo "Which Linux distribution do you want to install?"
echo "1. Ubuntu"
echo "2. Debian"
echo "3. Fedora"
echo "4. CentOS"

read choice

case $choice in
    1)
        echo "Installing Ubuntu..."
        # Commands to install Ubuntu
        ;;
    2)
        echo "Installing Debian..."
        # Commands to install Debian
        ;;
    3)
        echo "Installing Fedora..."
        # Commands to install Fedora
        ;;
    4)
        echo "Installing CentOS..."
        # Commands to install CentOS
        ;;
    *)
        echo "Invalid choice!"
        ;;
esac

```

In this example, we use the `echo` command to print a list of Linux distributions to the screen, and the `read` command to read the user input. We then use a `case` statement to match the user input against the list of distributions, and execute the corresponding commands to install the selected distribution.

When the user runs this script, they will be prompted to select a Linux distribution to install. If they enter a valid choice (1, 2, 3, or 4), the script will execute the corresponding commands to install the selected distribution. If they enter an invalid choice, the script will print an error message.

Note that the `case` statement can be used to match any variable against a list of patterns, not just user input.

## at command

The `at` command in bash is used to run a command or script at a specified time in the future. The syntax of the `at` command is as follows:

```
at [-f file] [-m] [-q queue] [-t time] [-v] [time]

```

Here, `time` is the time at which the command or script should be run. The time can be specified in a number of different formats, such as `now`, `noon`, or `midnight`, or as a specific date and time.

The `[options]` specify additional options for the `at` command. For example, the `-f` option can be used to specify a file containing the command or script to be run, and the `-m` option can be used to send an email to the user when the job is complete.

### Example

Suppose we want to run a script called `backup.sh` at 3:00 AM tomorrow. We can use the following command:

```
echo "/path/to/backup.sh" | at 3am tomorrow

```

In this example, we use the `echo` command to write the command `/path/to/backup.sh` to the standard input of the `at` command. We then use the `at` command to run the command at 3:00 AM tomorrow.

When the `at` command runs the script, it will execute the commands in the script as if they were typed directly into the terminal. The script can perform any task, such as backing up files or sending email notifications.

Note that the `at` command can be used to run any command or script, not just bash scripts. For example, you can use the `at` command to schedule a shutdown or reboot of the system, or to run a Python script or other program.

### Scheduling Jobs in Bash

In bash, you can use the `cron` utility to schedule jobs to run at specified intervals. The `cron` utility is a time-based job scheduler that runs commands at specified intervals.

To schedule a job in `cron`, you need to create a `crontab` file that specifies the jobs to run and the intervals at which they should be run. The syntax of a `crontab` file is as follows:

```
*     *     *     *     *  command to be executed
-     -     -     -     -
|     |     |     |     |
|     |     |     |     +----- day of the week (0 - 6) (Sunday = 0)
|     |     |     +------- month (1 - 12)
|     |     +--------- day of the month (1 - 31)
|     +----------- hour (0 - 23)
+------------- min (0 - 59)

```

Here, the first five fields specify the time and date when the command should be run, and the last field specifies the command to be run. The asterisk (`*`) symbol is used as a wildcard to match any value.

For example, the following `crontab` entry would run the command `/path/to/command` every day at 3:30 AM:

```
30 3 * * * /path/to/command

```

To edit your `crontab` file, you can use the `crontab -e` command. This will open your `crontab` file in the default text editor. You can then add, edit, or delete entries as needed.

Note that the syntax of the `crontab` file can be complex, so it is a good idea to test your entries using the `date` command before adding them to your `crontab` file.

### Example

Suppose we want to schedule a job to run a script called `backup.sh` every day at 5:00 AM. We can use the following `crontab` entry:

```
0 5 * * * /path/to/backup.sh

```

In this example, the `crontab` entry specifies that the command `/path/to/backup.sh` should be run every day at 5:00 AM.

When the `cron` daemon runs the `crontab` entry, it will execute the command `/path/to/backup.sh` at the specified time. The `backup.sh` script can perform any task, such as backing up files or sending email notifications.

Note that the `crontab` entry can be modified to run the command at different intervals, such as every hour or every week. For example, the following `crontab` entry would run the command every hour:

```
0 * * * * /path/to/command

```

This entry specifies that the command `/path/to/command` should be run every hour at the start of the hour (when the minute field is `0`).

### Common Issues

One common issue when using `cron` is that the `PATH` environment variable may not be set correctly. This can cause `cron` to be unable to find the commands specified in the `crontab` file.

To fix this issue, you can set the `PATH` environment variable in your `crontab` file. For example, you can add the following line to your `crontab` file to set the `PATH` variable to include the directories `/usr/bin` and `/usr/local/bin`:

```
PATH=/usr/bin:/usr/local/bin

```

This will ensure that `cron` can find the commands specified in your `crontab` file.

Another common issue is that the output of the command may not be redirected correctly. By default, the output of the command is sent to the email address of the user who created the `crontab` file. This can result in large amounts of email being sent to the user's inbox.

To fix this issue, you can redirect the output of the command to a file instead of sending it to the user's email address. For example, you can add the following line to your `crontab` file to redirect the output of the command to a file called `output.log`:

```
0 5 * * * /path/to/backup.sh > /path/to/output.log 2>&1

```

This will ensure that the output of the command is stored in the file `output.log` instead of being sent to the user's email address. The `2>&1` syntax is used to redirect both standard output and standard error to the same file.

### Conclusion

In this section, we have discussed how to schedule jobs in bash using the `cron` utility. We have seen how to create a `crontab` file, and how to specify the intervals at which commands should be run. We have also discussed some common issues that can arise when using `cron`, and how to fix them.

With this knowledge, you should be able to schedule jobs in bash with confidence and ensure that your scripts are run at the correct intervals.

## Summary

Topic

Summary

While Loop

Repeatedly executes a set of commands as long as a specified condition is true.

For Loop

Iterates over a sequence of values.

Functions

Block of code that can be called repeatedly throughout a script.

Read input from the user

Reads input from the user and stores it in a variable.

Case Statement

Matches a variable against a list of patterns, and executes corresponding commands if a match is found.

At command

Runs a command or script at a specified time in the future.

Cron utility

Schedules jobs to run at specified intervals.

### Examples

### While Loop

```
i=1
while [ $i -le 5 ]
do
    echo $i
    i=$((i+1))
done

```

### For Loop

```
for i in 1 2 3 4 5
do
    echo $i
done

```

### Functions

```
check_exit_code () {
    if [ $? != 0 ]
    then
        echo "error"
    fi
}

```

### Read input from the user

```
echo "What is your name?"
read name
echo "Hello, $name!"

```

### Case Statement

```
case $choice in
    1)
        echo "Installing Ubuntu..."
        # Commands to install Ubuntu
        ;;
    2)
        echo "Installing Debian..."
        # Commands to install Debian
        ;;
    3)
        echo "Installing Fedora..."
        # Commands to install Fedora
        ;;
    4)
        echo "Installing CentOS..."
        # Commands to install CentOS
        ;;
    *)
        echo "Invalid choice!"
        ;;
esac

```

### At command

```
echo "/path/to/backup.sh" | at 3am tomorrow

```

### Cron utility

```
0 5 * * * /path/to/backup.sh

```