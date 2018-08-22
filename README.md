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
