## Branch Deleted on Github but still visible in VSCode? 

### solution 1 (recommended):
    git fetch --prune
    
    # example output on terminal
    - [deleted]         (none)     -> origin/<deleted_remote_branch>

### solution 2:

Branches removed from GitHub are just removed from GitHub. 
You still have local copy of branch on your machine. To delete local branch run:
    
    git branch -d <the_local_branch> 

p.s. There is no command in VS Code to do so, 
but you can start terminal in VSCode using View: Toggle Integrated Terminal command and run command from it.
