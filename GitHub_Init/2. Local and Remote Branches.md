# Local and Remote Branches

last edit: 12 Aug 2021

### Branches

    # list local branches
    git branch
    # list all branches (including the remote ones)
    git branch -a

    # change to a specific branch
    git checkout <branchname>

    # create a new branch 
    git checkout -b <branchname>

    # delete a branch
    git branch -d <branchname>
    # forced delete
    git branch -D <branchname>


    # merge a branch to current branch
    git merge <branch_to_merge_to_current>
   
### Tags

    # add tags to a branch
    git tag <v1.0>
    git tag
    git checkout v1.0

    git tag <tagName> 
    git push origin <tagName> 

    # check local tags
    git tag 
    git tag -l
    # check remote tags
    git ls-remote --tags origin

    # delete local tags
    git tag -d <tagName>
    # delete remote tags
    git push origin :<tagName>

    # rename local tag before commit
    git tag -d <oldTagName>
    git tag <newTagName>
    git push origin <newTagName>
    # rename after commit
    git tag -d <oldTagName>
    git push origin :<oldTagName>
    git tag <newTagName>
    git push origin <newTagName> 
    

### git push & branches

    # specify the local branch and the remote branch
    git push origin <local branch name>:<remote branch name>
    # if they share the same name 
    git push origin <shared branch name>

    # set an upstream
    git branch --set-upstream-to=origin/<remote branch> <local branch> 
    # since then, we could simpy do git push/pull without args


    # Set upstream branch using git push
    git push -u <remote> <branch>
    git push --set-upstream <remote> <branch>
    git branch --vv
    # example 
    $ git branch --set-upstream-to=origin/remote_branch1 local_branch1
    $ : Branch 'local_branch1' set up to track remote branch 'remote_branch1' from 'origin'.
    $ git branch -vv
    * local_branch1 44a277a [origin/remote_branch1: behind 1] Update README.md
      master        44a277a [origin/master] Update README.md
   
   
 ### local remote mismatch : local_branch —> remote_branch (upstream set)
 
    git push
    fatal: The upstream branch of your current branch does not match
    the name of your current branch.  To push to the upstream branch
    on the remote, use

        git push origin HEAD:remote_branch1

    To push to the branch of the same name on the remote, use

        git push origin local_branch1
        
### How to merge ?

    # merge on remote 
    # github branch <Pull_requests> 
    git checkout master/main
    git pull

    # merge at local
    git checkout <branchname>
    # ... do sth 
    git add .
    git commit -m "msg"
    git checkout main/master
    git merge <branchname> -m "msg"
  
### Verify & overview (commit history)

    git log
