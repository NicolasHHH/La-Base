# FORK

## 什么是fork?
- fork 指服务端代码仓库克隆，在自己的账户中新建一个仓库，包含了原来上游仓库（up-stream repo）的全部内容。
- fork 是 github 的操作，而不是git的操作。
- fork 后的仓库属于自己，可以任意提交 或通过PR（Pull Request）贡献回原仓库。
- fork 直译为分叉，即从fork时刻起开始内容不再同步。

## fork后如何merge/diff ？
场景：上游仓库更新，需要同步到自己的forked

方法一：
  1. 在forked中点击 `New pull request`
  2. 将左边base改成自己的forked <- head fork改成原来的项目
  3. `Create pull request`
  4. `Merge pull request`
  5. 本地 git pull
     
方法二：
  - `Sync fork` 
  - 参考： https://docs.github.com/zh/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork

## 如何将本地仓库的上游从官方仓库替换为自己的forked？

    # check upstream
    $ git remote -v 
  
    origin  git@github.com:<OFFICIAL>/<repo>.git (fetch)
    origin  git@github.com:<OFFICIAL>/<repo>.git (push)
  
    # replace remote
    $ git remote set-url origin git@github.com:<USER>/<forked_repo>.git
  
    $ git remote -v
  
    origin  git@github.com:<USER>/<forked_repo>.git (fetch)
    origin  git@github.com:<USER>/<forked_repo>.git (push)
  
    $ git fetch
    $ git pull
  
