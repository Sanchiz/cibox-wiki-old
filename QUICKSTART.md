Welcome to CIBox development workflow

Here you can see a quick how-to start current development workflow from scratch to first build for Pul Request.

* Clone repository to your local desktop. ```git clone https://github.com/propeoplemd/cibox.git```
* Create your own Ubuntu 14.04 powered virtual machine, vps or dedicated server and get its IP address
* Go into cloned ```cibox``` subfolder and add IP address of created machine to ```hosts``` file within a folder. It is simple ini file and there are examples of some testing hosts. Use unique name for your machine's ```IP```.
* Open ```jenkinsbox.yml``` with your favorite editor and replace ```CHANGE_ME``` placeholders (your host name from hosts file and project name without special characters and whitespaces).
* Run ```ansible-playbook jenkinsbox.yml``` from console of your desktop machine and wait untill all the software installed onto remote host. If there are errors during install or install been stalled for more than 5 minutes, try to stop ```CTRL-C``` and rerun the command untill it's done.
* Open ```github``` subfolder inside ```cibox``` folder and run ```ansible-playbook github.yml``` there. You'll get ```DEMO``` subfolder where all the files prepared for your future project. You should push content of the DEMO folder(not the folder itself) to github repository as is.
* After successfull run of ```jenkinsbox.yml``` playbook you should login into ```http://IP:8080``` Jenkins console with root credentials of your remote machine and change some unfilled settings for Jenkins itself and ```DEMO``` and ```*PR_BUILDER``` jobs.