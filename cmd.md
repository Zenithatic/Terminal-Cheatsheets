# Basic Command Line Commands

- [] = required argument
- () = optional argument
- {} = parameter

## Life Hacks

- you can hit tab on your keyboard to autocomplete directories when using the cd command
- you can press the up arrow to go through your command history upwards (same functionality with down arrow)
- you can open any file in the current directory by typing out the file name
- you can get the help information of a command by adding /? after the command
- you can go to the start of the current line by pressing home, and end of the current line by pressing end
- you can skip words at a time by holding ctrl + pressing left or right arrow
- you can delete words at a time by holding ctrl + pressing backspace
- executables can be run in the command line by typing the name of the executable
- you can stop a command from running by pressing ctrl + c
- you can store the results of a command in a text file by doing: cmd > file.txt

## cd [dir]

- changes the current working directory to (dir)
- directory can be absolute, e.g. C:\Users\User1\Directory1
- directory can be relative (../dir to go backwards, ./dir to go forwards)
- use "quotation marks" for directories with spaces, e.g. "C:\Program Files"

## dir (dir) ({/a}) (*.extn)

- lists all the files and subdirectories in the current working directory if dir is not provided
- lists all the files and subdirectories in the directory provided in the argument
- if /a is listed, all hidden directories will be shown as well
- if *.extn is listed, all files with file extension "extn" will be listed 

## cls

- clears all the output in the terminal

# mkdir [dirname]

- creates a new directory in the working directory with name "dirname"

# rmdir ({/s>}) [dirname]

- deletes a directory in the working directory with name "dirname"
- only deletes empty directories if no parameters specified
- if /s parameter specified, the entire directory as well as its contents will be deleted

# path

- whenever you type the name of a program, windows will first look in the current working directory for that program.
- if the program doesn't exist in the cwd, windows will look in the PATH directory, which acts as a global directory.
- the "path" command lists all the path variables
- path variables can be added using the "Edit the System Environment Variables" settings page in windows

# wmic logicaldisk get name

- displays all drive names on system

# tree 

- displays the hierarchy of files in a tree-like manner

# attrib

- used for dealing with file attributes
- add /? parameter after for help (cheatsheet)
- when used raw, it will list all files in the cwd and their attributes
- can also be used to modify attributes (e.g. attrib +r +h file.txt to make a file hidden and read only)

# echo

- used to "echo" messages or set echo property for command feedback
- can be used to create .txt files by typing: echo msg > file.txt
- the command above overrides if file already exist
- to append instead of override, use >> instead of >

# del [file]

- deletes a file in the cwd with a given filename

# type [file]

- displays all the contents of the file in the terminal

# copy [source] [destination]

- copies the file from source and pastes it in destination
- if a folder is provided as source, only FILES inside folder will be copied

# xcopy [source] [destination] ({/s})

- a more advanced copy command
- if a folder is provided as source and the /s parameter is provided, files AND folders will be copied

# move [source] [destination]

- moves source to destination

# rename [object] [newname]

- renames object to newname