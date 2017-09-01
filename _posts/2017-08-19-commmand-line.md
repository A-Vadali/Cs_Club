---
layout: post
title: "How to be a command line wizard"
author: "Chris Reuter"
---

What is the Command Line? Well it's the thing you see hackers typing into in the [`movies`](https://www.youtube.com/watch?v=dFUlAQZB9Ng). You know with all the [`black and green text`](http://hackertyper.com/). Think of the command line as a control panel for your computer.

# For Macs

How to open the command line. If your using a mac click on the search light and type terminal into the box and press enter. You should now have a box on the screen. That has something similar to this.


    Last login: Sat Aug 19 14:01:03 on ttys000
    Chriss-MacBook-Air:~ chris$


What can you type into the terminal? Well, you have to know how to navigate. To see where you are you can type [`pwd`](https://www.tcl.tk/man/tcl8.4/TclCmd/pwd.htm).


    Last login: Sat Aug 19 14:01:03 on ttys000
    Chriss-MacBook-Air:~ chris$ pwd
    /Users/chris
    Chriss-MacBook-Air:~ chris$ 


[`pwd`](https://www.tcl.tk/man/tcl8.4/TclCmd/pwd.htm) gives you the [`path`](https://www.computerhope.com/jargon/p/path.htm) of where you are on your computer. [`Pwd stands for print working directory`](http://www.unixguide.net/unix/faq/1.3.shtml). A lot of commands are shortened because they're quicker to type. Home directories are your starting folder, when you launch a terminal it starts in the home directory, /Users/chris is my home directory. In this directory is my Downloads, Desktop, Pictures ... etc folders. To see whats in your home directory type [`ls`](http://linuxcommand.org/lc3_man_pages/ls1.html).


    Chriss-MacBook-Air:~ chris$ ls
    Applications			Desktop				Library
    PreVeil-Testing			Villefort			school
    Chris Reuter's CV.pdf		Documents			Movies
    ProjectEuler			assignments			social.org
    Chris Reuter's CV1.pages	Downloads			Music
    Public				bower.json			tale-master
    Chris Reuter's CV1.pdf		Haskell				Pictures
    Purescript			lc.hs
    Chriss-MacBook-Air:~ chris$ 


As you can see I have a lot of folders in my home directory, you should see something similar.
If at any point you want to read more about a command, say [`ls`](http://linuxcommand.org/lc3_man_pages/ls1.html) you can type [`man ls`](https://www.tutorialspoint.com/unix_commands/man.htm)


    LS(1)                     BSD General Commands Manual                    LS(1)

    NAME
    ls -- list directory contents

    SYNOPSIS
     ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]

    DESCRIPTION
     For each operand that names a file of a type other than directory, ls displays
     its name as well as any requested, associated information.  For each operand that
     names a file of type directory, ls displays the names of files contained within
     that directory, as well as any requested, associated information.

     If no operands are given, the contents of the current directory are displayed.
     If more than one operand is given, non-directory operands are displayed first;
     directory and non-directory operands are sorted separately and in lexicographical
     order.

     The following options are available:

     -@      Display extended attribute keys and sizes in long (-l) output.

     -1      (The numeric digit ``one''.)  Force output to be one entry per line.
     This is the default when output is not to a terminal.

     -A      List all entries except for . and ...  Always set for the super-user.

     -a      Include directory entries whose names begin with a dot (.).

     -B      Force printing of non-printable characters (as defined by ctype(3) and
     current locale settings) in file names as \xxx, where xxx is the numeric value of
     the character in octal.

     -b      As -B, but use C escape codes whenever possible.

     -C      Force multi-column output; this is the default when output is to a
     terminal.

     -c      Use time when file status was last changed for sorting (-t) or
     long printing (-l).

     -d      Directories are listed as plain files (not searched recursively).

     -e      Print the Access Control List (ACL) associated with the file, if present,
     in long (-l) output.

     -F      Display a slash (`/') immediately after each pathname that is a
     directory, an asterisk (`*') after each that is executable, an at sign (`@')
     after each symbolic link, an equals sign (`=') after each socket, a percent sign
     (`%') after each whiteout, and a vertical bar (`|') after each that is a FIFO.

     -f      Output is not sorted.  This option turns on the -a option.

     -G      Enable colorized output.  This option is equivalent to defining CLICOLOR
     in the environment.  (See below.)

     -g      This option is only available for compatibility with POSIX; it is used
     to display the group name in the long (-l) format output
     (the owner name is suppressed).

     -H      Symbolic links on the command line are followed.  This option is assumed
     if none of the -F, -d, or -l options are specified.

     -h      When used with the -l option, use unit suffixes: Byte, Kilobyte,
     Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the number of
     digits to three or less using
             base 2 for sizes.

     -i      For each file, print the file's file serial number (inode number).

     -k      If the -s option is specified, print the file size allocation in
     kilobytes, not blocks.  This option overrides the environment variable BLOCKSIZE.

     -L      Follow all symbolic links to final target and list the file or
     directory the link references rather than the link itself.  This option cancels
     the -P option.

     -l      (The lowercase letter ``ell''.)  List in long format.  (See below.)
     If the output is to a terminal, a total sum for all the file sizes is output on
     a line before the long listing.

You can use the arrow keys to move up and down and type q to quit. That's a lot of information, but you don't have to memorize it! You can just look it up at any time. Man stands for manual if you haven't already guessed that.

So now we know how to see where we are and see what's there. To change where we are you can use[`cd`](http://linuxcommand.org/lc3_man_pages/cdh.html). So from my home directory let's say I want to go to my downloads. I can type cd Downloads/


    Chriss-MacBook-Air:~ chris$ cd Downloads/
    Chriss-MacBook-Air:Downloads chris$ 


The slash at the end means it's a directory. Directory is just computer nerd speak for a folder. Notice how the [`prompt`](https://en.wikibooks.org/wiki/Guide_to_Unix/Explanations/Shell_Prompt) changes to include Downloads, the prompt is the thing that occurs before the
`$` sign.

Let's see what's in my Downloads.


    Chriss-MacBook-Air:Downloads chris$ ls
    18620254_1987587898129254_5717056479093310776_n.jpg	Doc Apps—USSoc.docx
    alex.pem						2012-08-01 pro-se-reply-brief.August 2012.pdf
    Epic_53.0.2785.143 (1).dmg				captain-log
    547409.jpg						Epic_53.0.2785.143 (2).dmg
    captain-log-20170815T032940Z-001.zip			760731.jpg
    Epic_53.0.2785.143.dmg					chromedriver_mac64.zip
    760733.png						Firefox
    console-master.zip					760734.png
    Firefox 54.0.1.dmg					fish-1.1
    760738.jpg						Firefox.zip
    fish-1.1.tar.gz						Chris Reuter CV (1).pdf
    KeePass2.23.app						geckodriver-v0.18.0-macos.tar.gz
    Chris Reuter CV (2).pdf					KeePass2.23.zip
    github-recovery-codes.txt				Chris Reuter CV.pdf
    MacPass-0.6.2-alpha.zip					introtopython-ch0.pdf
    Chris Reuter's CV (1).docx				MacPass.app
    material-bliss-jekyll-theme-master			Chris Reuter's CV.docx
    Pop punk.docx						material-bliss-jekyll-theme-master.zip
    Chris Reuter's CV.pdf					RHITAthletics.jpg
    pass.kdbx      						Chris Reuter's CV1.docx
    Recon Docs USSocREV (1).docx				ruby-2.4.1.tar.gz
    Chris Reuter's CV1.pages				Recon Docs USSocREV.docx
    rubygems-2.6.12						Chris Reuter's CV1.pdf
    Remembering The Day After.REV'17.docx			rubygems-2.6.12.tgz
    Chris Reuter's CV3 (1).docx				TorBrowser-7.0.4-osx64_en-US.dmg
    tale-maste 2   	   					Chris Reuter's CV3 (1).pages
    USSoc.Project'17REV1.docx				tale-master
    Chris Reuter's CV3.docx					USSoc.Project'17REV2.docx
    tale-master (1).zip					College Counseling_Autobiography.pdf
    Unconfirmed 33452.crdownload				 tale-master-1.zip
    College Data Sheet.pdf					Unconfirmed 407272.crdownload
    xmoto-0.5.10-macosx.zip					Critical Essay Tips (1).docx
    Unconfirmed 751700.crdownload				Critical Essay Tips.docx
    X-Moto.app
    Chriss-MacBook-Air:Downloads chris$ 

Wow, that's a lot of stuff! I should really delete some of it.
To delete a file we can use the [`rm`](https://linux.die.net/man/1/rm) command. Be warned rm doesn't move things into the trash bin. It just deletes it. `once you rm something it is well and truly gone`. [`Consider yourself officially warned`](https://unix.stackexchange.com/questions/2677/recovering-accidentally-deleted-files?noredirect=1&lq=1). Most command line tools assume you know what your doing, so it's possible to break your OS if you delete the wrong file. I don't need all these copies of my CV so let's delete them. To delete Chris Reuter CV.pdf I can type `rm Chris\ Reuter\ CV.pdf`. The \ escapes the spaces. Spaces have a special meaning in the command line. Without the \\ rm would try to delete the file Chris, the file Reuter and the file CV.pdf. Since rm interprets everything separated by a space as a different file. So when we add a \ it means that the space just means a regular space and not a different file.


    Chriss-MacBook-Air:Downloads chris$ rm Chris\ Reuter\ CV.pdf
    Chriss-MacBook-Air:Downloads chris$ ls
    18620254_1987587898129254_5717056479093310776_n.jpg	Doc Apps—USSoc.docx
    X-Moto.app 						2012-08-01 pro-se-reply-brief.August 2012.pdf
    alex.pem						captain-log
    547409.jpg						Epic_53.0.2785.143 (2).dmg
    760731.jpg						Epic_53.0.2785.143.dmg
    captain-log-20170815T032940Z-001.zip			760733.png
    Firefox							chromedriver_mac64.zip
    760734.png						Firefox 54.0.1.dmg
    console-master.zip					760738.jpg
    Firefox.zip						fish-1.1
    Chris Reuter CV (1).pdf					KeePass2.23.app
    fish-1.1.tar.gz 					Chris Reuter CV (2).pdf
    KeePass2.23.zip					        geckodriver-v0.18.0-macos.tar.gz
    Chris Reuter's CV (1).docx				MacPass-0.6.2-alpha.zip
    github-recovery-codes.txt				Chris Reuter's CV.docx
    MacPass.app						introtopython-ch0.pdf
    Chris Reuter's CV.pdf					Pop punk.docx
    material-bliss-jekyll-theme-master			Chris Reuter's CV1.docx
    RHITAthletics.jpg					material-bliss-jekyll-theme-master.zip
    Chris Reuter's CV1.pages				Recon Docs USSocREV (1).docx
    pass.kdbx	   					Chris Reuter's CV1.pdf
    Recon Docs USSocREV.docx				ruby-2.4.1.tar.gz
    Chris Reuter's CV3 (1).docx				Remembering The Day After.REV'17.docx
    rubygems-2.6.12    					Chris Reuter's CV3 (1).pages
    TorBrowser-7.0.4-osx64_en-US.dmg			rubygems-2.6.12.tgz
    Chris Reuter's CV3.docx					USSoc.Project'17REV1.docx
    tale-maste 2	  					College Counseling_Autobiography.pdf
    USSoc.Project'17REV2.docx				tale-master
    College Data Sheet.pdf					Unconfirmed 33452.crdownload
    tale-master (1).zip					Critical Essay Tips (1).docx
    Unconfirmed 407272.crdownload				tale-master-1.zip
    Critical Essay Tips.docx				Unconfirmed 751700.crdownload
    xmoto-0.5.10-macosx.zip					Epic_53.0.2785.143 (1).dmg
    Chriss-MacBook-Air:Downloads chris$ 


Now it's gone. However, if I delete one file at a time it's going to take forever! Unix has a feature called the [`wild card`](http://www.robelle.com/smugbook/wildcard.html) which allows you to delete multiple files at once. If I want to delete all files starting with Chris\ Reuter. I can just type rm Chris\ Reuter*. The * is called a wild card and it means to delete every file that starts with Chris Reuter.


    Chriss-MacBook-Air:Downloads chris$ rm Chris\ Reuter*
    Chriss-MacBook-Air:Downloads chris$ ls
    18620254_1987587898129254_5717056479093310776_n.jpg	KeePass2.23.zip
    console-master.zip					2012-08-01 pro-se-reply-brief.August 2012.pdf
    MacPass-0.6.2-alpha.zip					fish-1.1
    547409.jpg						MacPass.app
    fish-1.1.tar.gz						760731.jpg
    Pop punk.docx						geckodriver-v0.18.0-macos.tar.gz
    760733.png						RHITAthletics.jpg
    github-recovery-codes.txt				760734.png
    Recon Docs USSocREV (1).docx				introtopython-ch0.pdf
    760738.jpg						Recon Docs USSocREV.docx
    material-bliss-jekyll-theme-master			College Counseling_Autobiography.pdf
    Remembering The Day After.REV'17.docx			material-bliss-jekyll-theme-master.zip
    College Data Sheet.pdf					TorBrowser-7.0.4-osx64_en-US.dmg
    pass.kdbx	 					Critical Essay Tips (1).docx
    USSoc.Project'17REV1.docx				ruby-2.4.1.tar.gz
    Critical Essay Tips.docx				USSoc.Project'17REV2.docx
    rubygems-2.6.12						Doc Apps—USSoc.docx
    Unconfirmed 33452.crdownload				rubygems-2.6.12.tgz
    Epic_53.0.2785.143 (1).dmg				Unconfirmed 407272.crdownload
    tale-maste 2       					Epic_53.0.2785.143 (2).dmg
    Unconfirmed 751700.crdownload				tale-master
    Epic_53.0.2785.143.dmg					X-Moto.app
    tale-master (1).zip					Firefox
    alex.pem						tale-master-1.zip
    Firefox 54.0.1.dmg					captain-log
    xmoto-0.5.10-macosx.zip					Firefox.zip
    captain-log-20170815T032940Z-001.zip			KeePass2.23.app
    chromedriver_mac64.zip
    Chriss-MacBook-Air:Downloads chris$ 

Now that that's gone. How about those .crdownload files? To delete these we can use the wild card again. To delete everything ending with .crownload I can use  `rm *.crdownload`. Now it pattern matches at the front.


    Chriss-MacBook-Air:Downloads chris$ rm *.crdownload
    Chriss-MacBook-Air:Downloads chris$ ls
    18620254_1987587898129254_5717056479093310776_n.jpg	KeePass2.23.app
    fish-1.1						2012-08-01 pro-se-reply-brief.August
    2012.pdf						KeePass2.23.zip
    fish-1.1.tar.gz						547409.jpg
    MacPass-0.6.2-alpha.zip					geckodriver-v0.18.0-macos.tar.gz
    760731.jpg						MacPass.app
    github-recovery-codes.txt				760733.png
    Pop punk.docx						introtopython-ch0.pdf
    760734.png						RHITAthletics.jpg
    material-bliss-jekyll-theme-master			760738.jpg
    Recon Docs USSocREV (1).docx				material-bliss-jekyll-theme-master.zip
    College Counseling_Autobiography.pdf			Recon Docs USSocREV.docx
    pass.kdbx						College Data Sheet.pdf
    Remembering The Day After.REV'17.docx			ruby-2.4.1.tar.gz
    Critical Essay Tips (1).docx				TorBrowser-7.0.4-osx64_en-US.dmg
    rubygems-2.6.12						Critical Essay Tips.docx
    USSoc.Project'17REV1.docx				rubygems-2.6.12.tgz
    Doc Apps—USSoc.docx					USSoc.Project'17REV2.docx
    tale-maste 2						Epic_53.0.2785.143 (1).dmg
    X-Moto.app 						tale-master
    Epic_53.0.2785.143 (2).dmg				alex.pem
    tale-master (1).zip					Epic_53.0.2785.143.dmg
    captain-log						tale-master-1.zip
    Firefox							captain-log-20170815T032940Z-001.zip
    xmoto-0.5.10-macosx.zip					Firefox 54.0.1.dmg
    chromedriver_mac64.zip					Firefox.zip
    console-master.zip
    Chriss-MacBook-Air:Downloads chris$ 



Pass.kdbx is an important password file so let's move that into the home directory to save it for later.
To move a file we use the command [`mv`](https://linux.die.net/man/1/mv). Mv takes two arguments the file to move and where it's going. To move my pass.kdbx file back into my home directory I can write `mv pass.kdbx ../`. `../` is a shortcut to move the file into the directory above it.


    Chriss-MacBook-Air:Downloads chris$ mv pass.kdbx ../
    Chriss-MacBook-Air:Downloads chris$ ls
    18620254_1987587898129254_5717056479093310776_n.jpg	Firefox.zip				
    chromedriver_mac64.zip					2012-08-01 pro-se-reply-brief.August 2012.pdf	
    KeePass2.23.app						console-master.zip
    547409.jpg						KeePass2.23.zip						
    fish-1.1						760731.jpg						
    MacPass-0.6.2-alpha.zip					fish-1.1.tar.gz
    760733.png						MacPass.app						
    geckodriver-v0.18.0-macos.tar.gz			760734.png						
    Pop punk.docx						github-recovery-codes.txt
    760738.jpg						RHITAthletics.jpg					
    introtopython-ch0.pdf					College Counseling_Autobiography.pdf			
    Recon Docs USSocREV (1).docx				material-bliss-jekyll-theme-master
    College Data Sheet.pdf					Recon Docs USSocREV.docx				
    material-bliss-jekyll-theme-master.zip			Critical Essay Tips (1).docx				
    Remembering The Day After.REV'17.docx			ruby-2.4.1.tar.gz
    Critical Essay Tips.docx				TorBrowser-7.0.4-osx64_en-US.dmg
    rubygems-2.6.12						Doc Apps—USSoc.docx
    USSoc.Project'17REV1.docx				rubygems-2.6.12.tgz
    Epic_53.0.2785.143 (1).dmg				USSoc.Project'17REV2.docx 
    tale-maste 2       					Epic_53.0.2785.143 (2).dmg
    X-Moto.app						tale-master
    Epic_53.0.2785.143.dmg					alex.pem
    tale-master (1).zip					Firefox
    captain-log						tale-master-1.zip
    Firefox 54.0.1.dmg					captain-log-20170815T032940Z-001.zip	
    xmoto-0.5.10-macosx.zip
    Chriss-MacBook-Air:Downloads chris$ 




Alex.pem and github-recover-codes.txt are also important files so let's move into my home for safe keeping.


    Chriss-MacBook-Air:Downloads chris$ ls
    18620254_1987587898129254_5717056479093310776_n.jpg	Firefox.zip						
    console-master.zip 2012-08-01 pro-se-reply-brief.August	2012.pdf		
    KeePass2.23.app    		  			fish-1.1
    547409.jpg						KeePass2.23.zip						
    fish-1.1.tar.gz						760731.jpg						
    MacPass-0.6.2-alpha.zip					geckodriver-v0.18.0-macos.tar.gz
    760733.png						MacPass.app		
    introtopython-ch0.pdf					760734.png					
    Pop punk.docx						material-bliss-jekyll-theme-master
    760738.jpg						RHITAthletics.jpg			
    material-bliss-jekyll-theme-master.zip              	College Counseling_Autobiography.pdf		
    Recon Docs USSocREV (1).docx				ruby-2.4.1.tar.gz
    College Data Sheet.pdf					Recon Docs USSocREV.docx		
    rubygems-2.6.12						Critical Essay Tips (1).docx		
    Remembering The Day After.REV'17.docx			rubygems-2.6.12.tgz
    Critical Essay Tips.docx				TorBrowser-7.0.4-osx64_en-US.dmg	
    tale-maste 2   						Doc Apps—USSoc.docx		
    USSoc.Project'17REV1.docx				tale-master
    Epic_53.0.2785.143 (1).dmg				USSoc.Project'17REV2.docx
    tale-master (1).zip					Epic_53.0.2785.143 (2).dmg\
    X-Moto.app						tale-master-1.zip
    Epic_53.0.2785.143.dmg					captain-log
    xmoto-0.5.10-macosx.zip					Firefox	
    captain-log-20170815T032940Z-001.zip			Firefox 54.0.1.dmg	
    chromedriver_mac64.zip
    Chriss-MacBook-Air:Downloads chris$ 


Those .jpgs are wallpapers from the movie [`The Grand Budapest Hotel`](https://www.youtube.com/watch?v=1Fg5iWmQjwk), which I highly recommend. I could just move those into the home directory, but let's move them into a wallpaper directory. To make a directory we can use the [`mkdir`](https://linux.die.net/man/1/mkdir) command. So let's make a wallpaper directory in the home folder.


    Chriss-MacBook-Air:Downloads chris$ mkdir ../wallpapers
    Chriss-MacBook-Air:Downloads chris$ mv *.jpg ../wallpapers/
    Chriss-MacBook-Air:Downloads chris$ ls
    2012-08-01 pro-se-reply-brief.August 2012.pdf	Firefox
    TorBrowser-7.0.4-osx64_en-US.dmg		introtopython-ch0.pdf
    760733.png					Firefox 54.0.1.dmg	
    USSoc.Project'17REV1.docx			material-bliss-jekyll-theme-master
    760734.png					Firefox.zip		
    USSoc.Project'17REV2.docx			material-bliss-jekyll-theme-master.zip
    College Counseling_Autobiography.pdf		KeePass2.23.app		
    X-Moto.app					ruby-2.4.1.tar.gz
    College Data Sheet.pdf				KeePass2.23.zip			
    captain-log					rubygems-2.6.12
    Critical Essay Tips (1).docx			MacPass-0.6.2-alpha.zip	
    captain-log-20170815T032940Z-001.zip		rubygems-2.6.12.tgz
    Critical Essay Tips.docx			MacPass.app		
    chromedriver_mac64.zip				tale-maste 2
    Doc Apps—USSoc.docx				Pop punk.docx			
    console-master.zip				tale-master
    Epic_53.0.2785.143 (1).dmg			Recon Docs USSocREV (1).docx	
    fish-1.1					tale-master (1).zip
    Epic_53.0.2785.143 (2).dmg			Recon Docs USSocREV.docx
    fish-1.1.tar.gz					tale-master-1.zip
    Epic_53.0.2785.143.dmg				Remembering The Day After.REV'17.docx	
    geckodriver-v0.18.0-macos.tar.gz		xmoto-0.5.10-macosx.zip
    Chriss-MacBook-Air:Downloads chris$ 



I don't need anymore of this stuff in my downloads, so let's nuke it. `Rm -rf *` will delete everything in a directory. The `-rf` just means to also delete the directories in the directories where deleting things.


    Chriss-MacBook-Air:Downloads chris$ rm -rf *
    Chriss-MacBook-Air:Downloads chris$ ls
    Chriss-MacBook-Air:Downloads chris$ 

This has only covered a hand full of commands, but I hope it was a stepping stone into the world of the command line. If you want a full list of commands on your system you can type `ls /usr/bin/`. There's a lot of them, but with `man` or your friend Google you can figure most of them out.

