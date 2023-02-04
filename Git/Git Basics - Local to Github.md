# Git Basics 
Setup, Configuration and Pushing local files to Github


## Contents
  * [Setting up and connecting with SSH](#setting-up-and-connecting-with-ssh)
    + [Generate SSH Key](#generate-ssh-key)
    + [Add SSH Key to your account](#add-ssh-key-to-your-account)
    + [Connect to git](#connect-to-git)
  * [Start the SSH Agent](#start-the-ssh-agent)
  * [Verify Key is in use](#verify-key-is-in-use)
  * [Add SSHkey to SSH-agent](#add-sshkey-to-ssh-agent)
  * [Git](#git)
    + [Add new remote](#add-new-remote)
    + [Set Remote](#set-remote)
  * [CRLF & LF](#crlf---lf)
    + [(Windows)](#-windows-)
    + [(MacOS & Linux)](#-macos---linux-)
    + [Add Files](#add-files)
    + [Commit files message](#commit-files-message)
    + [Check Status of files](#check-status-of-files)
    + [Checks remote before push](#checks-remote-before-push)
    + [Prompt Authentication token / sign-in](#prompt-authentication-token---sign-in)
  * [Git Commands Cheatsheat](#git-commands-cheatsheat)


## Setting up and connecting with SSH 
### Generate SSH Key
```
ssh-keygen -t rsa -b 4096 -C "user@domainname.com"
```

### Add SSH Key to your account
 1) Visit https://github.com/settings/keys
 2) Click New SSH Key
 3) Give it the same name as your SSH key, Select Authentivation Key
 4) Add the contents of your public key to the Key field
 5) Click Add New Key

Once the process above is done, open a terminal such as the Command Promp, Powershell, Windows Terminal or Git CMD. 

### Connect to git 
```
ssh -vT git@github.com -i c:/users/user/.ssh/.git/.github/2023-02-03-private-key
```

## Start the SSH Agent
```
ssh-agent -s
```

## Verify Key is in use
```
ssh-add -l -E sha256 
```  

## Add SSHkey to SSH-agent
If you're using SSH keys outside the standard directory
you can add them to the SSH-agent
```
ssh-add C:\Users\user\.ssh\.git\.github\2023-02-03-private-key
```


## Git
### Add new remote 
```
git remote add origin https://github.com/UserName/Repository.git
```

### Set Remote
```
git remote set-url origin https://github.com/UserName/Repository.git
```
## CRLF & LF
### (Windows) 
When storing code to a repository, git should remove carriage return, when pulling code from the repository, git will add the carriage return to the local repository.
```
git config --global core.autocrlf true
```

### (MacOS & Linux) 
Git will modify the end of line when storing the project on the repository and remove the Carriage return when updating the repository.
```
git config --global core.autocrlf input
```

### Add Files
```
git add .
```

### Commit files message
```
git commit -m "Initial"
```

### Check Status of files
```
git status -s
```

### Checks remote before push
```
git remote -v
```

### Prompt Authentication token / sign-in
```
git push origin main
```

## Git Commands Cheatsheat
