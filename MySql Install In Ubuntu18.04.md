# To install mysql server on ubuntu 18.04 follow the step by step

### STEP -01: 
<pre>$ sudo apt update</pre>

`Running sudo apt-get update (or sudo aptitude update ) updates this on your local system. This is the step that actually retrieves information about what packages can be installed, including what updates to currently installed packages packages are available, from Internet sources.`

### STEP-02:
<pre>$ sudo apt install mysql-server</pre>
`Install MySql server pacakages`

### STEP-03:

<pre>$ sudo systemctl status mysql</pre>

`Once the installation is completed, the MySQL service will start automatically. To check whether the MySQL server is running, type:`
![image](https://user-images.githubusercontent.com/53125546/172546499-fd2607af-f2f6-4888-9e0c-6ff3563f901f.png)

### STEP 04: Securing Mysql server
`MySQL server package comes with a script called mysql_secure_installation that can perform several security-related operations. Run the below command`

<pre>$ sudo mysql_secure_installation</pre>

`You will be asked to configure the VALIDATE PASSWORD PLUGIN which is used to test the strength of the MySQL users’ passwords and improve the security. There are three levels of password validation policy, low, medium and strong. Press ENTER if you don’t want to set up the validate password plugin.`

`On the next prompt, you will be asked to set a password for the MySQL root user. Once you do that the script will also ask you to remove the anonymous user, restrict root user access to the local machine and remove the test database. You should answer “Y” (yes) to all questions.`

### STEP-05: Login as root
`To interact with the MySQL server from the command line you can use the MySQL client utility which is installed as a dependency of the MySQL server package.`

`In Ubuntu 18.04 systems running MySQL 5.7 (and later), the root user is authenticated by the auth_socket plugin by default.`

`The auth_socket plugin authenticates users that connect from the localhost through the Unix socket file. This means that you can’t authenticate as root by providing a password.`

`To log in to the MySQL server as the root user type:`

<pre>sudo mysql</pre>

![image](https://user-images.githubusercontent.com/53125546/172548326-04707a52-7c5d-4cd8-a9be-f5eb0f1662e9.png)

`If you want to login to your MySQL server as root from an external program such as phpMyAdmin you have two options.`

`The first one is to change the authentication method from auth_socket to mysql_native_password. You can do that by running the following command:`

<pre>mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'very_strong_password';
mysql>FLUSH PRIVILEGES;
</pre>

### STEP-06: For Remote connection
`Edit the mysql configuration file`
<pre>sudu nano /etc/mysql/mysql.conf.d/mysqld.cnf</pre>

`after execute the command comment the default blind adress ipaddress`
![image](https://user-images.githubusercontent.com/53125546/172553949-ea7f13d3-b32c-4862-a1e3-4b5933fb1040.png)

`If you don't have the default blind adress then execute the below image command`
![image](https://user-images.githubusercontent.com/53125546/172554227-e650ff57-27e5-49c8-be58-fdf8068690f2.png)

### STEP-07: Restart the mysql service

<pre>$ sudo systemctl restart mysql</pre>

### STEP-08: Bydefault you can't access the root user so you need to create new database user using below command
`create a user on you root user`
<pre> mysq> create user "username"@"%"identified by "password"</pre>

