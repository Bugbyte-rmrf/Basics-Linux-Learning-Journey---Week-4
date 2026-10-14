## Introduction

The module covered basic scripting.

The screenshots included in this README provide evidence of the commands I used and the results I obtained while completing the exercise.

---

### 1. Shell Scripts in a Nutshell
A **shell script** - A file of executable commands that has been stored in a text file.  

I learned that shell scripts have access to all the commands of the shell, including logic. 

A script can therefore test for the presence of a file or look for particular output and change its behavior accordingly. 

Running a script can be done either by passing it as an argument to your shell or by running it directly.

<img width="608" height="99" alt="Screenshot from 2026-10-14 10-40-20" src="https://github.com/user-attachments/assets/2c07cb41-9ebe-44a7-ae29-e1d61f493b4b" />

The error `Permission denied` means that the script has not been marked as executable.

`chmod` is used to change the permissions of a file.

**shebang** - A shorten form created by two characters `#!` which are traditionally called the **hash** and the **bang** respectively. 

It is used for traditional shell scripts and other text-based languages like Perl, Ruby, and Python.

### What I Learned
I learned that a script can be as simple as one command: `echo "Hello, World!"`

One can build scripts to automate repetitive parts of your work, which frees your time and ensures consistency each time you use the script. 

I also learned that it is important to be comfortable using a text editor before writing shell scripts, since you will need to create files in plain text. 

---

### 2. Editing Shell Scripts
a) The GNU nano editor 

It is a very simple editor well suited to editing small text files. 

I learned that you can type with your keyboard, using the arrow keys to move around and the delete/backspace button to delete text. 

To get familiar with the editor, run `nano test.sh` and start typing out a simple shell script while inside:

<img width="613" height="438" alt="Screenshot from 2026-10-14 11-05-18" src="https://github.com/user-attachments/assets/48fe6d16-c03b-49fa-891f-ce298ea200b6" />

<img width="611" height="37" alt="Screenshot from 2026-10-14 11-09-34" src="https://github.com/user-attachments/assets/bf86ad9a-348f-4dd5-907d-49954256d968" />

At this point, you can exit the program without saving by pressing the N key, or save first by pressing Y to save. The default is to save the file with the current file name. You can press the Enter key to save and exit.

<img width="613" height="438" alt="Screenshot from 2026-10-14 11-06-21" src="https://github.com/user-attachments/assets/04fb3f11-3a2a-4550-a8c7-3d5764926e73" />

*** Other Commands Used in GNU nano editor**
- `Ctrl + W` - search the document
- `Ctrl + W`, then `Control + R` - search and replace
- `Ctrl + G` - show all the commands possible
- `Ctrl + Y/V` - page up / down
- `Ctrl + C` - show the current position in the file and the file’s size

b) The Visual Editor, 

`vi`, or its newer version, VI improved (`vim`), is a remarkably powerful editor but has a steep learning curve. 

### 3. Scripting Basics
a) Variables

Variables, which hold temporary information in the script











