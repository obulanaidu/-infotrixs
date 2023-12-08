AWS CLOUD TASK

# Prerequisites:
I created AWS Account
# Login to AWS console
TASK:
MONOLOTHIC ARCHITECTURE: DEPLOY WORDPRESS AND MYSQL ON SAME INSTANCE
AMI-UBUNTU, EC2 INSTANCE TYPE;T2 MICRO (TASK REQUIREMENT I USED)

# LAUNCHED Ec2 instance below
AMI-Ubuntu, t2 micro-ec2 instance type,
created key pair, configured the security groups HTTP, HTTPS, SSH
# By using the public ip address of my launched ec2 instance connected
by SSH for mobixtream.
#1. Install Apache server on Ubuntu
sudo apt install apache2

2. Install Php runtime and php mysql connector
sudo apt install php libapache2-mod-php php-mysql

3. Install MySQL server
sudo apt install mysql-server

4. Login to MySQL server
sudo mysql -u root

5. Change authentication plugin to mysql_native_password (change the password to something
strong)
ALTER USER 'root'@localhost IDENTIFIED WITH mysql_native_password by
'Testpassword@124';

6. Create a new database user for wordpress (change the password to something strong)
CREATE USER 'wp1_user'@localhost IDENTIFIED BY 'Testpassword@124';

7. Create a database for wordpress
CREATE DATABASE wp;
8. Grant all privilges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp1_user'@localhost;
9.exit
We can navigate apache2 server by using ip address active or not.
It shows this image if it is working
9. Download wordpress
cd /tmp
wget https://wordpress.org/latest.tar.gz

10. Unzip
tar -xvf latest.tar.gz

11. Move wordpress folder to apache document root
sudo mv wordpress/ /var/www/html

12. Change to that directory to check whether wordpress is moved to document root and the
path for that dirctory is.

cd /var/www/html

13.To list the files
Ls
NOTE: here by navigating our ip /wordpress we can have wordpress installation screen.here by
clicking on lets go,we give db name,user,password,db host,table-prefix and submits.
here it shows unable to write wp-config.php file.here copy the below text of php file and go
back to terminal.
14.command to change in to the word press directory
cd wordpress/

15.created a new file with wp-config.php and paste the text of php file here and save it.
nano wp-config.php

Now installed wordpress by giving site title:WELCOME PAGE,username,password,email here
and click on install wordpress.it will take to wordpress login page.
Finally here by navigating browser ip address/wordpress it shows the wordpress website that is
deployed.
THIS IS THE OUTPUT OF MONOLOTHIC ARCHITECHTURE OF MY WEBSITE WITH URL
http://13.234.31.177/wordpress/
