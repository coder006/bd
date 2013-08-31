me: bd

--------------------------------------------------------------------
Description: Go back to a specific parent directory in linux instead
of typing "cd ../../.." redundantly.
--------------------------------------------------------------------
How to install:

Just put this 'bd' file in your /usr/bin (or any other directory
which is included in your "PATH" environment variable)

And optionally,

Put this line: 
     alias bd='. bd -s'
in your ~/.bashrc file and source it by typing "source ~/.bashrc"


--------------------------------------------------------------------
How to use:

If you are in this path /home/user/project/src/org/main/site/utils/file/reader/whatever
and you want to go to site directory quickly, 

(and if you haven't done the optional step)

then just type:
     '. bd site'

If you have done the optional step above(setting up alias), then you 
need not type a dot and space.

In that case, You can simply type 'bd <starting few letters>'.

So in the case of the following example, it would be
     'bd s' or 'bd si'

(Your intuition will tell you how to use)

If there are more than one directories with same name up in the hierarchy,
bd will take you to the closest. (Not considering the immediate parent.)

--------------------------------------------------------------------
Other uses:

Using bd within backticks (`bd <letter(s)>`) prints out the path
without changing the current directory. You can take advantage of 
that by combining `bd <letter(s)>` with other commands such as ls,
ln, echo, zip, tar etc..

Example:

1. If you just want to list the contents of a parent directory,
   without going there, then you can use:
		ls `bd p`
   in the given example, it will list the contents of 
             /home/user/project/

2. If you want to execute a file somewhere in a parent directory,
            `bd p`/build.sh
   will execute /home/user/project/build.sh while not changing the
   current directory.

3. If you reside in /home/user/project/src/org/main/site/utils/file/reader/whatever 
   and want to change to /home/user/project/test, then try
            cd `bd p`/test

--------------------------------------------------------------------

Screenshot:
![bd screenshot](https://raw.github.com/vigneshwaranr/bd/master/screenshot/bd.png "Screenshot that shows some of several ways to use bd")