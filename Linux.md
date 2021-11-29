### Essential CLI Tools

##### Check if you are ready to use: 

[Open Source Software Development, Linux and Git](https://training.linuxfoundation.org/cm/prep/?course=Coursera)


#####  List, Create, Delete and Rename Files and Directories: 

Command | Description
--------|------------
`ls` | List files
`cat` | Type out (concatenate) the files
`rm ` | Remove files
`mv` | Rename (move) files
`mkdir` | Create directories
`rmdir` | Remove directories
`file` | Show file types
`ln` | Create symbolic and hard links
`tail` | Look at the tail end of the file
`head` | Look at the beginning of the file
`less` | Look at the file, one screenful at a time
`more` | Look at the file, one screenful at a time
`touch` | Either create an empty file, or update the file modification time
`wc` | Count lines, words, and bytes in a file



#####  Find and locate: 

Command | Description
---------------------------------|---------------------------------
`find [location] [criteria] [actions]` | This is the general form of a find command where there are three classes of arguments, each of which may be omitted. If no location is given, the current directory (.) is assumed; if no criteria are given, all files are displayed; and, if no actions are given, only a listing of the names is given.
`find /etc -name "*.conf"` | An example of a logical expressions which can be used for criteria. The command:Type out (concatenate) the files will print out the names of all files in the /etc directory and its descendants, recursively, that end in .conf.
`find /etc -name "*.conf" -ls` | Specify a simple action request will print out a long listing, not just the names.
`find /tmp /etc -name "*.conf" -or -newer /tmp/.X0-lock -ls` | Look in subdirectories under /etc and /tmp for files whose names end in .conf, or are newer than /tmp/.X0-lock and print out a long listing.
`find . -name "*~" -exec rm {} ’;’` | (i) Perform actions with the -exec option,where {} is a fill in for the files to be operated on, and ’;’ indicates the end of the command. This can be unwieldy and one often pipes into the xargs program, as in below.
`find . -name "*~" \| xargs rm` | (ii) Accomplishes the above action
`for names in $(find . -name "*~" ) ; do rm $names ; done` | (iii) Accomplishes the above action
`find . -name "*~" -print0 \| xargs -0 rm` | (iv) If a filename has a blank space in it (or some other special characters), commands (i) to (iii) will fail, but this variant will work. 
`-exec rm {} ’;’. ` | Accomplishes action (iv)
`locate .conf` | Will find all files on your system that have .conf in them. locate will only find files that were already in existence the last time the database was updated. 
`sudo updatedb` |On most systems, to force an update, you need to do this as a background cron job, usually daily. 


