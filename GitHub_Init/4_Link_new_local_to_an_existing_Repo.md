### SSH Generation

    ssh-keygen -t rsa -C "email"
    
    # Creation of a .ssh folder in which we find the file id_rsa.pub
    # press enter all the way untill you see a randomart image. 
    # Open the ".pub" file (the one with a longer name) in terminal

    cat id_rsa.pub
    
    # copy all the content from "ssh_rsa" to the email address

### Add the SSH key to github

1. Click on your icon at the top right corner of the website
2. Open <Settings>
3. Find SSH and GPG keys
4. Add - New SSH KEY (green button)
5. Insert a title as you like
6. paste the code you've just copied
7. Finish
    
### Check SSH locally 
    
    # create a new folder anywhere you like
    # open it in the terminal 
    
    cd "folder path"
    
    git init
    git config --global init.defaultBranch main
    git branch -m main
    
    # the default principle branch name is "master"
    # it's recommended to change it to "main" with the commands above
    # in order to match the branch naming on github

    
    # global configs (for first time initiations)
    
    git config --global user.name "name"
    git config --global user.email "email"


    # link the folder to a remote ssh address 
    
    git remote add origin git@github.com:XXXXXXX/xxxxxxx.git
    
    # make sure you add the ssh address instead of the http one

    
    # Sychronization
    
    git pull origin main --allow-unrelated-histories
    
    # master in the place of main if you haven't change the principle branch name
    # to check your local branch names : git branch
    # (yes/no/..) : yes

    
    # set push upstream to enable upload
    
    git branch --set-upstream-to=origin/main
    

### Problem Shooting

- git@github.com: Permission denied (publickey). Could not read from remote repository. Please make sure you have the correct access rights and the repository exists.`
    
Solution : delete the key you've just created on github, then redo from the beginning and pay attention to the notice "press enter all the way untill you see a randomart image". This problem is probably caused by the wrong placement of the file id_rsa.pub which should be located in the .ssh folder in the root folder (ls -a to check)


