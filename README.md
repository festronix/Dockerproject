# dockerproject

This is my first docker project based on mysql and wordpress. 

Pre-configurations which are needed for making a project

I am using RedHat Enterprise Linux (RHEL 8). In that I have installed Docker Software using command. we can use any Operating system and but the thing is you should have docker installed in that OS.

 For Docker Installation : I used command
 
 docker pull wordpress:5.1.1-php7.3-apache
 
For MYSQL Installation : I used command docker pull mysql:5.7

 There are some of the important things before starting the project like Disable the firewall:
why we are disabling the Firewall?

Firewall sometimes used to block some networks and it will create issue for us. For disabling Firewall use command systemctl stop firewalld.

Then use systemctl start docker to start Docker Services

After downloading images which we will required for the projects you can see those images by docker images command. You will see two images there one is of Wordpress and one is of mysql 5.7.

In this project we are doing Multi Tier Architecture . Here wordpress is dependent on mysql because mysql is database server and all the data will be stored there. We need to launch mysql first. 

There are two steps to do this first is manual and another is one by using docker compose.

First type the command docker run -it mysql:5.7 . It will show you that we need to specify the variables like username or password.

 Use docker run -d -it -e MYSQL_ROOT_PASSWORD= ****** -e MYSQL_USER= ******* -e MYSQL_PASSWORD= ****** -e MYSQL_DATABASE=******** -v mysql_storage:/var/lib/mysql --name ***** mysql:5.7
 
Now its time to check that database is created or not then you have to install MySQL cilent software in your base OS. 

Type docker ps then it will show you the containers then type docker inspect **** (starting letter of your IP) |grep IP. Then type which mysql it will show you the location then type rpm -qf / location then yum install mysql then type mysql -h IP -u **** -p*****

Now its time to check that database is created or not then you have to install MySQL cilent software in your base OS. 

Type docker ps then it will show you the containers then type docker inspect **** (starting letter of your IP) |grep IP. Then type which mysql it will show you the location then type rpm -qf / location then yum install mysql then type mysql -h IP -u **** -p*****

then type ifconfig to get the IP of your OS and copy that IP and add your port number will show you the website.
