# **Laravel 9.1**
## **Starter Guide**

October 31, 2022  
Grant Kellie

## Contents
- [About](#about)
- [What is Laravel](#what-is-laravel)
- [Laravel features](#laravel-features)
- [Setup Requirements](#setup-requirements)
- [Visual Studio Code](#visual-studio-code)
- [Apache Web Server](#apache-web-server)
- [SSH (Secure Shell) : Optional](#ssh--secure-shell----optional)
- [Composer](#composer)
- [Windows Terminal (Optional)](#windows-terminal--optional-)
- [Installing Laravel](#installing-laravel)
- [Securing Laravel](#securing-laravel)
- [Setup Laravel](#setup-laravel)
- [Model, View, Controller](#model--view--controller)
  * [About](#about-1)
  * [Routes](#routes)
  * [Model](#model)
    + [Database](#database)
  * [View](#view)
  * [Controller](#controller)

## About

This guide is being created a reference resource for starting a basic Laravel website and to get an understanding in what Laravel is and what it can offer for website developers.

Documentation for Laravel 9.X can be found at [https://laravel.com/docs/9.x#meet-laravel](https://laravel.com/docs/9.x#meet-laravel)

The guide assumes you understand or experience with managing Apache web servers, use of Terminal commands, SSH, Composer & Cpanel.

In the case you do not have much or any experience, resources will be supplied to aid in the progression of the guide.

This guide does not cover command line interfaces or use of the Terminal in full and may use shortcut methods to achieve the desired outcome.

## What is Laravel

Laravel is a PHP Web Application Framework with an expressive and elegant syntax.
 The framework was created by [Taylor Otwell](https://github.com/sponsors/taylorotwell?frequency=recurring) back in June 2011.

 Since then it has grown to be one of the most used and well documented PHP frameworks available to the open source community.

 While the framework is free to use

## Laravel features

- **Progressive development** of Laravel enables growth for you and your applications requirements.
- **Horizontal Scalable** for a high volume of concurrent users by making use of built-in caching systems and distributed systems such as Redis and Amazon web services serverless technology.
- **Community developers** help contribute to the ecosystem of Laravel by creating accessible packages for

## Setup Requirements

The minimum requirements for setting up Laravel require a web server (preferably Apache), MySQL Database and Composer which is accessible through a terminal.

 This guide will make use of Cpanel for various parts of the guide.

## Visual Studio Code

Code Editor
[https://code.visualstudio.com/](https://code.visualstudio.com/)

## Apache Web Server

Xampp is web server often run-on local environments containing the core packages to build dynamic websites.
These packages include Apache, MariaDB, PHP 8 & Perl web server
[https://www.apachefriends.org/index.html](https://www.apachefriends.org/index.html)

## SSH (Secure Shell) : Optional

A protocol that allows you to securely remote access into another machine, this process can involve a user & password login, bug generally good practice would involve the use of SSH public/private key pairs.

SSH can be used through tools such as Windows Terminal or even in VSCode with the Remote SSH plugin.

[https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)

## Composer

A dependency manager for PHP that allows you to manage and add packages from repositories such as Packagist.

[https://getcomposer.org/](https://getcomposer.org/)

[https://getcomposer.org/doc/00-intro.md#installation-windows](https://getcomposer.org/doc/00-intro.md#installation-windows)

## Windows Terminal (Optional)

Windows Terminal is an excellent customizable alternative to PowerShell, Command Line, and other Terminal tools you may have installed on your System.

[https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-gb&gl=gb](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-gb&gl=gb)

## Installing Laravel

Once you have setup your code editor, Apache web server, composer, you will be able to install Laravel the following using a Terminal.

```terminal
composer create-project laravel/laravel directoryPath/projectName
```

## Securing Laravel

Laravel on installation will come with sensitive files that can be accessed directly from the URL of your site.

Without any configuration to a .htaccess file, example.com/.env will be completely exposed for public access, making sensitive global variables such as database credentials exposed.

If your Apache server is configured correctly, you can create and modify a .htaccess file in the root directory to help protect your sensitive files from client side access.

see: [RewriteRule Flags](https://httpd.apache.org/docs/2.4/rewrite/flags.html#:~:text=from%20external%20redirects.-,F%7Cforbidden,being%20downloaded%20from%20your%20server).

```
# Secure files by forbidding access (visiting file URL)
# https://httpd.apache.org/docs/2.4/rewrite/flags.html
RewriteRule^(.env)- [F]
```

## Setup Laravel

By default, your server may not load up the Laravel's home page.
To do so you may need to create and modify a .htaccess file in the root directory.

See: [How to change my document root to a folder using .htaccess](https://www.ecenica.com/support/answer/how-to-change-my-document-root-to-a-folder-using-htaccess/)

![image](https://user-images.githubusercontent.com/94868357/216785555-c017671a-068d-4750-a7ac-1f272b126662.png)

```terminal
# Point to Laravel DocumentRoot / Bootstrap
RewriteEngine on
RewriteCond%{HTTP\_HOST}^example.com$ [NC,OR]
RewriteCond%{HTTP\_HOST}^www.example.com$
RewriteCond%{REQUEST\_URI}!public/
RewriteRule(.\*)/public/$1 [L]
```

![](RackMultipart20230204-1-uv3f50_html_a2e605826ea7dd6a.png)The script above will point to where Laravel's index.php and bootstrap are located.
 on success will load the home page on your domain.

## Model, View, Controller

### About

MVC or Model, View, Controller is an architectural design pattern in use with laravel to sperate the database layer, frontend layer and backend logic.

### Routes

### Model

While most systems in PHP use SQL queries to preform create, read, update, and delete (CRUD) actions, Laravel makes use of a system called Object relational mapping (ORM) with a package known as Eloquent ORM to communicate and interact with the database.

See: [Eloquent ORM 5.0](https://laravel.com/docs/5.0/eloquent)

#### Database

### View

### Controller
