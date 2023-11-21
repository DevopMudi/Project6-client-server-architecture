# Project6-client-server-architecture
IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

To demonstrate a basic client-server using MySQL Relational Database Management System (RDBMS), follow the below instructions

1.	Create and configure two Linux-based virtual servers (EC2 instances in AWS).

Server A name - `mysql server`

Server B name - `mysql client`


![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/d86b9409-9920-4242-ac8a-8e54da5f2e10)


2.	On mysql server Linux Server install MySQL Server software. Remember to note your password so you wont forget it
         
Interesting fact: MySQL is an open-source relational database management system. Its name is a combination of “My”, the name of co-founder Michael Widenius’s daughter, and “SQL”, the abbreviation for Structured Query Language.

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/c448d5d0-4725-4a17-9952-5cc55bc821b0)

3.	On mysql client Linux Server install MySQL Client software.

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/ef8466cc-41a9-40b2-813c-f415a5ac1d6a)


4.	By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses.

  	Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in

  	‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your mysql client.

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/a62d49da-619f-4317-9c06-baa53fffd703)

Remember to save rule as below

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/8dc8beb7-5371-4bad-bd9a-2c76978af740)

5.	You might need to configure MySQL server to allow connections from remote hosts.

  	 **sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf** afterwhich we **Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:**  as carried out in image below

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/3f1df252-32c9-449e-9e1c-c55e739c0b43)

 - change from the above to the below at the bind address area in the image

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/77646bf8-7c28-41b0-91d2-bf4be6270134)

6.	From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.

# steps to carry out option 6 above

- Install mysql_secure_installation on the server virtual machine by using this command : **sudo install mysql_secure_installation**

  ![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/d62bd291-4726-4593-8fae-01a733f959a9)

- create a mysql user on server after installation from above
  
  ![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/bd87ba44-f644-4436-a7f3-4211739ef1a8)

 - Configure mysql on server to allow connection from remote host(just confirm change from 0.0.0.0  )

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/f22a66f6-60ad-4d03-a439-ac362a6e113c)

- From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH

connect from client instance

Note: 
**By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses.**

**Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in**

**‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your mysql client.**


![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/159aba21-eadf-4cd7-819e-48c970e5ceb3)


![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/3f951556-759e-46f8-9c9e-cb5e7e28d14b)

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/8aad143c-5d6a-466c-a828-4d068e104408)

  
7.	Check that you have successfully connected to a remote MySQL server and can perform SQL queries

To do this:

copy private ipv4 of the server ip and put in the commandline of the client virtual machine using: **sudo mysql -u remote_user -h 172.31.20.176 -p** and enter the password created initially when creating data base.

![image](https://github.com/DevopMudi/Project6-client-server-architecture/assets/149855241/617b0aa6-db67-4970-9dfe-49682d735f43)

As can be seen on the above inital data created on the mysql server can be seen on the client showing as above






















































   
