# # bWAPP-installation-2024
## This Tutorial for php version that higher than 7.0 

[![Ask Me Anything !](https://img.shields.io/badge/Ask%20me-anything-1abc9c.svg)](https://github.com/ghozt666)

**Created by [Salman Ghozy Nashrullah](https://github.com/ghozt666) from [University of Brawijaya Malang](https://www.linkedin.com/in/salman-ghozy-nashrullah-3b80882a6/)**

"bWAPP, or buggy web application, is a free and open-source web application deliberately designed to be insecure. It aids security enthusiasts, developers, and students in discovering and preventing web vulnerabilities (Fauzan, F. (2021, July 27).

## Installing bWAPP on Kali Linux & Ubuntu
### Download bWAPP from the Official Website
1. Go to [bWAPP download page](http://www.itsecgames.com/download.htm).
2. Click on "Download Latest Version".

### Prepare the Environment
1. Go to the downloads directory:
    ```sh
    cd /Downloads
    ```

### Extract bWAPP
1. Unzip the bWAPP zip file ke direktori /var/www/html:
    ```sh
    sudo unzip -d /var/www/html bWAPPv2.2.zip
    ```

### Install MySQL
1. Check if MySQL is installed:
    ```sh
    mysql -V
    ```
2. Update the system before installation:
    ```sh
    sudo apt-get update -y
    ```
3. Install MySQL if not installed:
    ```sh
    sudo apt install mysql-server
    ```
4. Start MySQL:
    ```sh
    sudo systemctl start mysql
    ```
5. Enable MySQL on startup:
    ```sh
    sudo systemctl enable mysql
    ```
6. Check MySQL status:
    ```sh
    sudo systemctl status mysql
    ```
    Press `Q` to exit.

### Install Apache2
1. Check if Apache2 is installed:
    ```sh
    apache2 -v
    ```
2. Update the system before installation:
    ```sh
    sudo apt-get update -y
    ```
3. Install Apache2 if not installed:
    ```sh
    sudo apt install apache2
    ```
4. Start Apache2:
    ```sh
    sudo systemctl start apache2
    ```
5. Enable Apache2 on startup:
    ```sh
    sudo systemctl enable apache2
    ```
6. Check Apache2 status:
    ```sh
    sudo systemctl status apache2
    ```

### Prepare bWAPP
1. Navigate to the bWAPP directory:
    ```sh
    cd bWAPP
    ```
2. Give all permissions to these directories:
    ```sh
    sudo chmod -R 777 bWAPP
    ```
### Configure the Application
1. set username, password and name as you like.
    ```sh
    $db_server = "localhost";
    $db_username = "ghozt";
    $db_password = "ghozt666";
    $db_name = "bWAPP";
    ```
### Create and setup a MySQL Database:
1. create a MySQL user 
    ```sh
    create user 'ghozt'@'localhost'identified by 'ghozt666';
    ```
2.  set up for privileges
    ```sh
    grant all privieges on bWAPP.*to'ghozt'@'localhost'identified by 'ghozt666';
    ```
3. create database;
    ```sh
    create database bWAPP;
    exit;
    ```
4. restart mysql service
    ```sh
    sudo service mysql restart
    ```
### Adjusment
1. Remove '!' mark, before installing bWAPP
    ```sh
    mousepad bWAPP/install.php
    
    before
    //checks if the database 'bWAPP' already exists
    if(!mysqli_select_db($link,"bWAPP"))

    After
    //checks if the database 'bWAPP' already exists
    if(mysqli_select_db($link,"bWAPP"))
    ```
Note: The reason removing '!' mark is, it could leads to blank screen. Carefully remove the mark.


# Reference
- Fauzan, F. (2021, July 27). bwapp on ubuntu. Medium. https://medium.com/@farrasfauzannn/1-0-bwapp-on-ubuntu-bacbox-3ee6685014a7
- Hunter, H. (2024, August 22). Installation procedure to bWAPP on Linux: A Step-by-Step Guide for Bug Bounty Hunters. Medium. https://dkcyberz.medium.com/installation-procedure-to-bwapp-on-linux-a-step-by-step-guide-for-bug-bounty-hunters-883b0d23be2a



