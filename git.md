# Git Cheatsheet

- Git is an open source and free source control management (SCM).
- Git is used to manage changes to files over time.
- Git Bash is the default CLI for Git. 
- A .gitignore file can be used to ignore files in the repository. E.g.:

```
# This is a comment

# Ignore a single file
example.txt

# Keep a single file
!example.txt

# Ignore multiple files with same extension
*.txt

# Ignore multiple files with same name
example*

# Ignore folder
examples/

# Ignore file inside folder
examples/example.txt

# Ignore everything in a folder
examples/*

# Keep a file in a folder
!examples/example.txt

# Ignore all files with the same name in every folder
**/example.txt

# Ignoring files only in root directory
/example.txt
```

# Git Commands

- To get help with any command, type the command then put -h after it.
- To get the manual page, type git help cmd.
- [] = required argument
- () = optional argument
- {} = parameter

## Configurations

### git config --global user.name "name"
- sets the name of the user to use

### git config --global user.email "email"
- sets the email of the user to use

### git config --global init.default branch "main"
- sets the default branch name to "main"

## Helper Commands

### clear
- clears the terminal of any previous output

### cd [dir]
- changes the current working directory to dir

### git --help
- displays a list of commonly used git commands

## Repository Commands

### git init
- initializes the repository in the current working directory

### git status
- shows the status of the respository in the cwd
- by default, it will show that all of the files are untracked (git won't care if they are changed)

### git add ({--all}) [filename] 
- tracks the file with name "filename"
- if --all is specified, all files in directory will be tracked (or do git add .)
- make sure to re-add files after editing them to add them to staging (can be skipped with git commit -a)

### git rm ({--cached}) [filename]
- untracks the file with name "filename"
- if --cached is specified, it will only be removed from the repository. If unspecified, file will be deleted from fs too.

### git commit ({-a}) -m ["commitMessage"] ({--amend})
- takes a "snapshot" of the repository at the current point in time
- makes a commit with description commitMessage after -m tag
- if -a is provided, all tracked & modified files will be automatically staged (skip git add)
- if --amend is provided, the commit will amend and modify the previous commit

### git diff
- shows the differences between the current directory and the latest commit

### git restore ({--staged}) [filename]
- restores the given file to its previous commit state
- moves file back to working files if --staged is specified (file would not be included in commit)

### git mv [oldFileName] [newFileName]
- renames, or "moves", old file into new file

### git log ({--oneline}) ({-p})
- shows the history of commits for the current repository
- if --oneline is specified, each commit will be displayed on one line
- if -p is specified, a more detailed log will be outputted (press q to exit)

### git reset [hashtag]
- rewinds the repository to the commit with given tag

### git branch ({-d}) ({-M}) (name)
- creates a new branch with a given name
- if name is not provided, a list of all the branches will be outputted
- if -d tag is specified, branch with given name will be deleted
- if -M tag is provided, current branch will be renamed to name

### git switch ({-c}) (branch)
- switches the current branch to the given branch
- if -c is specified, a new branch will be created and current branch will be set to new branch

### git merge -m [message] [branch]
- merges the given branch into the current branch 
- if a merge conflict arises, it has to be resolved by editing the file in which the conflict occurs

## Remote repository commands (GitHub)

### git remote add origin [link]
- establishes a remote connection to the link, calls this connection 'origin'

### git push ({--all}) ({--delete}) -u origin [branch]
- pushes the branch provided to the remote location
- if --all is specified, all branches will be pushed and branch parameter is not needed
- if --delete is specified, branch will be deleted at remote location

### git fetch origin [branch]
- fetches the given branch from the remote repository origin to origin/branch
- fetches everything if branch is not specified
- does not merge with local code (need to git merge origin/branch)

### git pull origin [branch]
- fetches the given branch from the remote repository origin
- fetches everything if branch is not specified
- merges local code and fetched code after