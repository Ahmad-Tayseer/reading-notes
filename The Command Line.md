***The Command Line***
***
***

**1. The Command Line**

*Definition:*

    It is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

*The Shell, Bash:*

    This is a part of the operating system that defines how the terminal will behave and looks after running (or executing) commands. 
    
    * There are various shells available but the most common one is called bash which stands for Bourne again shell.

***

**2. Basic Navigation**

    This stuff really forms the foundation of being able to work effectively in Linux.

*pwd command:* 

    Which stands for Print Working Directory. It tells the user what is the current or present working directory.

    Example: pwd => /home/ryan

*ls command:* 

    It tells the user what's there in current Location by listing the contents of a directory.

    Example: ls => bin Documents public_html

*Paths:*

    IT is a means to get to a particular file or directory on the system.

    - There are 2 types of paths we can use, absolute and relative.

    - Relative path is a file or directory location relative to where the user currently is in the file system.
    
    - Absolute path is a file or directory location in relation to the root of the file system.

    - Either type of path used, the system will still be directed to the same location.

*cd command:* 

   It stands for change directory, which lets the user to move around in the system or move to another directory.

***

**3. More About Files**

*Everything is a File:*

    Everything is actually a file. A text file is a file, a directory is a file, keyboard is a file (one that the system reads from only, your monitor is a file (one that the system writes to only) etc.

*Linux is an Extensionless System:*

    A file extension is normally a set of (2 - 4) characters after a full stop at the end of a file, which denotes what type of file it is. 

    The following are common extensions:

        - file.exe => an executable file, or program.
        - file.txt => a plain text file.
        - file.png, file.gif, file.jpg => an image.

*Linux is Linux is Case Sensitive:*

    - As such it is possible to have two or more files and directories with the same name but letters of different case.

    - Other systems such as Windows are case insensitive when it comes to referring to files.

    Examples: FILE1.txt ** File1.txt ** file1.TXT
    - Linux sees these all above files as distinct and separate files.

*Spaces in names:*

    It is about how to seperate items. Spaces in file and directory names are perfectly valid but it needs a little careful with them, because it is seen as two command line arguments.

    There are two ways to go about this:

    - Quotes: The first approach involves using quotes around the entire item. 

    Example: 'Holiday Photos'

    - Escape Characters: which is a backslash ( \ ). It does is escape (or nullify) the special meaning of the next character.

    Example: Holiday\ Photos

*Hidden Files and Directories:*

    Linux actually has a very simple and elegant mechanism for specifying that a file or directory is hidden. If the file or directory's name begins with a . (full stop) then it is considered to be hidden.

    - ls -a => List the contents of a directory, including hidden files.

***

**4. Manual Pages**

*Definition:*

    They are a set of pages that explain every command available on the system including what they do, the specifics of how it runs and what command line arguments they accept.

    - Look up the manual page for a particular command => man <command to look up>

    - To exit the man pages press 'q' for quit.

*Searching:*

    The searching can be helpful for the user whoe doesn't quite sure of what command may use but knows what result wanted. 

    - Do a keyword search for all manual pages containing the given search term => man -k <search term>

    - Within a manual page, perform a search for 'term' => /<term>

    - After performing a search within a manual page, select the next found item => n

***

**5. File Manipulation**

*Making a Directory:*

    mkdir command => Create a directory.

*Removing a Directory:*

    rmdir command => Delete a directory.

*Creating a Blank File:*

    touch command => Create a blank file.

*Copying a File or Directory:*

    cp command => Copy a file or directory.

*Moving a File or Directory:*

    mv command => Move a file or directory (can also be used to rename).

*Removing a File (and non empty Directories):*

    rm command => Delete a file.

*The Linux command line does not have an undo feature. Perform destructive actions carefully.*

***

**Cheat Sheet**

    This cheat sheet is intended to be a quick reminder for the main concepts involved in using the command line and assumes the user is already understand their usage. 

[Cheat Sheet link page](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)

***

[README](README.md)