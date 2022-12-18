<b>Jenkins and JS request counter</b>

The project shows the implementation of creating a Jenkins server on port 443 using docker compos, pipeline (Jenkinsfile),
as well as JS applications that count web requests and deposit them. based on CentOS operating system


1 - install docker and docker compos

https://docs.docker.com/engine/install/centos/ <br>
https://docs.docker.com/engine/install/linux-postinstall/
<hr>
2 - You will also need to install Java to run the Jenkins agent and git

<b>sudo yum install java-11-openjdk <br>
java -version

sudo yum install git</b>
<hr>
3 - Copy the docker composу file and run it with command
docker compose up -d

after the first launch, open the container log and look at the token, you will need it for the first login
<hr>
4 - Create a New Item, pipeline, copy the code from the jenkins file and enable the "GitHub hook trigger for GITScm polling" function
<hr>
5 - Create a new executor and name it agent1. copy the ready link, you can also run it on the same server
<hr>

6 - Now you can start the pipeline 
<hr>
<hr>

<b>From the current link https://github.com/asiamegic/js_counter-service
<br>
Main function of the script, the app receives and requests and displays their number</b><br>
<b>*</b> files are in the DEV branch<br>

There is a JS application project as well as a dockerbuild file for building the image.

JS application is launched as a server using the command<br><br>
<b>npm run start</b> <br>
or<br>
<b>node server.js/</b><br>
by default on port 3000. if you want to run on port 80 you need additional privileges on the server

you can test the application by typing in the browser<br><br>
<b>http://ip_address:your_port</b><br><br>
or curl commands <br>
<br>
<b>curl -X POST localhost:3000 <br>
curl -X GET localhost:3000 </b>
<br><br>
<hr>
<b>Thank you for visiting</b>
