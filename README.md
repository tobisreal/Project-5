# Project-5
# CLIENT-SERVER ARCHITECTURE WITH MYSQL

Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another.

In their communication, each machine has its own role: the machine sending requests is usually referred as "Client" and the machine responding (serving) is called "Server".

A simple diagram of Web Client-Server architecture is presented below:
![Screenshot (89)](https://user-images.githubusercontent.com/111396874/211891172-915e31f0-b3e4-45d9-973e-a2fc8291e41c.png)
In the example above, a machine that is trying to access a Web site using a Web browser or simply ‘curl’ command is a client and it sends HTTP requests to a Web server (Apache, Nginx, IIS or any other) over the Internet.

If we extend this concept further and add a Database Server to our architecture, we can get this picture:
![Screenshot (90)](https://user-images.githubusercontent.com/111396874/211891360-ed46e457-8d58-49e3-9451-f0d5c1fa8509.png)

In this case, our Web Server has a role of a "Client" that connects and reads/writes to/from a Database (DB) Server (MySQL, MongoDB, Oracle, SQL Server or any other), and the communication between them happens over a Local Network (it can also be an Internet connection, but it is a common practice to place Web Server and DB Server close to each other in a local network).

The setup on the diagram above is a typical generic Web Stack architecture that you have already implemented in previous projects (LAMP, LEMP, MEAN, MERN), this architecture can be implemented with many other technologies – various Web and DB servers, from small Single-page applications SPA to large and complex portal

## IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).
## TASK – Implement a Client-Server Architecture using MySQL Database Management System (DBMS).
To demonstrate a basic client-server using MySQL Relational Database Management System (RDBMS), follow the below instructions
* Create and configure two Linux-based virtual servers (EC2 instances in AWS).
```
Server A name - `mysql server`
Server B name - `mysql client`
```

* On mysql server Linux Server install MySQL Server software. ``sudo apt-get install mysql-server``

* On mysql client Linux Server install MySQL Client software. ``sudo apt-get install mysql-client``

* By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses. Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.
* You might need to configure MySQL server to allow connections from remote hosts.
```
sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
```
Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:
![Screenshot (91)](https://user-images.githubusercontent.com/111396874/227394122-199cf8bb-5998-4e2d-a55b-153e26207354.png)
* From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.
You can use the command below
```
mysql -h [remote_server_ip] -u [username] -p
```
* Check that you have successfully connected to a remote MySQL server and can perform SQL queries:


