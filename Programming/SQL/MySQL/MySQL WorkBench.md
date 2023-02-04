# Connecting to mysql workbench with SSH Quick setup guide

# Contents
- [About](#about)
  - [MySQL Workbench](#mysql-workbench)
  - [MySQL Workbench setup](#mysql-workbench-setup)
  - [PuTTY SSH](#putty-ssh)
- [Database](#database)
- [SSH](#ssh)
- [Setup and connecting to MySQL Workbench](#setup-and-connecting-to-mysql-workbench)
- [References](#references)

# About

This guide aims to assist with setting up MySQL workbench 8.0 via SSH tunnelling.
 The result should allow you to access a live websites database and perform SQL queries directly to the database through the workbench UI.

## MySQL Workbench

[https://www.mysql.com/products/workbench/](https://www.mysql.com/products/workbench/)

## MySQL Workbench setup

[https://help.krystal.uk/cpanel-advanced-topics/how-to-connect-to-my-sql-using-my-sql-work-bench](https://help.krystal.uk/cpanel-advanced-topics/how-to-connect-to-my-sql-using-my-sql-work-bench)

## PuTTY SSH

[https://help.krystal.uk/cpanel-advanced-topics/shell-access-to-your-server-using-ssh-pu-tty-for-windows](https://help.krystal.uk/cpanel-advanced-topics/shell-access-to-your-server-using-ssh-pu-tty-for-windows)

# Database

To start off you will need to create a database on your chosen platform.

| Detail | Credential |
| --- | --- |
| Database | example\_db |
| Username | example\_user |
| Password | \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* |

# SSH

Next you will need to create an SSH private key and authorize the certificate created.
 After creating the Key you should enable SSH with your host if you have not done so.

On the creation of your key, you should download the key and store somewhere safe.

| Detail | Credential |
| --- | --- |
| SSH Host | Example.com:22 |
| SSH Username | user |
| SSH Password | \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* |

**Note**
 Some hosts have SSH services disabled by default and may require enabling.
 You will need to search for documentation on your providers website or contact them directly.

# Setup and connecting to MySQL Workbench

Open MySQL workbench and open a new connection.
 You will then be prompt to enter your credentials and add your SSH private key.

 ![](RackMultipart20230129-1-2al84r_html_ed12bac2b8371ad2.jpg)

After entering your details, test connection.
 If it works you can then close the manage connections interface.

T ![](RackMultipart20230129-1-2al84r_html_dbb72c96eeafdcf0.png) o connect, simple click the connection you setup and you will be able to begin creating queries to manage your database.

# References

**There are no sources in the current document.**