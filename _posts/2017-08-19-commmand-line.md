---
layout: post
title: "How to use the command line"
author: "Chris"
---

What is the Command Line? Well it's the thing you see hackers typing into in the movies. You know with all the black and green text. Thing of the command line as a more powerful remote for your computer.

How to open the command line. If your using a mac click on the search light and type terminal into the box and press enter. You should now have a box on the screen. That has something similar to this.

```
Last login: Sat Aug 19 14:01:03 on ttys000
Chriss-MacBook-Air:~ chris$

```

You are now into the mainframe!

So what sorts of things can you type into that box? Well first off you have to know how to navigate. To see where you are you can type pwd.

```
Last login: Sat Aug 19 14:01:03 on ttys000
Chriss-MacBook-Air:~ chris$ pwd
/Users/chris
Chriss-MacBook-Air:~ chris$ 
````

Pwd gives you the path of where you are on your computer.Pwd stands for print working directory. A lot of commands have been shortened because when they writing unix back in the day, they didn't wan't to type out a whole command. You may not be familair with the file structure of a unix system but /Users/chris is my home directory. In this directory is my Downloads, Desktop, Pictures ... etc Files. So how do we see these files. Type ls.

```
Chriss-MacBook-Air:~ chris$ ls
Applications			Desktop				Library				PreVeil-Testing			Villefort			school
Chris Reuter's CV.pdf		Documents			Movies				ProjectEuler			assignments			social.org
Chris Reuter's CV1.pages	Downloads			Music				Public				bower.json			tale-master
Chris Reuter's CV1.pdf		Haskell				Pictures			Purescript			lc.hs
Chriss-MacBook-Air:~ chris$ 


```

As you can see I have a lot of folders in my home directory but you should see something similar.
If at any point you wan't to read more about a commmand, say ls you can type `man ls`

```
LS(1)                     BSD General Commands Manual                    LS(1)

NAME
     ls -- list directory contents

SYNOPSIS
     ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]

DESCRIPTION
     For each operand that names a file of a type other than directory, ls displays its name as well as any requested, associated information.  For each operand that names a file of
     type directory, ls displays the names of files contained within that directory, as well as any requested, associated information.

     If no operands are given, the contents of the current directory are displayed.  If more than one operand is given, non-directory operands are displayed first; directory and non-
     directory operands are sorted separately and in lexicographical order.

     The following options are available:

     -@      Display extended attribute keys and sizes in long (-l) output.

     -1      (The numeric digit ``one''.)  Force output to be one entry per line.  This is the default when output is not to a terminal.

     -A      List all entries except for . and ...  Always set for the super-user.

     -a      Include directory entries whose names begin with a dot (.).

     -B      Force printing of non-printable characters (as defined by ctype(3) and current locale settings) in file names as \xxx, where xxx is the numeric value of the character in
             octal.

     -b      As -B, but use C escape codes whenever possible.

     -C      Force multi-column output; this is the default when output is to a terminal.

     -c      Use time when file status was last changed for sorting (-t) or long printing (-l).

     -d      Directories are listed as plain files (not searched recursively).

     -e      Print the Access Control List (ACL) associated with the file, if present, in long (-l) output.

     -F      Display a slash (`/') immediately after each pathname that is a directory, an asterisk (`*') after each that is executable, an at sign (`@') after each symbolic link, an
             equals sign (`=') after each socket, a percent sign (`%') after each whiteout, and a vertical bar (`|') after each that is a FIFO.

     -f      Output is not sorted.  This option turns on the -a option.

     -G      Enable colorized output.  This option is equivalent to defining CLICOLOR in the environment.  (See below.)

     -g      This option is only available for compatibility with POSIX; it is used to display the group name in the long (-l) format output (the owner name is suppressed).

     -H      Symbolic links on the command line are followed.  This option is assumed if none of the -F, -d, or -l options are specified.

     -h      When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the number of digits to three or less using
             base 2 for sizes.

     -i      For each file, print the file's file serial number (inode number).

     -k      If the -s option is specified, print the file size allocation in kilobytes, not blocks.  This option overrides the environment variable BLOCKSIZE.

     -L      Follow all symbolic links to final target and list the file or directory the link references rather than the link itself.  This option cancels the -P option.

     -l      (The lowercase letter ``ell''.)  List in long format.  (See below.)  If the output is to a terminal, a total sum for all the file sizes is output on a line before the
             long listing.
```

You can use the arrow keys to move up and down and type q to quit. That's a lot of information I know. But you don't have to memorize it! You can just look it up at any time. Man sounds for manual if you haven't guessed that.

So know we know how to see where we are and see what's there let's learn how to change where we are. To change where we are you can type cd. So from my home directory let's say I wan't to go to my downloads. I can type cd Downloads/

```
Chriss-MacBook-Air:~ chris$ cd Downloads/
Chriss-MacBook-Air:Downloads chris$ 
```

The slash at the end means it's a directory, directory is just computer nerd speak for a folder. Notice how the prompt changes to include Downloads, the prompt is the thing that occurs before the
`$` sign.

Let's see what's in my Downloads.

```
Chriss-MacBook-Air:Downloads chris$ ls
18620254_1987587898129254_5717056479093310776_n.jpg	Doc Apps—USSoc.docx					alex.pem
2012-08-01 pro-se-reply-brief.August 2012.pdf		Epic_53.0.2785.143 (1).dmg				captain-log
547409.jpg						Epic_53.0.2785.143 (2).dmg				captain-log-20170815T032940Z-001.zip
760731.jpg						Epic_53.0.2785.143.dmg					chromedriver_mac64.zip
760733.png						Firefox							console-master.zip
760734.png						Firefox 54.0.1.dmg					fish-1.1
760738.jpg						Firefox.zip						fish-1.1.tar.gz
Chris Reuter CV (1).pdf					KeePass2.23.app						geckodriver-v0.18.0-macos.tar.gz
Chris Reuter CV (2).pdf					KeePass2.23.zip						github-recovery-codes.txt
Chris Reuter CV.pdf					MacPass-0.6.2-alpha.zip					introtopython-ch0.pdf
Chris Reuter's CV (1).docx				MacPass.app						material-bliss-jekyll-theme-master
Chris Reuter's CV.docx					Pop punk.docx						material-bliss-jekyll-theme-master.zip
Chris Reuter's CV.pdf					RHITAthletics.jpg					pass.kdbx
Chris Reuter's CV1.docx					Recon Docs USSocREV (1).docx				ruby-2.4.1.tar.gz
Chris Reuter's CV1.pages				Recon Docs USSocREV.docx				rubygems-2.6.12
Chris Reuter's CV1.pdf					Remembering The Day After.REV'17.docx			rubygems-2.6.12.tgz
Chris Reuter's CV3 (1).docx				TorBrowser-7.0.4-osx64_en-US.dmg			tale-maste 2
Chris Reuter's CV3 (1).pages				USSoc.Project'17REV1.docx				tale-master
Chris Reuter's CV3.docx					USSoc.Project'17REV2.docx				tale-master (1).zip
College Counseling_Autobiography.pdf			Unconfirmed 33452.crdownload				tale-master-1.zip
College Data Sheet.pdf					Unconfirmed 407272.crdownload				xmoto-0.5.10-macosx.zip
Critical Essay Tips (1).docx				Unconfirmed 751700.crdownload
Critical Essay Tips.docx				X-Moto.app
Chriss-MacBook-Air:Downloads chris$ 


```
Wow that's a lot of stuff I should really delet some of it.
To delete a file we can use the command rm. Be warned rm doesn't move things into the trash bin it just deletes it off the hardrive never to be found again so `once you rm something it is well and truly gone`. Consider yourself officially warned.