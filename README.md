# New project
If starting a new project, the easiest way to do it is to create the project on github and then just clone it to my pc.

1. git clone https://github.com/fabiomolinar/javascript-tips.git
  * The URL above is an example; use the one from the repository you want to clone

# Copying project from PC to Github
How to move a folder from my PC to a github repository that already exists.

1. git init
2. git add *
  * Or any files you would like to add
3. git commit -m "A commit message"
  * The message above is an example and can be change for anything else
4. git remote add origin https://github.com/fabiomolinar/react-basics.git
  * The URL above is an example; use the one from the repository to where you want to send the files
5. git pull origin master --allow-unrelated-histories
  * This is necessary to merge whatever was already in the repository.
  * `--alow-unreleated-histories` is necessary as explained here: https://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories-on-rebase
6. git push -u origin master

# Script to check status of multiple github folders
- Source: https://coderwall.com/p/grmruq/git-status-on-all-repos-in-folder

`find . -maxdepth 1 -mindepth 1 -type d -exec sh -c '(echo {} && cd {} && git status -s && echo)' \;`

Where:
  - find . : to find everything in the current folder
  - -maxdepth 1 : so that it doesn't recurse into subdirs of the repos
  - -mindepth 1 : so that it skips the current directory (of depth 0)
  - -type d : only find directories
  - -exec sh -c : spawn a shell and give it a command
  - `'(echo {} && cd {} && git status && echo)'` : the command given to the shell
  - echo {} : echo the directory found by find
  - cd {} : cd into the directory found by find
  - git status -s : run the actual git status, with the -s (short) option
  - echo : echo an empty line, for readability
  - \; : semicolon to run shell for each of the found directories instead of passing them all to one shell as arguments
