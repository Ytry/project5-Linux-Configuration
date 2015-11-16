# project5-Linux-Configuration

CONNECTION
===========
Hostname: http://ec2-52-33-239-104.us-west-2.compute.amazonaws.com/

public IP: 52.33.239.104

note that the ip won't work for website only the host name. The public IP is only used for login

SSH Port: 2200

CONFIGURATION
=============

get and update packages:

sudo apt-get update
sudo apt-get upgrade

sudo apt-get dist-upgrade

Created user grader:

sudo adduser grader

Give user grader sudo permission:

sudo adduser grader sudo

change SSH port:
- sudo nano /etc/ssh/sshd_config
change ssh from 22 to 2200

DEPENDENCIES / PACKAGES INSTALLED
====================

- apache2
- python-setuptools
- libapache2-mod-wsgi
- postgresql
- python-dev
- git
- python-pip
- Flask
- postgresql-client
- postgresql-contrib
- psycopg2
- Flask-SQLAlchemy
- python-ouath2client
- python-psycopg2

UFW FIREWALL
============

Set default to deny incoming:
sudo ufw default deny incoming

Set default allow outgoing:
sudo ufw default allow outgoing

Allow ssh on port 2200:
sudo ufw allow 2200

Allow http on port 80:
sudo ufw allow 80

Allow NTP on port 123:
sudo ufw allow 123

Enable firewall:
sudo ufw enable

OTHER CONFIGURATIONS
======================

I created a postgresql user named catalog with catalog as the password, I created a database called catalog as well.
In my catalog.py, database_setup.py, and lotsofitems.py I had to change the database connection for sqllite to postgresql.

As far as configuration apache2 to serve my python web app, all the configuration changes I made were following this tutorial: https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps

RESOURCES AND CREDITS:
======================
I used many tutorials and resources from the udacity forums the lists of tutorials can be found below:
1. https://discussions.udacity.com/t/markedly-underwhelming-and-potentially-wrong-resource-list-for-p5/8587
2. https://discussions.udacity.com/t/project-5-resources/28343

