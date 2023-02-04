# Git Basics 
Setup, Configuration and Pushing local files to Github

## Generate SSH Key
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

### If you're using SSH keys outside the standard directory
### you can add them to the SSH-agent
```
ssh-add C:\Users\user\.ssh\.git\.github\2023-02-03-private-key
```



## Add new remote (do once)
```
git remote add origin https://github.com/UserName/Repository.git
```

## Set Remote
```
git remote set-url origin https://github.com/UserName/Repository.git
```

## (Windows) When storing code to a repository, git should remove carriage return, when pulling code from the repository, git will add the carriage return to the local repository.
```
git config --global core.autocrlf true
```

## (MacOS & Linux) Git will modify the end of line when storing the project on the repository and remove the Carriage return when updating the repository.
```
git config --global core.autocrlf input
```

## Add Files
```
git add .
```

## Commit files message
```
git commit -m "Initial"
```

## Check Status of files
```
git status -s
```

## Checks remote before push
```
git remote -v
```

## Prompt Authentication token / sign-in
```
git push origin main
```
