# Github Basics
last edit : 21 Aug 2021

Global Configurations
    
    #global configs
    git config --global user.name "username"
    git config --global user.email "mail"
    git config --global init.defaultBranch main

Init from remote
    
    # git clone
    # locate a destination folder and clone from target website
    cd ~/<dir>
    git clone <https://github.com/example-url.git>

Init from local
    
    # locate a folder to init
    cd ~/<dossier>
    git init
    # check init
    ls -a 
    # a shadow folder named .git appears


    # add all files in the folder, wait for commit
    git add .
    # add a specific file, wait for commit 
    git add <filename>


    # commit 
    git commit -m "msg"

Connect local to remote

    # generate ssh key
    ssh-keygen -t ed25519 -C "your_email@example.com"
    # generate ssh key option 2
    ssh-keygen -t rsa -C "your_email@example.com"

    cd ~/.ssh
    vim id_ed25519.pub 
    # for option 2 : id_rsa.pub
    # copy to github -> setting -> deploy key -> add new key -> allow write

    # github repository link
    git remote add origin <git@...>

    # change default branch name from "master" to "main
    git config --global init.defaultBranch main
    git branch -M main

    git push -u origin main
    # origin signifies the remote repo to push to
    # if error/fatal: pull remote files down to local first
    git pull --rebase origin main 
    # push again 
   
 Branches management 
    
    # more detailed info here in "Local and Remote Branches"
 
     # list local branches
     git branch
     # list all branches (including the remote ones)
     git branch -a

     # change to a specific branch
     git checkout <branchname>

     #create a new branch 
     git checkout -b <branchname>
  
 Other Operations 
 
     # delete a file (previously commited)
      git rm <filename>

      # rename a file
      git mv <oldname> <newname>
      # which is equivalent to 
      # change the filename manually
      git rm <oldname>
      git add <newname>
      git commit -m "rename"

      # cancel a commit
      git rm --cached filename
    
    
