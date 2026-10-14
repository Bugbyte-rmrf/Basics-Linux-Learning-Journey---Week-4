## Introduction

The module covered basic scripting.

The screenshots included in this README provide evidence of the commands I used and the results I obtained while completing the exercise.

---

### 1. Shell Scripts in a Nutshell
**Shell script** - A file of executable commands that has been stored in a text file.  

I learned that shell scripts have access to all the commands of the shell, including logic. 

A script can therefore test for the presence of a file or look for particular output and change its behavior accordingly. 

Running a script can be done either by passing it as an argument to your shell or by running it directly.


<img width="608" height="99" alt="Screenshot from 2026-10-14 10-40-20" src="https://github.com/user-attachments/assets/2c07cb41-9ebe-44a7-ae29-e1d61f493b4b" />

The error `Permission denied` means that the script has not been marked as executable.

`chmod` is used to change the permissions of a file.

**shebang** - A shorten form created by two characters `#!` which are traditionally called the **hash** and the **bang** respectively. 

```bash
#!/bin/sh
echo "Hello, World!"
```

or 
```bash
#!/bin/bash
echo "Hello, World!"
```

It is used for traditional shell scripts and other text-based languages like Perl, Ruby, and Python.

### What I Learned
I learned that a script can be as simple as one command: `echo "Hello, World!"`

One can build scripts to automate repetitive parts of your work, which frees your time and ensures consistency each time you use the script. 

I also learned that it is important to be comfortable using a text editor before writing shell scripts, since you will need to create files in plain text. 

---

### 2. Editing Shell Scripts

---

**a) The GNU nano editor** 

It is a very simple editor well suited to editing small text files. 

I learned that you can type with your keyboard, using the arrow keys to move around and the delete/backspace button to delete text. 

To get familiar with the editor, run `nano test.sh` and start typing out a simple shell script while inside:

<img width="611" height="37" alt="Screenshot from 2026-10-14 11-09-34" src="https://github.com/user-attachments/assets/bf86ad9a-348f-4dd5-907d-49954256d968" />

<img width="613" height="438" alt="Screenshot from 2026-10-14 11-05-18" src="https://github.com/user-attachments/assets/48fe6d16-c03b-49fa-891f-ce298ea200b6" />

At this point, you can exit the program without saving by pressing the N key, or save first by pressing Y to save. The default is to save the file with the current file name. You can press the Enter key to save and exit.

<img width="613" height="438" alt="Screenshot from 2026-10-14 11-06-21" src="https://github.com/user-attachments/assets/04fb3f11-3a2a-4550-a8c7-3d5764926e73" />

**Other Commands Used in GNU nano editor**
- `Ctrl + W` - search the document
- `Ctrl + W`, then `Control + R` - search and replace
- `Ctrl + G` - show all the commands possible
- `Ctrl + Y/V` - page up / down
- `Ctrl + C` - show the current position in the file and the file’s size

---

**b) The Visual Editor**

`vi`, or its newer version, VI improved (`vim`), is a remarkably powerful editor but has a steep learning curve. 

---

### 3. Scripting Basics

---

**a) Variables**

I learned that variables hold temporary information in the script. 

```bash
#!/bin/bash`
ANIMAL="penguin"
echo "My favorite animal is a $ANIMAL"
```

The variable name is `ANIMAL` and the `equals sign` assigns the string penguin.

The script echos a string to the console. The string contains the name of the variable preceded by a `dollar sign`. 

When the interpreter sees that `dollar sign` it recognizes that it will be substituting the contents of the variable, which is called **interpolation**. 

The output of the script is then `My favorite animal is a penguin`.

```bash
#!/bin/bash
CURRENT_DIRECTORY=`pwd`
echo "You are in $CURRENT_DIRECTORY"
```

Based on the above, I learned another way to assign to a variable is to use the output of another command as the contents of the variable by enclosing the command in back ticks. This pattern is often used to process text. 

It is possible to get input from the user of your script and assign it to a variable through the `read` command:

```bash
#!/bin/bash

echo -n "What is your name? "
read NAME
echo "Hello $NAME!"
```
The `read` command can accept a string right from the keyboard or as part of command redirection
 
I learned also that the `grep` command can be used to look for a string within a file with the `–q` flag, which means “quiet”. The `grep`, while running in quiet mode, returns `0` if the string was found and `1` otherwise.

<img width="609" height="106" alt="Screenshot from 2026-10-14 12-05-06" src="https://github.com/user-attachments/assets/cde6f3c8-5c67-4605-8fec-a468125dd9eb" />

Likewise you can set the exit code of your own script with the `exit` command:

```bash
#!/bin/bash
# Something bad happened!
exit 1
```

The example above shows a comment `#`. Anything after the hash mark is ignored, which can be used to help the programmer leave notes. The `exit 1` returns exit code 1 to the caller. This even works in the shell, if you run this script from the command line and then type `echo $?` you will see it returns `1`.

By convention, an exit code of `0` means *“everything is OK”*. Any exit codes *greater than `0`* mean *some kind of error happened*, which is specific to the program. 


### What I Learned
I learned that capitalizing the name of the variable is not necessary but it is a useful convention to separate variables from commands to be executed.

I also learned that it is important that there are no spaces between the name of the variable, the equals sign, and the item to be assigned to the variable. 

---

**b) Conditionals**

---

**i)`if` Command**

I learned that Conditionals lets you to make your script do different functions based on tests called **branching**.

The `if` statement is the basic operator to implement branching.

```bash
if somecommand; then
  # do this if somecommand has an exit code of 0
fi
```

---

**ii)`grep` Command**

Using what you know about `grep`, you can now write a script that does different things based on the presence of a string in the password file:

```bash
#!/bin/bash

if grep -q root /etc/passwd; then
  echo root is in the password file
else
  echo root is missing from the password file
fi
```

I learned that from the above example, instead of an `fi` to close off the `if` block, there’s an `else`. This lets you do one action if the condition is true, and another if the condition is false. The `else `block must still be closed with the `fi` keyword.

---

**iii)`test` Command**

The `test` command gives you easy access to comparison and file test operators. For example:
- `test –f /dev/ttyS0` - 0 if the file exists
- `test ! –f /dev/ttyS0` - 0 if the file doesn’t exist
- `test –d /tmp` - 0 if the directory exists
- ``test –x `which ls`` - substitute the location of `ls` then `test` if the user can execute
- `test 1 –eq 1` - 0 if numeric comparison succeeds
- `test ! 1 –eq 1` - NOT – 0 if the comparison fails
- `test 1 –ne 1` - Easier, `test` for numeric inequality
- `test “a” = “a”` - 0 if the string comparison succeeds
- `test “a” != “a”	` - 0 if the strings are different
- `test 1 –eq 1 –o 2 –eq 2` - `-o` is OR: either can be the same
- `test 1 –eq 1 –a 2 –eq 2` - `-a` is AND: both must be the same

Consult the `test man` page for more.

---

**iv)`elif` Command**

I learned also that the `if` statement has a final form that lets you do multiple comparisons at one time using `elif` (short for `else if`).

```bash
#!/bin/bash

if [ "$1" = "hello" ]; then
  echo "hello yourself"
elif [ "$1" = "goodbye" ]; then
  echo "nice to have met you"
  echo "I hope to see you again"
else
  echo "I didn't understand that"
fi
```

The code above compares the first argument passed to the script. If it is `hello`, the first block is executed. 

If not, the script checks to see if it is goodbye and echos a different message if so. 

Otherwise, a third message is sent. Note that the `$1` variable is quoted and the string comparison operator is used instead of the numeric version (`-eq`).


**v)`if/elif/else` Command**

```bash
#!/bin/bash

case "$1" in
hello|hi)
  echo "hello yourself"
  ;;
goodbye)
  echo "nice to have met you"
  echo "I hope to see you again"
  ;;
*)
  echo "I didn't understand that"
esac
```
The case statement starts off with a description of the expression being tested: `case EXPRESSION in`. The expression here is the `quoted $1`.

Next, each set of tests are executed as a pattern match terminated by a closing parenthesis. That is for `hello`or `hi`; multiple options are separated by the vertical bar `|` which is an OR operator in many programming languages. Following that are the commands to be executed if the pattern returns true, which are terminated by `two semicolons`. The pattern repeats.

The `*` pattern is the same as an `else` because it matches anything. The behavior of the case statement is similar to the `if/elif/else`statement in that processing stops after the first match. If none of the other options matched, the `*` ensures that the last one will match.

### What I Learned
In `test`command, 01 and 1 are the same by numeric comparison, but not by string comparison. You must always be careful to remember what kind of input you expect.

---

**c) Loops**

 I learned that Loops allow code to be executed repeatedly. 

---

**i)`for` Loop**

I learned that `for` loops are used when you have a finite collection over which you want to iterate, such as a list of files, or a list of server names:

```bash
#!/bin/bash

SERVERS="servera serverb serverc"
for S in $SERVERS; do
  echo "Doing something to $S"
done
```

The script first sets a variable containing a space separated list of server names. The `for` statement then loops over the list of servers, each time it sets the `S` variable to the current server name. 

The choice of `S` was arbitrary, but note that the `S` has no dollar sign but the `$SERVERS` does, showing that `$SERVERS` will be expanded to the list of servers. The list does not have to be a variable. 

I also learned that there are two more ways to pass a list as shown below:

```bash
#!/bin/bash

for NAME in Sean Jon Isaac David; do
  echo "Hello $NAME"
done

for S in *; do
  echo "Doing something to $S"
done
```

For the first loop, list is passed to the `for` loop directly instead of using a variable. Using a variable helps the clarity of the script as someone can easily make changes to the variable rather than looking at a loop.

The second loop uses a `*` which is a file glob. This gets expanded by the shell to all the files in the current directory.

---

**ii)`while` Loop**

 i learned that `while` loop operates on a list of unknown size. 

Its job is to keep running and on each iteration perform a test to see if it should run another time. 

You can think of it as *“while some condition is true, do stuff.”*

```bash
#!/bin/bash

i=0
while [ $i -lt 10 ]; do
  echo $i
  i=$(( $i + 1))
done
echo “Done counting”
```

The example above shows a `while` loop that counts from 0 to 9. A counter variable, `i`, is initialized to `0`. Then a `while` loop is run with the `test` being *“is $i less than 10?”*

Note that the while loop uses the same notation as an if statement!

Within the `while` loop, the current value of `i` is echoed and then `1` is added to it through the `$`(( *arithmetic* )) command and assigned back into `i`. Once `i` becomes 10 the `while` statement returns false and processing continues after the loop.
