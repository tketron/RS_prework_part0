# `RS_prework_part0`

## Terminal & Git

### Terminal

#### Terminal Basics Exercises

##### Part I

1. make a directory called first

	`mkdir first`
	
1. change directory to the first folder

	`cd first`
	
1. create a file called person.txt

	`touch person.txt`
	
1. change the name of person.txt to another.txt

	`mv person.txt another.txt`
	
1. make a copy of the another.txt file and call it copy.txt

	`cp another.txt copy.txt`
	
1. remove the copy.txt file

	`rm copy.txt`
	
1. make a copy of the first folder and call it second

	`cp -r first second`
	
1. delete the second folder
	
	`rm -rf second`
	
##### Part II

1. What does the man command do? Type in man rm. How do you scroll and get out?

	The `man` command displays a help manual for a command.  Scroll with arrow keys and press `q` to quit.
	
1. Look at the man page for ls. What does the -l flag do? What does the -a flag do?

	The `-a` flag displays all entries whose names begin with a dot.  The `-l` flag displays entries in long format.
	
1. Type the following command to download and save the contents of google.com: curl https://www.google.com > google.html


1. Use less to look at the contents of google.html.

	`less google.html` 
	
1. Look at the man page for less. Read the section on /pattern. Search for the text hplogo in the google.html file.

	`/hplogo`

1. How do you jump between words in the terminal?

	`Option +` left or right arrow.
	
1. How do you get to the end of a line in terminal?

	`Ctrl + E`
	
1. How do you move your cursor to the beginning in terminal?

	`Ctrl + A`
	
1. How do you delete a word (without pressing backspace multiple times) in terminal?

	`Ctrl + W`
	
1. What is the difference between a terminal and shell?

	The shell is the actual program which processes commands.  The terminal is a wrapper program which runs the shell.
	
1. What is an absolute path?

	An absolute path is the address to a file or folder relative to the root directory `/`.
	
1. What is an relative path?

	A relative path is the address to a file or folder relative to the current directory.
	
1. What is a flag? Give three examples of flags you have used.

	A flag is an additional option passed to a command.  Example commands include `-a` and `-l` with `ls` and `-r` with `cp`.
	
1. What do the r and f flags do with the rm command?

	The `-r` flag recursively removes all sub directories nested inside the file argument.  The `-f` flag attempts to remove files without prompting for confirmation.
	
	
#### Permissions, Redirection, and Piping Exercise

##### Part I (Permissions and links)

1. Create a file called restricted.txt.

	`touch restricted.txt`

1. Change the permissions on the restricted.txt file to allow the owner to read and write to the restricted.txt file. Do this using the Octal Notation.

 	`chmod 600 restricted.txt`

1. Change the permissions on the restricted.txt file to only allow the owner, group and everyone to read and write and execute the restricted.txt file. Do this using the Symbolic notation.

	`chmod ugo+rwx restricted.txt` 

1. Create a folder called secret_files. Inside the secret_files folder create a file called first_secret.txt and another folder called classified. Inside of the classified folder create a file called super_secret.txt.

	```
	mkdir secret_files
	cd secret_files
	touch first_secret.txt
	mkdir classified
	cd classified
	touch super_secret.txt
	```

1. Change the permissions on the secret_files to only allow the owner and group to read, write and execute in all the files and folders inside of secret_files. Do this using the Octal Notation.

	`chmod -R 770 secret_files`

1. Create a hard link for the restricted.txt called hard_link.

	`ln restricted.txt hard_link`

1. Create a symbolic link for the classified folder called classified_link.

	`ln -s secret_files/classified classified_link`
	
	
##### Part II (Piping and Redirection)

1. Sort vegetables.txt.

	`sort vegetables.txt`

1. Count the number of lines in vegetables.txt.

	`wc -l vegetables.txt`

1. Create a file called vegetables_sorted.txt which contains all the unique vegetables sorted in ascending order in vegetables.txt (do this without the touch command).

	`sort vegetables.txt | uniq > vegetables_sorted.txt`

1. Create a file called last_three.txt which contains the last three vegetables in the vegetables.txt file (do this without the touch command).

	`tail -n 3 vegetables.txt > last_three.txt`

1. Count the number of lines the word "Broccoli" appears on (using wc and grep).

	`grep 'Broccoli' vegetables.txt | wc -l`
	
#### Intermediate Terminal Exercises

##### Part I

1. Create an environment variable called FIRST_NAME and set it equal to your first name (this does not need to be permanent)

	`export FIRST_NAME=Tyler`
	
1. Print the FIRST_NAME variable

	`echo $FIRST_NAME`
	
1. Print out the $PATH variable

	`echo $PATH`
	
1. What is the $PATH variable?

	The $PATH variable tells the terminal where to search for programs to execute.
	
1. Why would you want to create an environment variable?

	To modify or simplify the functioning of the terminal.
	
1. How do you permanently save environment variables?

	Add them to the shell configuration file (.zshrc for zsh, located in the home directory).
	
1. What is a process?

	A program on the computer being run.
	
1. How do you list all processes running on your machine?

	Use the `ps` command with the `aux` flags
1. What is a PID?

	A unique ID for each process.
	
1. How do you terminate a process?

	Use the `kill` command passing in the PID of the process to be terminated as an argument.
	
1. What is the difference between kill and kill -9?

	Processes that are crashed or frozen may not pick up on the signal to terminate from the `kill` command alone.  `kill -9` send a non-catchable non-ignorable request to the process and so is an additional option to try when `kill` alone does not work.
	
1. What grep flag allows for case insensitive search?

	`-i`
	
1. What grep flag allows for a certain number of lines before the match?

	`-B n` where n is the number of lines
	
1. What grep flag allows for a certain number of lines around the match?

	`-C n` where n is the number of lines
	
1. What grep flag allows for a certain number of lines after the match?

	`-A n` where n is the number of lines
	
1. What grep flag allows for full word search?

	`-w`
	
1. What grep flag shows you the line number of a match?

	`-n`

##### Part II

1. Find all files inside the Desktop folder that have a name of "learn."

	`find ~/Desktop -name "learn"`

1. Find all files inside the Desktop folder that start with a "P."

	`find ~/Desktop -name "P*`

1. Find all files inside the Desktop folder that end with .txt.

	`find ~/Desktop -name "*.txt"`

1. Find all files inside the Desktop/views folder that have the name data somewhere in their filename.

	`find ~/Desktop -name "*data*"`


1. Inside of the instructors.txt file, output the number of times the word "Elie" appears.

	`grep -c "Elie" instructors.txt`

1. Inside of the instructors.txt file, list all matches for any full word that starts with a capital "P."

	`grep -w "P.*" instructors.txt`

1. Inside of the instructors.txt file, list all the line numbers for any full word that starts with a "z" (it should match regardless of upper or lower case).

	`grep -iwn "z.*" instructors.txt`


### Git

#### Git Basics Exercises

1. Create a folder called learn_git_again.
	`mkdir learn_git_again`
1. cd into the learn_git_again folder.
	`cd learn_git_again`
1. Create a file called third.txt.
	`touch third.txt`
1. Initialize an empty git repository.
	`git init`
1. Add third.txt to the staging area.
	`git add third.txt`
1. Commit with the message "adding third.txt".
	`git commit -m "adding third.txt`
1. Check out your commit with git log.
	`git log`
1. Create another file called fourth.txt.
	`touch fourth.txt`
1. Add fourth.txt to the staging area.
	`git add fourth.txt`
1. Commit with the message "adding fourth.txt"
	`git commit -m "adding fourth.txt`
1. Remove the third.txt file
	`rm third.txt`
1. Add this change to the staging area
	`git add -A`
1. Commit with the message "removing third.txt"
	`git commit -m "removing third.txt`"
1. Check out your commits using git log
	`git log`
1. Change your global setting to core.pager=cat - you can read more about that here.
	`git config --global --replace-all core.page cat`
1. Write the command to list all of the global configurations for git on your machine. You can type git config --global to find out how to do this
	`git config --global -l`
	
#### Branching and Merging Exercises

##### Part I

1. What does git clean do?

	Removes untracked files from the working directory (i.e., removes files that are not under version control)
	
1. What do the -d and -f flags for git clean do?
2. 
	`-d` removes untracked folders in addition to files
	`-f` instructs the command to use force.  Without this flag git-clean will not delete files or directories unless the clean.requireForce config variable is set to false.
	
1. What git command creates a branch?

	`git checkout -b NAME_OF_BRANCH`
	
1. What is the difference between a fast-forward and recursive merge?

	A fast forward merge can occur when commits happened chronologically.  A recursive merge occurs when git cannot easily determine the order of commits on different branches.
	
1. What git command changes to another branch?
	
	`git checkout NAME_OF_BRANCH`
	
1. How do you remove modified or deleted files from the working directory?
	
	`git checkout NAME_OF_FILE`, if the file is being tracked by version control.
	
1. What git command deletes a branch?
	
	`git branch -D NAME_OF_BRANCH`
	
1. What does the git diff command do?
	
	`git diff` allows you to see changes between commits, branches, and the working tree.
	
1. How do you remove files from the staging area?

	`git rm --cached NAME_OF_FILE`
	
1. How do merge conflicts happen?
	
	The same file has been modified on two different branches and is no longer the same between branches.
	
##### Part II

	
	mkdir merge_conflict && cd merge_conflict
	git init
	touch first.txt
	echo hello > first.txt	
	git add .
	git commit -m "initial commit"
	
	git checkout -b feature
	echo world > second.txt
	git add .
	git commit -m "second commit"
	
	git checkout master
	git goodbye > second.txt
	git add .
	git commit -m "third commit"
	
	git merge feature
	
	

#### GitHub Exercises

##### Part I

1. Create a local repository and add and commit some files

	```
	mkdir github_test
	cd github_test
	git init
	touch example1.txt
	touch example2.txt
	echo foo bar > example1.txt
	echo hello world > example2.txt
	git add .
	git commit -m "initial commit"
	```


1. Create a remote repository and push your code from the local repo to the remote

	```
	git remote add origin git@github.com:tketron/test_repo.git
	git pull origin master
	git push origin master
	```


1. Fork the repo https://github.com/rithmschool/git_practice - clone it and submit a pull request




1. Create a new branch locally and push it to GitHub

	```
	git checkout -b feature
	git push origin feature
	```


1. Submit a pull request with your new branch against the master branch on the git_practice repo.

	`git pull origin master`


