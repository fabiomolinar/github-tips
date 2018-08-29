If starting a new project, the easiest way to do it is to create the project on github and then just clone it to my pc.

1. git clone https://github.com/fabiomolinar/javascript-tips.git
    [The URL above is an example; use the one from the repository you want to clone]

How to move a folder from my PC to a github repository that already exists.

1. git init
2. git add *
	[Or any files you would like to add]
3. git commit -m "A commit message"
	[The message above is an example and can be change for anything else]
4. git remote add origin https://github.com/fabiomolinar/react-basics.git
	[The URL above is an example; use the one from the repository to where you want to send the files]
5. git pull origin master --allow-unrelated-histories
	[This is necessary to merge whatever was already in the repository.]
	[--alow-unreleated-histories is necessary as explained here: https://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories-on-rebase]
6. git push -u origin master
