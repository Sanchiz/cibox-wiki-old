Welcome to CIBox development workflow

Here you can see a quick how-to start current development workflow from scratch to first build for Pul Request.

* Clone repository to your local desktop. ```git clone https://github.com/propeoplemd/cibox.git```
* Create your own Ubuntu 14.04 powered virtual machine, vps or dedicated server and get its IP address
* Go into cloned ```cibox``` subfolder and add IP address of created machine to ```hosts``` file within a folder. It is simple ini file and there are examples of some testing hosts. Use unique name for your machine's ```IP```.
* Open ```jenkinsbox.yml``` with your favorite editor and replace ```CHANGE_ME``` placeholders (your host name from hosts file and project name without special characters and whitespaces).
* Run ```ansible-playbook jenkinsbox.yml``` from console of your desktop machine and wait untill all the software installed onto remote host. If there are errors during install or install been stalled for more than 5 minutes, try to stop ```CTRL-C``` and rerun the command untill it's done.
* Open ```github``` subfolder inside ```cibox``` folder and run ```ansible-playbook github.yml``` there. You'll get ```DEMO``` subfolder where all the files prepared for your future project. You should push content of the DEMO folder(not the folder itself) to github repository as is.
* After successfull run of ```jenkinsbox.yml``` playbook you should login into ```http://IP:8080``` Jenkins console with root credentials of your remote machine and change some unfilled settings for Jenkins itself and ```DEMO``` and ```*PR_BUILDER``` jobs.
* Open Jenkins system settings ```http://IP:8080/configure``` and add your own github bot user credentials and access token.
![API 1](http://druler.com/drulerfiles/github/api1.png)
![API 2](http://druler.com/drulerfiles/github/api2.png)
![BOT 1](http://druler.com/drulerfiles/github/bot1.png)
* Open Jenkins users credentials ```http://IP:8080/credential-store/domain/_/``` and change CHANGE_ME placeholdered user with your bot's credentials.
* ```DEMO``` and ```*PR_BUILDER``` jobs should have appropriate urls to github repository of your project. Please replace urls with CHANGE_ME placeholders to right ones. Also change user to your bot user within ```*PR_BUILDER``` settings
![BOT 2](http://druler.com/drulerfiles/github/bot2.png)
* login to your Jenkins host machine via console under ```jenkins``` user credentials and create ssh key
```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```. You should upload that key to github bot account for adding ability to access github repo from Jenkins server. You should [test connection](https://help.github.com/articles/generating-ssh-keys/#step-5-test-the-connection) and add github to known hosts before starting to use CI Box by this step. 
* Create New Pull request for your project repo and wait ~5 minutes. You should get changed status and build comment afterwards.
* For debugging Jenkins problems use ```http://IP:8080/log/all``` UI or ```/var/log/jenkins/jenkins.log``` on your Jenkins server. Also take a look at [Known Issues wiki page](https://github.com/propeoplemd/cibox/wiki/Known-Issues) for a possible issues.