RHCSA book chapters notes Ch 2

Displaying the current environment
#env

Finding the right man page
Use apropos or man -k(ex #man -k partition)

Environment Configuration Files 
When a user logs in, an environment is created for that user automatically. This happens based on four different files where some script code can be specified and where variables can be defined for use by one specific user: ￼ 
/etc/ profile: This is the generic file that is processed by all users upon login. ￼ 
/etc/ bashrc: This file is processed when subshells are started. ￼ 
~/. bash_profile: In this file, user-specific login shell variables can be defined. ￼ 
~/. bashrc: In this user-specific file, subshell variables can be defined. 

Using --help
Nearly all commands provide a short overview of help when the option --help is used. Some commands do not honor that option and consider it erroneous. 

Using man
To get to the bottom of the man page as fast as possible, use the G command. You can also type /example to search the man page for any examples. 
To find information in man pages, you can search the mandb database by using apropos or man -k.

Man pages are categorized in different sections. The most relevant sections for system administrators are as follows: ￼ 
1: Executable programs or shell commands ￼ 
5: File formats and conventions ￼ 
8: System administration commands 

Because man -k does not give the expected result, it makes sense to look in the man page for the man command. Type man man to open the man page of man. Once in the man page, type /-k to look for a description of the -k option. Type n a few times until you get to the line that describes the option. You’ll see that man -k is equivalent to apropos and that you can read the man page of apropos for more details.

There are also sections that provide in-depth detail, such as the sections about system calls and library calls. When using man -k, you’ll get results from all of these sections. To limit the results that display, it makes sense to use grep to show only those sections that are relevant for what you need. So, if you are looking for the configuration file that has something to do with passwords, use man -k password | grep 5, or if you are looking for the command that an administrator would use to create partitions, use man -k partition | grep 8. Another useful man option is -f. The command man -f < somecommand > displays a short description of the item as found in the man database. This may help you when deciding whether this man page contains the information you are looking for.

If that happens, you might need to update the man database. Doing that is easy: Just run the mandb command as root without any arguments. 

Using info 
Apart from the information that you’ll find in man, another system provides help about command usage. This is the info system. Most commands are documented in man, but some commands are documented only in the info system.  If that is the case, the “see also” section of the man page of that command will tell you that “The full documentation for ... is maintained as a Texinfo manual.” If that happens, you can read the Info page using the command pinfo or info. Both commands work, but in pinfo, special items such as menu items are clearly indicated, which is why using pinfo is recommended.

Using /usr/ share/ doc Documentation Files 
A third source of information consists of files that are sometimes copied to the /usr/ share/ doc directory. This happens in particular for services and larger systems that are a bit more complicated. You will not typically find much information about a command like ls, but some services do provide useful information in /usr/ share/ doc. Some services store very useful information in this directory, like rsyslog, bind, Kerberos, and OpenSSL. For setting up advanced services, you need access to this information. For setting up services on the RHCSA and RHCE exams, you can probably do without.


Define key terms
Shell- The environment from which commands can be executed. Bash is the default shell on Linux, but other shells exist as well.
Bash-The default shell that is used on Red Hat Enterprise Linux. 
Internal commands-A command that is a part of the shell and does not exist as a file on disk.
External commands - A command that exists as a file on disk.
$PATH-When used as a variable, it contains a list of directories that are searched for executable files when a user enters a command.  
Variable-A label that contains a specific value that can be changed dynamically. In scripting, variables are frequently used to allow the script to be flexible. 
STDIN- Computer keyboard <0
STDOUT- Monitor >1
STDERR-Monitor >2
File descriptor-A pointer that is used by a Linux process to refer to files that are in use by the process. 
Pipe-A structure that can be used to forward the output of one command to be used as input for another command. 
Redirect-Method where something is sent somewhere else. Used mainly in DNS
Device files-A file that is created in the /dev directory and that is used to represent and interact with a device. 
Environment-The collection of settings that users or processes are using to do their work. 
Login shell-The shell that is opened directly after a user has logged in. 
Subshell-A shell that is started from another shell. Typically, by running a shell script a subshell is started. 

Review Questions 
1. What is a variable? A placeholder that contains a specific value and that can be used in scripts to work with dynamic contents
2. Which command enables you to find the correct man page based on keyword usage? man -k
3. What file do you need to change if you want a variable to be set for every shell that is started? 
/etc/bashrc
4. When analyzing how to use a command, you read that the documentation is maintained with the Techinfo system. How can you read the information? 
Use pinfo
5. What is the name of the file where bash stores its history? 
~/.bash_history
6. Which command enables you to update the database that contains man keywords? 
mandb 
7. How can you undo the last modification you have applied in vim? 
 Use u 
8. What can you add to a command to make sure that it does not show any error message, assuming that you do not care about the information that is in the error messages either? 
2> /dev/null
9. How do you read the current contents of the PATH variable? 
echo $PATH
10. How do you repeat the last command you used that contains the string dog somewhere in the command?
Ctrl+r, dog














