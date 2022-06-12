# CICD with Jenkins using ngnix server
#the demo project is succeded, here i am successfully build the workflow of CI/CD using jenkins and docker.
# please go and check the code and it runs perfectly fine.
please follow the steps:-
-install Docker in VM
-Install Jenkins in VM:-
 Run the following Commands:
1) sudo apt-get update -y
2) wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
3) sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ >
/etc/apt/sources.list.d/jenkins.list'
4) sudo apt update
5) sudo apt install openjdk-8-jdk -y
6) sudo apt install jenkins -y
7) sudo systemctl start jenkins
8) sudo systemctl status jenkins

After installing jenkins in local system create pipeline and add the git hub https link then build it.
