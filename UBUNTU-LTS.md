// How to install Cameras on Ubuntu 16.04
	sudo add-apt-repository ppa:atareao/atareao
	sudo apt-get update
	sudo apt-get install cameras -y
	sudo apt-get remove cameras -y



//How to Write a Shell Script using Bash Shell in Ubuntu
	https://www.youtube.com/watch?v=He-5BpUGSag
	vim ListDir.sh
	press 'i' to insert
	#!/bin/bash

	echo "Welcome to Bash Shell Scripting";
	ls
	echo "This completes the listing of directories"

	press 'esc'
	:w
	:x	
	root@uJohn:~# chmod +x ListDir.sh
	root@uJohn:~# ./ListDir.sh

//Identifying Device that is missing driver
	root@uJohn:~# lshw | pastebinit

// check lists of hardware device installed
	root@uJohn:~# lspci
	root@uJohn:~# lsusb

// I cannot hear any sounds on the computer
	https://help.ubuntu.com/stable/ubuntu-help/sound-nosound.html.en

// How to Check Your RAM on Ubuntu
	root@uJohn:~# free -h
	john@uJohn:~$ sudo dmidecode --type memory | less

	
	root@uJohn:~# free -h
             	  total        used        free      shared  buff/cache   available
	Mem:           6.8G        4.6G        117M        387M        2.1G        1.4G
	Swap:          5.0G        113M        4.8G

	results when open phpstorm
	john@uJohn:~$ free -h
              	  total        used        free      shared  buff/cache   available
	Mem:           6.8G        5.2G        120M        404M        1.5G        811M
	Swap:          5.0G        240M        4.7G

// How to clean virus by command line scan in Ubuntu and Linux Mint
	https://www.fosslinux.com/2808/how-to-clean-virus-by-command-line-scan-in-ubuntu-linux-mint.htm

	-- Installing ClamAV
	sudo apt-get install clamav	

	-- Updating ClamAV Virus Signature Database
	sudo freshclam

// sublime text can't auto refresh the files/folders when added new one	
	- solution
		run sublime text in root user 
		ex: 
			open terminal
			sudo -i
			enter password
			type: subl
			solve: everytime you will add files and folder it automatically refresh because of permission root has it. :) 
			
// access root user (super user) via terminal
	sudo -i
	password:
	subl

	su
	password:
	subl - menus missing