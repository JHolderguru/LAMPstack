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
