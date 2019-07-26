
// restart docker
	sudo service docker restart
	sudo systemctl start docker

	
//can't start or restart docker
	john@uJohn:~/Desktop/devbox-linux$ sudo service docker restart
	Failed to add /run/systemd/ask-password to directory watch: No space left on device

	answer:
	//fixed
	sudo lsof -K | grep inotify | (less||more||pg)
	sudo -i
	echo 1048576 > /proc/sys/fs/inotify/max_user_watches
	root@uJohn:~# exit
	logout
	john@uJohn:~$ 

//List all containers (only IDs)
	docker ps -aq

//shows all stopped docker containers
	docker ps -a | grep Exit
	sudo docker ps -a
	docker container list --all

//checks all running container
	docker ps


//Stop all running containers
	docker stop $(docker ps -aq)

// Remove all containers
	docker rm $(docker ps -aq)
