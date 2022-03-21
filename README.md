## Github Useful Commands

#### How to inital a Github Repo:
```python
git init 
git remote add origin git@github.com:Andy/Git_Command.git # add remote Github repo, origin is the alias of git@github.... You can use another name, but it's not suggest.
git remote rm git@github.com:Andy/Git_Command.git  #remove remote git repo if you find the url is wrong.
git push -u origin master # push local master to remote Github
    if you use https you need to type the user name and password for authentication
    if you use ssh you need below step.(recommended)
        ssh-keygen -t rsa -b 4096 -C andy@github.com # generate a ssh key, it including public_key(id_rsa.pub) and private_key(id_rsa)
        cd ~/.ssh  # the dir that key located
        cat id_rsa.pub # copy the key
        paste to Github. 
            Use for one Repo: go to Repo -> Settings -> Deploy keys - add deploy key
            Use for all Repos: go to user profile-> Settings -> SSH and GPG keys->New SSH key
```


#### How to view/config repo info:
```python
git clone git@github.com:Andy/Git_Command.git # download the remote repo to local
git clone git@github.com:Andy/Git_Command.git repo_name  # set a repo name for download repo
git status  # check local repo status if has anything changes(Check remote by 'git remote show origin')
git diff    # check the diff between local workspace and local cache
git show    # Show various types of objects
git reflog   # check all the commit history
git log    # view local log and commit_id(sha1), will not display reset commit info
git log origin/master # view remote log and commit_id(sha1)
git log -3  # view the latest 3 logs
git log --graph  # view log by graph
git log --graph --pretty=oneline --abbrev-commit # view the brief log by graph
git config --list  # vew git config
git config --global user.name "andy"    # config your Global user_name and email 
git config --global user.email andy@example.com
git config –local -l     # view git local level config info
git config –global -l     # view git global level config info
git config –system -l     # view git system level config info
git branch     # view branch info
git branch -v     # v stands for verbose, view branch info and display commit id
git branch -a     # list all the branchs including detached branch(游离分支)
git branch -av
git remote -v      # view remote branch info
git remote show     # Check remote server list
git remote show origin      # view remote repo info
git remote rm git@github.com:Andy/Git_Command.git  #remove remote git repo, but please use git remove -v to check info before that
git tag      # check all tag info 
git tag tagname       # set a tag 
git blame andy.txt    # check who modified this file
git config --global alias.ch checkout     # set an alias for checkout command(store in ~/.gitconfig file)
git log --graph --pretty=oneline --abbrev-commit  # pretty the commit log
git remote set-url origin git@github.com:andy/k8s.git  # change the git remote url when the repo url is changed
git remote -r  # list remote branch list 
git remote -a   # list all remote branch
git branch -v -a  # v abbrev list all remote branch with abbrev of commit
git checkout renovate/github.com-spf13-viper-1.2  # switch to one branch

``` 

#### How to push a file to remote repo:
```python
touch andy.txt
vim andy.txt
git add .
git add -m "add a new file"
git push orgin master
```

#### How to push the local branch to the remote repo:
```python
git checkout -b new_branch    #Create a new branch and chechout to that branch(equal to 'git branch new_branch & git checkout new_branch')
touch andy.txt
vim andy.txt
git add .
git add -m "add a new file"
git push -u origin new_branch     # push local new_branch to remote repo(origin)
or git push --set-upstream origin new_branch
```
#### How to pull the remote branch to local repo:
```python
git pull     # pull all the remote branch to local tracking branch
git branch -av      # check all the branches(local and local tracking)
git checkout -b dev origin/dev     # checkout tracking branch origin/dev to local branch dev
or git checkout -b dev --track origin/dev
or git checkout -b --track origin/dev # omit the name, will use default remote branck name
```

#### How to discard the change after git add:
```python
touch andy.txt
vim andy.txt
git add .
git restore --staged andy.txt
rm andy.txt
git status
``` 
#### How to discard the change after git commit:
```python
touch andy.txt
vim andy.txt
git add .
git commit -m "Add a new file"
git checkout . or git checkout -- andy.txt
git status
``` 
#### How to remove the file after git commit:
```python
touch andy.txt
vim andy.txt
git add .
git commit -m "Add a new file"
git rm andy.txt
git commit -m "delete andy.txt"
git status
``` 
#### How to discard the change after git rm:
```python
touch andy.txt
vim andy.txt
git add .
git commit -m "Add a new file"
git rm andy.txt
git reset head andy.txt
git checkout -- andy.txt
git status

``` 
#### How to change commit comments :
```python
touch andy.txt
vim andy.txt
git add .
git commit -m "Add a new file"
git commit --amend -m "New comments"

``` 
#### How to create/delete/checkout local branch:
```python
git branch --list
git branch -v
git branch newbrach   # Create a new branch
git checkout -b newbrach  # Create a new branch and chechout to that branch
git branch -d newbranch   # Delete a branch, but require merge commit first
git branch -D newbranch   # Force delete a branch ignore the unmerge commit
git merge newbranch   # Require checkout to master then meger branch to master

``` 
#### How to delete remote branch:
Way1: delete branch from Github protal
Way2: delete by CLI
```python
git push origin source:destination    # syntax
git push origin :dev  # delete remote dev branch by empty source to replace remote branch
or git push origin --delete dev

``` 
#### How to delete useless local tracking branch:

```python
git remote prune origin --dry-run   # dryrun the useless branch
git remote prune origin     # remove the useless branch

``` 

#### How to ignore a file and don't commit to remote:
```python
cd ~/gitfolder
touch .gitignore
vim .gitignore     # Add file name to this file, it's also support wildcard.
    andy.txt       # ignore andy.txt file
    *.txt          # ignore all txt files
    !.txt          # ignore all the files except txt file
    dir/*          # ignore dir 
    dir/*/*.txt
    dir/**/*.txt   # ** stands for all the subdir
git merger --no-ff master # no fast forward

``` 
#### How to rollback commit:
```python
vim andy.txt
git commit -am "add new file"    # -am will add file then make the comments. Equal to (git add . + git commit -m "add new file"), but can not use for the first time after the file create. 
git log      # get the commit SHA1(commit_id)
Revert:
git revert commit_id     # commit_id is like 029302c63663....
Reset:
git reset --hard HEAD^      # revert to last version, ^^ go back to version
git reset --hard HEAD~n     # going back n commits before HEAD
git reset --hard -f HEAD~4  # force move
git reset --hard commit_id    # going back the specified version by commit_id
Note: revert will keep the commit control version history, reset will not keep the version history, but it can be find by 'git reflog' or '--keep'. A revert is the best choice for undoing changes

``` 

#### Checkout Version Shuttle(checkout 版本穿梭):
```python
git log or reflog     # get the commit history
git checkout commit_id    # checkout to specified commit version
Note: Don't suggest to change the pervious commit file. If you want to change file in pervious version, suggest to create a new branch.


``` 

#### How to rename branch:
```python
git branch -m master master2      # -m stands for move/rename. 

``` 

#### Git Stash(保存现场): 
```python
git checkout -b newbranch
touch andy.txt
vim andy.txt 
git add .
git checkout master   # this step will get error, you need to commit the change or stash the change
git stash or
git stash save ‘先保存再切换分支’
git checkout master    # checkout to other branch, and finish the job
git checkout newbranch    # checkout back to your branch
git stash list     # view the save version
git stash pop      # restore the last stash content, and will delete the stash version(view by git stash list)
    git stash pop stash@{n}     # restore the specified stash content
git stash apply      # restore the last stash content, but will keep the stash version(view by git stash list)
    git stash drop stash@{0}     # delete the stash history manually
    git stash apply stash@{n}    # restore the specified stash content

``` 

#### Git Tag: 
```python
tag is work for the whole project
git tag # view tags
git tag tagname # create a tag
git tag -a V2.0 -m "first tag" # create a tag with comments
git tag -d V2.0 # delete tag
git tag -l 'V2.0' # query tag
git tag -l 'V*'  # fuzzy query tag
git push origin v2.0 # Only push local tag to remote repo(releases)
git push origin v3.0 v4.0 # push multi tags
git push origin --tags # push all tags to remote repo
git push origin refs/tags/v1.0:refs/tags/v1.0
git pull # pull all the tags from remote to local
git fetch origin tag v4.0 # fetch a specified tag from remote to local
git push origin :refs/tags/v1.0 # remove remote tag v1.0

```

#### Git Diff: 
```python
git diff # 暂存区和工作区比较差异
git diff readme.md  # check the new change of the file
git diff commit_if # 对象区和工作区比较差异
git diff HEAD # 最新的对象区和工作区比较差异
git diff --cached commit_id # 对象区和暂存区比较差异
git diff --cached HEAD # 最新的对象区和暂存区比较差异
Note: git diff is only check the local repo info, not for check the diff between local and remote repo(check remote repo by 'git remote show origin')

```

#### Git merge & git rebase

```python
直接git merge: 
git checkout -b dev
git add .
git commit -m "add new file"
git checkout master
git merge dev

先git rebase 再 git merge:
git checkout -b dev
git commit -ad "add a new file"
git rebase master
git add .
git rebase --continue
git checkout master
git merge dev

总结
git merge 操作合并分支会让两个分支的每一次提交都按照提交时间（并不是push时间）排序，并且会将两个分支的最新一次commit点进行合并成一个新的commit，最终的分支树呈现非整条线性直线的形式
git rebase操作实际上是将当前执行rebase分支的所有基于原分支提交点之后的commit打散成一个一个的patch，并重新生成一个新的commit hash值，再次基于原分支目前最新的commit点上进行提交，并不根据两个分支上实际的每次提交的时间点排序，rebase完成后，切到基分支进行合并另一个分支时也不会生成一个新的commit点，可以保持整个分支树的完美线性
另外值得一提的是，当我们开发一个功能时，可能会在本地有无数次commit，而你实际上在你的master分支上只想显示每一个功能测试完成后的一次完整提交记录就好了，其他的提交记录并不想将来全部保留在你的master分支上，那么rebase将会是一个好的选择，他可以在rebase时将本地多次的commit合并成一个commit，还可以修改commit的描述等
最后
如果你想要你的分支树呈现简洁，不罗嗦，线性的commit记录，那就采用rebase, 否则，就用merge吧

参考链接：https://www.jianshu.com/p/6960811ac89c


```

#### Rename the default branch from main to master(If you have a local clone, you can update it by running)
```
git branch -m main master
git fetch origin
git branch -u origin/master master
git remote set-head origin -a

```
#### Clean git cached for save repo data
```
git rm --cached template/charts

```
#### Mix
```
git clone -b release-0.8 --single-branch git@github.com:prometheus-operator/kube-prometheus.git  # 指定下载版本
```

Refer: https://www.liaoxuefeng.com/wiki/896043488029600
