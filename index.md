
Unix for Data Science
1. Why Unix
2. Basic Unix commands
3. Redirecting  standard IO
4. Pipes and Filters
5. Useful Unix commands for Data Science.





#Unix Commands for Data Science.

##Why Unix
Unix is the core of most OS except the Windows OS. MacOD, linux, BSD and android are among the popular OS supported by the unix kernel.
Most of the servers used by big tech giants like Google, meta(facebook) and IBM run on unix OS. 
The introduction of the linux terminal in the Windows OS confirms how relevant the unix terminal is for developers.

What makes the Unix OS so important to  developers?
The Shell!!
The unix shell is command line interpreter to takes input from the user as commands, execute the command and prints out the results from the commands.
The Uinx shell comes in various flavors, the popular ones being BASH, CSHELL and KSH. 
The shell is available to the user as a terminal(command line tool on unix systems) but it may also be presented as a GUI.
The three main component of a Unix shell is the STDIN, STDOUT and STDERR. These are data streams that are created when you run a commnad on a Unix shell.

## Input Streams & Redirecting IO
STDIN(F0): Standard Input. This is the input for the shell as a command. 
STDOUT(F1): Standard Output. This is the output of a shell command when the command is successfully exceuted.
STDERR(F2): Standard Error. This is the output of a command when it fails.

Demonstrating the Unix Input Streams.
STDIN
-- `ls`
This is command is an input to the shell. It is executed as a command and the output is sent to the STDOUT or STDERR should the command fail.
Not all command will return a text output hence you might not always see a text output after running the command. 
You will usually get a message in the terminal should the command fail. The command `echo $?` will return 0 if the command was successfully excecuted. 
This is a useful tip in shell scripting.

STDOUT
-- Out put of the ls command (Screenshot)
The output of the `ls` command is returned to the STDOUT. 

So where do we get the STDERR from the `ls` command above. The answer is there is no STDERR because there was no error.
Let's try listing the content of a non-existing directory, in this case there would be an error, hence we would have something in our STDERR.

STDERR
`ls  non_existing_directory`
-- Output of the STDERR with screenshot

STDIN, STDOUT, STDERR
Let's do a quick demo if these inputs stream by combining some using the file redirection[ details covered in this article] in unix.
`(ls . ; ls non_existing_folder) 0>stdin.txt  1>stdout.txt  2>stderr.txt `
- `(ls . ; ls non_existing_folder)`: We are trying to run two commands at a go and expecting one of them to fail and another to pass.
- `1>stdout.txt `:  Write the STDOUT to to text file stdout.txt.
- `2>stderr.txt ` :Write the STDERR to a text file stderr.txt.
This implies the output of this command will not be displayed on the terminal but into the files stdout.txt and stderr.txt.

`cat stdout.txt`: View the contents of STDOUT(stdout.txt) (with screenshot)
`cat stderr.txt`: View the content of STDERR(stderr.txt) (with screenshot)

##Basic Unix Commands













