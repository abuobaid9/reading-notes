# What is The Command Line ?

A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

## Opening a Terminal :-

---

- If you're on a Mac then you'll find the program Terminal under Applications -> Utilities. An easy way to get to it is the key combination 'command + space' which will bring up Spotlight, then start typing Terminal and it will soon show up.

- If on Linux then you will probably find it in Applications -> System or Applications -> Utilities. Alternatively you may be able to 'right-click' on the desktop and there may be an option 'Open in terminal'.

- If you are on Windows and intend to remotely log into another machine then you will need an SSH client. A rather good one is Putty (free) .

## Navigation :-

---

- pwd : Print Working Directory - ie. Where are we currently.

- ls / ls [options] [location] : It's short for list. Let's give it a go.

- cd : Change Directories - ie. move to another directory.

### Paths :-

There are 2 types of paths we can use, absolute and relative :-

1. Absolute path : A file or directory location in relation to the root of the file system..

2. Relative paths : A file or directory location relative to where we currently are in the file system.

### More on Paths :-

- ~ (tilde) - This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents.

- . (dot) - This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).

- .. (dotdot)- This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.

## About File :-

---

- IN linux everything is actually a file. A text file is a file, a directory is a file.

- Some Type Of Files [path] :-

1. file.exe - an executable file, or program.
2. file.txt - a plain text file.
3. file.png, file.gif, file.jpg - an image.

### Some Rules In linux :-

- Linux is Case Sensitive

- Don't use spaces in names

- Using quotes around the entire item (You can use either single or double quotes).

- Using backslash ( \ ) like student \ profile ( Escape Characters).

## Hidden Files and Directories :-

To make a file or directory hidden all you need to do is create the file or directory with it's name beginning with a . or rename it to be as such.

- rename a hidden file to remove the . and it will become unhidden.

- we can use this command to check it :

ls -a List the contents of a directory, including hidden files.

## Manual Pages

---

The manual pages are a set of pages that explain every command available on your system including what they do, the specifics of how you run them and what command line arguments they accept.

- man [command to look up] it will give me all details about the command I am looking for also how to use it.

- man -k <'search'>: if we want to search withen the manulas.

- / < term > : Within a manual page, perform a search for 'term'.

- n :After performing a search within a manual page, select the next found item.

## File Manipulation :-

---

- mkdir : Make Directory - ie. Create a directory :-

1. mkdir -p : it will make pairent directory as needed .
2. mkdir -v : it will show us what mkdir command doing .

- rmdir : Remove Directory - ie. Delete a directory :-

1. rmdir [options] < Directory >.

- touch : Create a blank file :-

1. touch [options] < filename >.

- cp Copy - ie. Copy a file or directory :-

1. cp [options] < source > < destination >.

- mv : Move - ie. Move a file or directory (can also be used to rename) :-

1. mv [options] < source > < destination >.

- rm : Remove - ie. Delete a file :-

1. rm [options] < file >.
2. rm -rf < file > : for non empty directories.
