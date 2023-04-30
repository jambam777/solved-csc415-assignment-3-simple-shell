Download Link: https://assignmentchef.com/product/solved-csc415-assignment-3-simple-shell
<br>
For this assignment you will implement your own shell that runs on top of the regular command-line interpreter for Linux.

Your shell should read lines of user input, then parse and execute the commands by forking/creating new processes. For each command, your shell should call fork() followed by execvp(). Following each command, your shell should wait for its child process to complete, and then print the child PID and the return result from the child. The user should be able to specify the command to execute by giving a path to the executable file (e.g. /bin/ls) or by using path expansion to locate the executable file (i.e. searching each directory in the PATH environment variable). (Note that the execvp() function perform this processing automatically; you do not need to program it yourself.)

If your shell encounters an error while reading a line of input it should report the error and exit. If your shell encounters EOF while reading a line of input, it should exit gracefully without reporting an error. Ensure that you do not overflow a 1024 byte buffer when fetching the line of input (functions that do not accept the size of your buffer are not able to prevent overflows whereas functions that do accept a size generally do; be sure to check the manpage of any function you use carefully). You do not need to report an error if the user’s input line is larger than the 1024 byte buffer; just use the truncated input as the command.

Before your shell forks a new process to call execvp(), it should parse the input string and separate it into a collection of substrings representing the executable file and any command-line arguments. If the user entered an empty line, report an error and fetch a new line of input. Your code must handle at least four command-line arguments (in addition to the name of the executable file itself).

You should store pointers to the substrings in an array (similar to the “argv” array passed to main()) and pass this array of arguments to execvp(). Note that the number of command-line arguments is variable; this is indicated in the array by including a NULL pointer in the array after the last substring. (This means that if the user specifies N substrings, your array must hold N + 1 pointers where the last pointer is NULL.) If the user enters the exit command, your shell should terminate (returning to the regular shell).

Not that your shell does not need to support cd (change directory).

Your program should be able to also accept a command line argument which is the prefix prompt. If no value is specified use “&gt;” as the prompt.

Here is a sample execution:

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b0c3c4c5d4d5dec4f0c3c4c5d4d5dec49de6d9c2c4c5d1dcf2dfc8">[email protected]</a>:~/CSC415/assignment3$ ./assn3 prompt$prompt$ ls -ltotal 20-rwxr-xr-x 1 student student 13216 Feb 23 13:44 assn3-rw-r–r– 1 student student 1583 Feb 23 13:44 assn3.cChild 2124, exited with 0prompt$ ls fools: cannot access ‘foo’: No such file or directoryChild 2125, exited with 2prompt$ exit<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="d6a5a2a3b2b3b8a296a5a2a3b2b3b8a2fb80bfa4a2a3b7ba94b9ae">[email protected]</a>:~/CSC415/assignment3$You should submit your source code file(s), and Makefile along with a short writeup in PDF format that includes a description of what you did and the compilation and execution output from your program to GitHub and just the PDF to iLearn. Your execution output should include commands with command-line arguments. Then use the exit command to exit your program and show the output of the same commands in the regular command-line interpreter for that machine to ensure they match.

All filenames should be &lt;lastname&gt;_&lt;firstname&gt;HW&lt;#&gt;_&lt;optional&gt;.&lt;proper extension&gt;


