# Linux Commands Cheat Sheet
## Most Common Commands
Use --help or man (manual) for lists of arguments
|Command|Full Name|Description|Example|
|--- |---|---|---|---|
|whoami||Current user|`whoami`|
|ls|List Directory contents|Lists everything in the current or named directory|`ls [folder]`|
|cd|Change directory|Followed by file path, changes the current directory|`cd [file path/folder name]` `cd ..`(Return a folder)|
|cat|Concatenate|Followed by file name it outputs the contents of said file|`cat [file]`|
|pwd|print working directory|Shows the directory I'm currently in|`pwd`|
|find||Searches for specific files or using regex|`find [file]/[*.*]`
|grep|Global regular expression print|Searches the contents of files for specifc values|`grep "[search term]" [file]`|
|ssh|Secure Shell|Allows connection to remote machines|`ssh [login]@[IP Address]`|

### Interacting with Files and Folders
|Command|Full Name|Description|Example|
|---|---|---|---|---|
|touch|Change File Timestamps|Update times or create file|`touch [file name]`
|mkdir|Make Directory|Create a folder|`mkdir [folder name]`|


## Shell Operators
|Symbol/Operator|Description|
|---|---|
|&|Run commands in background|
|&&|Combine multiple commands|
|>|Redirects. Output of a commander is directed elsewhere|
|>>|Does the same as above but appends (doesn't overwrite)|
