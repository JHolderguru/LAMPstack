## LAMP stack on AWS linux machine
#### installing Linux Apache2 MySql PhPAdmin
#### ssh into your ubuntu machine
```python

#Updrage your machine with all the latest packages
sudo apt update -y

sudo apt upgrade -y

#Set up the LAMP server

sudo apt install apache2 -y

sudo systemctl status apache2

sudo systemctl enable apache2


# Install MariaDB server and MySql


sudo apt install mariadb-server mariadb-client


sudo systemctl start mariadb

sudo systemctl status mariadb

sudo mysql_secure_installation

sudo systemctl restart mariadb



#install PHP
sudo apt install php php-mysql php-gd php-cli php-common -y


#Go to word press website and right click on the latest address and copy link address

sudo apt install wget unzip -y

sudo wget https://wordpress.org/latest.zip

sudo unzip latest.zip

#copy all the wordpress contents into the var directory
sudo cp -r wordpress/* /var/www/html/

cd /var/www/html/

ls
#change the permmisions
cd /var/www/html/

ls -l

sudo chown www-data:www-data -R /var/www/html/

#then you can see the ownership has been changed
ls -l

```

#### Now Copy the public IP address from the ubuntu instance to test.

```python
#run this command
sudo rm -rf index.html

refresh instance and this should take you to wordpress set up

#select english and go back to your bash command and run

sudo mysql -u root -p
 #expected output

 Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 37
Server version: 10.3.22-MariaDB-1ubuntu1 Ubuntu 20.04

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

#the wordpress website will require a database name, username , password , Database host  so the following commands are to create that

create database wordpress;

create user "wpadmin"@"%" identified by "wpadminpass";

grant all privileges on wordpress.* to "wpadmin"@"%";



```

#### on the owrdpress installation site input the details created to log in
```python

database: wordpress
username: wpadmin
host: localhost
table prefix (leave as default)

#expected output

All right, sparky! You’ve made it through this part of the installation. WordPress can now communicate with your database. If you are ready, time now to…
```
