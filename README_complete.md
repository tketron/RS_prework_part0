# `RS_prework_part0`

## Terminal & Git

### Terminal
#### Navigating in Terminal

* What is the difference between / and ~? What do we call each of these directories?
	* `/` refers to the root directory, the parent directory for all files and folders on the machine
	* `~` denotes the home directory, one per user under the `/Users` directory
* What command do we use to change directories?
	* `cd`
* What is the difference between an absolute and relative path?
	* An absolute path is the address to a file or folder from the root directory, while a relative path is the address for a file or folder relevant to the current directory

	
#### Working with Files and Folders

1. Create a file called name.txt.

	`touch name.txt`
	
1. Try renaming the file to rename.txt using the mv command. What does this tell you about the command?

	`mv name.txt rename.txt`.  This command can be used to rename files.
	
1. Using the cp command, make a copy of rename.txt and call it copy.txt.

	`cp rename.txt copy.txt	`
	
1. Remove the file copy.txt.

	`rm copy.txt`
	
1. Create a folder called questions.

	`mkdir questions`
	
1. Change directories to the questions folder.

	`cd questions`
	
1. Create a file called first.txt.

	`touch first.txt`
	
1. Create a file called second.txt.

	`touch second.txt`
	
1. Go back a directory and make a copy of the questions folder and call it questions_copy.

	```
	cd ..  
	cp -r questions questions_copy
	```
	
1. When using cp -r what is the -r called? What does it do?

	`-r` is called a flag, and it functions as an option to modify the command.
	
1. Delete the original questions folder and the copy.

	```
	rm -rf questions  
	rm -rf questions_copy
	```
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