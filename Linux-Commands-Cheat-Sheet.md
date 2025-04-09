# Linux Commands Cheat Sheet
Use `--help` or `man` (manual) for lists of arguments  

## Most Common Commands

|Command|Full Name|Description|Example|
|---|---|---|---|
|whoami||Current user|`whoami`|
|ls|List Directory contents|Lists everything in the current or named directory|`ls [folder]`|
|cd|Change directory|Followed by file path, changes the current directory|`cd [file path/folder name]` `cd ..`(Return a folder)|
|cat|Concatenate|Followed by file name it outputs the contents of said file|`cat [file]`|
|pwd|print working directory|Shows the directory I'm currently in|`pwd`|
|find||Searches for specific files or using regex|`find [file]/[*.*]`
|grep|Global regular expression print|Searches the contents of files for specifc values|`grep "[search term]" [file]`|
|ssh|Secure Shell|Allows connection to remote machines|`ssh [login]@[IP Address]`|  
|su|switch user|Switches the user using the username and password|`su [user]`|
|wget|??|Downloads files from the web using HTTP|`wget [website url]`|
|scp|secure copy|Transfers files and rename from the host (Between two pcs)|From host to remote`scp [file name] [user@IP:folder path]` From remote to host `scp [user@IP:file path] [file name]`|

### Interacting with Files and Folders
|Command|Full Name|Description|Example|
|---|---|---|---|
|touch|Change File Timestamps|Update times or create file|`touch [file name]`
|mkdir|Make Directory|Create a folder|`mkdir [folder name]`|
|cp|copy|Copy a file or folder|`cp [folder/file name to copy] [folder/file to paste to]`|
|mv|move|Move a file or folder can also rename|`mv [file/folder name to move] [file path to be moved to]`|
|rm|remove|Remove a file or folder|`rm [file/folder name]`|
|file|file|Determine type of file|`file [file name]`|

## Shell Operators
|Symbol/Operator|Description|
|---|---|
|&|Run commands in background|
|&&|Combine multiple commands|
|>|Redirects. Output of a commander is directed elsewhere|
|>>|Does the same as above but appends (doesn't overwrite)|

## Common Directories
|Directory Name|Use|
|---|---|
|/etc|root directory stores system files|
|/var|Variable data, root folder on Linux. Stores data frequently accessed or written by services or applications|
|/root|Home for the "root" user. Default /home/root|
|/tmp|On Linux, volatile, stores data that's only accessed a couple times. When pc restarts the folder is cleared.|

## Nano
`nano [filename]`  
`up` and `down` Keys to Navigate  
`Enter` to start a new line  
Press `ctrl`(^ on linux) and the corresponding letter to use features.  
