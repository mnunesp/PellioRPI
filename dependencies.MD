# This is the dependencies file for PellioRPI. It is meant to help us manage dependencies involved with the project. 

## Installation 
In order to run and test Pellio, the user will need to have some dependencies installed. 

..* Python 3
..* Django
..* MySQL 


### Installing MySQL on Microsoft Windows
The easiest way to get MySQL is to use the top installer at https://dev.mysql.com/downloads/windows/installer/

The installer can also be reached by going to https://www.mysql.com/ then clicking on
Downloads
Community
MySQl on Windows
and MySQL installer

After downloading the installer, run it.

Click Next
Select Devoloper Default and click Next

Click Yes if asked to skip missing extras
Click Execute to download all components
Click Next
Click Next
Click Next
Click Next

Enter a password for MySQL at the top. We will use this connect to the server.
Add a User at the botton. This will be you.
Click Next

Uncheck run at startup if desired (This reccomended unless you will be working 24/7)
Click Next
Click Next
Click Execute
Click Finish
Click Next
Click Finish
Click Next
Click Check
Click Next
Click Execute
Click Finish
Click Next
Click Finish

### Running and stopping the server on Windows
If you just installed MySQL the server should already be running. Unchecking "run at startup" during installation will require you to start the server manually when you boot your computer.
To start or stop the server, go to your taskbar in the botton right and click on the MySQL Notifier, go to MySQL57, and click on either Start or Stop.

### Creating the database
Open the MySQL Shell that was installed and enter:
`\sql` to switch to sql mode
`\connect root@localhost;` to connect to the server
Enter your password created during installation
`\create database pelliodb;`
`\show databases;` and check if pelliodb has been created

### Downloading mysqlclient
Lastly, you will need mysqlclient for Django to actually access the database.
In the command line enter:
`pip3 install mysqlclient`



## Known Issues 
### Making the python3 manage.py runserver work on MacOS
Since the project is using python 3 and MacOS usually defaults python to be 2.7, there can be issues when trying to setup the files. If you find that you have all the files installed but can't run the server using runserver, try running the following commands: 
`sudo ln -s /usr/local/Cellar/openssl/1.x.x/lib/libssl.1.x.x.dylib /usr/local/lib`
`sudo ln -s /usr/local/Cellar/openssl/1.x.x/lib/libssl.1.x.x.a /usr/local/lib`
`sudo ln -s /usr/local/Cellar/openssl/1.x.x/lib/libcrypto.1.x.x.dylib /usr/local/lib`
`sudo ln -s /usr/local/Cellar/openssl/1.x.x/lib/libcrypto.1.x.x.a /usr/local/lib`

This will allow your python to look in the right places for dependencies. 
