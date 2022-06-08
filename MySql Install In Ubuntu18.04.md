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

