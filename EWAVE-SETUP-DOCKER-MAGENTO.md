


// step to setup docker inlinux: devbox-linux 

// clone
root@uJohn:~/Desktop git clone https://github.com/ewave-com/devbox-linux.git
// access create magento2 under projects folder and create 2 files .env and .env-projects.json
root@uJohn:~/Desktop/devbox-linux/projects/magento2
	- .env
	- .env-projects.json

if there's an error like
 Current MySQL port 3306  is using 
 use this links below 
 https://stackoverflow.com/questions/11583562/how-to-kill-a-process-running-on-particular-port-in-linux/32592965
 stop apache services : systemctl stop apache2.service, systemctl stop mysqld
 or change MySQL port: locate -i config.inc.php 3306 -3307 
 	ex: 

 		$dbport = 3307;	// change port number	
	    if (!empty($dbport) || $dbserver != 'localhost') {
	        $cfg['Servers'][$i]['connect_type'] = 'tcp';
	        $cfg['Servers'][$i]['port'] = $dbport;
	    }

 if sudo: docker-compose: command not found
 	run this command: sudo curl -L "https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

 	run this : 
 		if need permission run this
 			john@uJohn:~/Desktop/devbox-linux$ chmod +x start-devbox.sh

 		root@uJohn:~/Desktop/devbox-linux# sudo bash start-devbox.sh

 	then it will install all you need 




############################################# other way to fix some errors
//serach file
locate -i my.cnf
locate -i config.inc.php

root@ubuntu:~# mysql -uroot -p
mysql> show global variables like 'port%';


fuser -k 3306/tcp

sudo /etc/init.d/mysql start

# adding new group
$ sudo groupadd docker

# adding user to the 'docker' group
$ sudo gpasswd -a ${your_username} docker

# restart the docker (documentation suggests to use 'docker.io' instead of 'docker',
# for me both variants work just fine!
$ sudo service docker restart

################# DOCKER 
// add to : .env-project.json 
https://stash.ewave.com/scm/mv/magento-2.3.1-ee.git
https://stash.ewave.com/scm/mv/magento-2.3.1-ee.git

//checks all running container
docker ps

//stops multiple docker containers
docker stop 4537fa6b4138 08517034b94f 8628d77d5d62

//shows all stopped docker containers
docker ps -a | grep Exit
sudo docker ps -a
docker container list --all

//List all containers (only IDs)
docker ps -aq

//Remove all images
docker rmi $(docker images -q)

// http://blog.baudson.de/blog/stop-and-remove-all-docker-containers-and-images
// error on running : root@uJohn:~/Desktop/devbox-linux# sudo bash start-devbox.sh
Generating autoload files
----------------------------------------------
 * * * * * * *  Select project * * * * * * * * 
----------------------------------------------
1) magento2
2) Exit
Please input number  --->:1
 Containers form project magento2 is running now 
 You cann't run already running containers 
--- solution
	//Stop all running containers
	1. docker stop $(docker ps -aq)

	// Remove all containers
	2. root@uJohn:~/Desktop/devbox-linux# docker rm $(docker ps -aq)
	
	// run 
	3. root@uJohn:~/Desktop/devbox-linux# sudo bash start-devbox.sh



	// setup magento2 with docker



	master branch

	Username for 'https://stash.ewave.com': albert.osmena
	Password for 'https://albert.osmena@stash.ewave.com': albert03

	Parameter            Value     
	-------------------- ---------- 
	DB Name              magento2  
	Admin Backend Path   admin     
	Admin User           admin     
	Admin Password       ewave123  

	[OK] Permissions has been updated                                                                                                               
	nginx-reverse-proxy

	-----------------------------------------------------------------------
	 * * * * * * *  URL's, ports and container names   * * * * * * * * 
	-----------------------------------------------------------------------

	-------------------------- SERVICES -----------------------------------
	Mailhog URL : http://127.0.0.1:8025
	Portainer URL : http://127.0.0.1:9999
	-----------------------------------------------------------------------

	-------------------------- WEB ----------------------------------------
	Project name URL : http://magento2.local
	Web container : magento2_web
	Varnish container : magento2_varnish
	-----------------------------------------------------------------------

	-------------------------- MYSQL --------------------------------------
	MYSQL container : magento2_mysql
	MYSQL connect  [from LOCAL PC]:
	Server IP : 127.0.0.1
	Server Port : 3307
	Credentials : root / root 
	MYSQL connect  [from containers]: mysql -uroot -proot -hdb magento2
	-----------------------------------------------------------------------

	-------------------------- REDIS --------------------------------------
	Redis container : magento2_redis
	-----------------------------------------------------------------------

	-------------------------- ALL CONTAINERS -----------------------------
	magento2_varnish
	magento2_mysql
	magento2_web
	magento2_redis
	mailer
	nginx-reverse-proxy
	portainer
	-----------------------------------------------------------------------
	root@uJohn:/home/john/Desktop/DOCKER/devbox-linux# 



	//restart docker

	https://askubuntu.com/questions/828779/failed-to-add-run-systemd-ask-password-to-directory-watch-no-space-left-on-dev
	john@uJohn:~$ sudo systemctl start docker
	[sudo] password for john: 
	Failed to add /run/systemd/ask-password to directory watch: No space left on device

	//fixed
	john@uJohn:~$ sudo lsof -K | grep inotify | (less||more||pg)
	john@uJohn:~$ sudo -i
	root@uJohn:~# echo 1048576 > /proc/sys/fs/inotify/max_user_watches
	root@uJohn:~# exit
	logout
	john@uJohn:~$ 



	//old permission
	drwxr-xr-x  7 root         root         4096 Jul 24 10:59 .
	drwxr-xr-x  3 root         root         4096 Jul 22 17:19 ..
	drwxr-xr-x  8 root         root         4096 Jul 23 12:20 configs
	drwxr-xr-x  5 guest-6um78r guest-6um78r 4096 Jul 24 10:52 db
	-rw-r--r--  1 root         root         2045 Jul 24 10:05 docker-compose.yml
	-rw-r--r--  1 root         root          239 Jul 24 10:05 docker-redis-image.yml
	drwxr-xr-x  5 root         root         4096 Jul 23 12:20 dumps
	-rwxrwxrwx  1 www-data     www-data     2983 Jul 24 10:05 .env
	-rw-r--r--  1 root         root         1184 Jul 24 09:59 .env-project.json
	drwxr-xr-x  2 root         root         4096 Jul 23 12:20 es
	drwxrwxrwx 15 www-data     www-data     4096 Jul 24 10:34 public_html

	//new permission
	root@uJohn:~/Desktop/devbox-linux/projects/magento2# sudo chown -R john:www-data . 
	root@uJohn:~/Desktop/devbox-linux/projects/magento2# ls  -al
	total 44
	drwxr-xr-x  7 john www-data 4096 Jul 24 10:59 .
	drwxr-xr-x  3 root root     4096 Jul 22 17:19 ..
	drwxr-xr-x  8 john www-data 4096 Jul 23 12:20 configs
	drwxr-xr-x  5 john www-data 4096 Jul 24 10:52 db
	-rw-r--r--  1 john www-data 2045 Jul 24 10:05 docker-compose.yml
	-rw-r--r--  1 john www-data  239 Jul 24 10:05 docker-redis-image.yml
	drwxr-xr-x  5 john www-data 4096 Jul 23 12:20 dumps
	-rwxrwxrwx  1 john www-data 2983 Jul 24 10:05 .env
	-rw-r--r--  1 john www-data 1184 Jul 24 09:59 .env-project.json
	drwxr-xr-x  2 john www-data 4096 Jul 23 12:20 es
	drwxrwxrwx 15 john www-data 4096 Jul 24 10:34 public_html

	// locate files
	root@uJohn:~# sudo docker exec -it magento2_web /bin/bash
	www-data@774c9c61c414:~$ ls -al
	www-data@774c9c61c414:~$ cd public_html
	www-data@774c9c61c414:~/public_html$ ls  -al


	
P
################# END DOCKER 

//restart docker-compose
sudo service docker restart
sudo systemctl start docker

sudo bash start-devbox.sh
cd projects/magento2
/usr/local/bin/docker-compose
sudo systemctl stop apache2.service
sudo systemctl restart apache2
systemctl stop mysqld


-- https://askubuntu.com/questions/538208/how-to-check-opened-closed-ports-on-my-computer
160

There's a few parameters to netstat that are useful for this :

-l or --listening shows only the sockets currently listening for incoming connection.
-a or --all shows all sockets currently in use.
-t or --tcp shows the tcp sockets.
-u or --udp shows the udp sockets.
-n or --numeric shows the hosts and ports as numbers, instead of resolving in dns and looking in /etc/services.
You use a mix of these to get what you want. To know which port numbers are currently in use, use one of these:

netstat -atn           # For tcp
netstat -aun           # For udp
netstat -atun          # For both
-- end



//errors on 
Varnish cache server, Error 503 Backend fetch failed
- sudo systemctl stop docker
- sudo systemctl restart apache2 : use this if you'll need to start apache2


