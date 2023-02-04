# Terminal Commands
a general and minimalised list of useful day-to-day commands for Linux Debian

## Contents
- [Nano](#nano)
    + [Open File](#open-file)
    + [Save File](#save-file)
    + [Search](#search)
- [Debian](#debian)
  * [User Management](#user-management)
    + [Get all user groups](#get-all-user-groups)
    + [Delete Groups](#delete-groups)
    + [User groups](#user-groups)
    + [Add User to group](#add-user-to-group)
    + [Remove User from group](#remove-user-from-group)
  * [Directory Management](#directory-management)
    + [Make Directory](#make-directory)
    + [Remove Directory](#remove-directory)
    + [Remove Directory and Contents](#remove-directory-and-contents)
    + [Change Permissions](#change-permissions)
    + [Change Ownership](#change-ownership)
    + [Change Group ownership](#change-group-ownership)
  * [Debug](#debug)
    + [Locate active process](#locate-active-process)
  * [Kill Certbot Process](#kill-certbot-process)
    + [Find active Certbot processes](#find-active-certbot-processes)
    + [Kill Certbot processes](#kill-certbot-processes)

## Nano
#### Open File
```terminal
$ sudo nano /directory/filename.ext
```

#### Save File
```terminal
CTRL + S
```

#### Search
```terminal
CTRL + W
```

## Debian

### User Management

#### Get all user groups
```terminal
$ sudo getent group
```

#### Delete Groups
```terminal
$ sudo groupdel groupName
```

#### User groups
```terminal
$ sudo groups username
```

#### Add User to group
```terminal
$ sudo usermod -a -G groupname username
```

#### Remove User from group
```terminal
$ sudo gpasswd –delete username group
```

### Directory Management
#### Make Directory
```terminal
$ sudo mkdir /path/of/directory/folder1
```

#### Remove Directory
```terminal
$ sudo rmdir /path/of/directory/folder1
```

#### Remove Directory and Contents
```terminal
$ sudo rm -r /path/of/directory/folder1
```

#### Change Permissions
```terminal
$ sudo chmod 775 /path/of/directory/folder1
```

#### Change Ownership
```terminal
$ sudo chown username:username  /path/of/directory/folder1
```

#### Change Group ownership
```terminal
$ sudo chgrp userGroupName -R /path/of/directory
```


### Debug
#### Locate active process
Search for Port 8080 processes
```terminal
$ sudo ps -ef | grep ':8080'
```

#### Kill Certbot Process
Error: Another instance of Certbot is already running.
Find active Certbot processes
````terminal
$ ps -ef | grep certbot
````
 
#### Kill Certbot processes
Note: The process id shown in this image may be different from your own.
````terminal
$ sudo kill 47666
````