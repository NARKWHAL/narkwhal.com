## Basics
- ```cd\``` is windows cd ..
- ```dir``` -> lists the contents of the current directory
- ```dir /A``` -> WIll show all contents even the hidden ones
- ```type file.txt``` -> shows the contents of the file
- When working with a file with spaces in the name you have to put the file in double quotes
- ```type "cats are great.txt"```
- ```echo "Meow" > cat.txt``` -> This will use echo to create a file named cat.txt and add "Meow" to it
- ```echo Meow > cat.txt``` -> Will create a file with Meow in it
- ```2>``` will pipe an error if it happens
- ```del``` -> deletes a file
- ```rename``` -> Self explanatory
		- ```rename cat.txt kitten.txt``` -> renames cat.txt to kitten.txt
- ```move``` -> Moves files
		- ```move cat.txt Desktop\``` -> Moves the cat.txt to desktop
- ```copy``` -> copies a file
- ```mkdir``` -> makes a directory
- ```rmdir``` -> removes a directory
		- ```rmdir /s``` -> Allows you to remove a directory and all the files and directories inside it
- ```>``` -> operator overwrites a file
- ```>>``` -> operator appends
- ```fc``` -> Compares files
	- ```fc meow.txt cat.txt``` -> Will compare the two files and state the difference

### Locating Files
- ```dir /s meow.txt``` -> This will search the current directory and all of its sub directories for Meow.txt
- ```dir /s *.exe``` -> The wildcard will allow us to search the current and all sub directories for all executables
- ```dir /s *.txt /p``` -> Does similar to the one above but the ```/p``` switch makes the query stop when it fills the screen
- ```tree``` -> Will create a tree showing us all sub directories in a more digestable view.
- ```tree Directory\SubDirectory /F``` -> This will show the tree starting at ```SubDirectory``` the ```/F``` switch allows us to see all the files in the directories (maybe all might just be interesting)

### Searching Text in Files
- ```find "persian" C:\Docs\cats.txt``` -> will look for the string "persian" in the cats.txt file
	- You can pipe ```find``` ie ```|```
	- Find does not support Regex
- ```findstr "Alan Pasta" text.txt``` -> this will search for all occurrences of either Alan or Pasta inside of the txt doc
- ```more``` -> allows us to look at big outputs in a more user friendly method by allowing us to use arrowing to paginate through the output.

### Permissions - Users and Groups
```net``` -> allows us to manage users and groups
	- ```net user``` -> Lists all users on the current machine
	- ```net user <USERNAME>``` -> Will list all details of the account to the username given.
	- ```net localgroup``` -> shows all the local groups for the machine
	- ```net localgroup Administrators``` -> shows us all the users tied to the Administrator group
	- ```net user /add Catman thiswouldbeapassword``` -> Allows you to add a user 
		- ****NOTE**** you have to do this running CMD as Administrator
	- ```net localgroup Administrators Catman /add``` -> Adds Catman to the administrators group
		- ****NOTE**** you have to do this running CMD as Administrator
	- ```net localgroup Administrators Catman /del``` -> Removes Catman from Administrators group
		- ****NOTE**** you have to do this running CMD as Administrator
	- ```net user /del Catman``` -> Deletes the user Catman
		- ****NOTE**** you have to do this running CMD as Administrator

### Permissions - Files and Directories
- ```icacls``` -> allows you to view and interact with permissions
	- ```icacls cat.txt``` -> Will show us the ACE's of the file
	- ```icacls "cat.txt" /grant Catman:R``` -> Grants Catman read only access to cat.txt
	- ```icacls "cat.txt" /deny Catman:R``` -> Removes the read only access to cat.txt for Catman.