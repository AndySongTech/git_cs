## Github Useful Commands
### 重要知识点
#### How to inital a Github Repo:
```python
git init 
git remote add origin git@github.com:AndySongTech/Github_Command.git
git push -u origin master
```
    
#### How to push a file to remote repo:
```python
touch andy.txt
vim andy.txt
git add .
git add -m "add a new file"
git push orgin master
```
#### How to discard the change affer git add:
```python
touch andy.txt
vim andy.txt
git add .
git restore --staged andy.txt
rm andy.txt
git status
``` 
#### How to discard the change affer git commit:
```python
touch andy.txt
vim andy.txt
git add .
git commit -m "Add a new file"
git checkout . or git checkout -- andy.txt
git status
``` 
#### How to remove the file affer git commit:
```python
touch andy.txt
vim andy.txt
git add .
git commit -m "Add a new file"
git rm andy.txt
git commit -m "delete andy.txt"
git status
``` 
#### How to discard the change affer git rm:
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
#### How to create/delete/checkout branch:
```python
git branch --list
git branch -v
git branch newbrach   # Create a new branch
git checkout -b newbrach  # Create a new branch and chechout to that branch
git branch -d newbranch   # Delete a branch, but require merge commit first
git branch -D newbranch   # Force delete a branch igore the unmerge commit
git merge newbranch   # Require checkout to master then meger branch to master

``` 
#### How to ignore a file and don't commit to workspace:
```python
cd ~/gitfolder
touch .gitignore
vim .gitignore # Add file name to this file, it's also support wildcard
    andy.txt # ignore andy.txt file
    *.txt # ignore all txt file
    !.txt # ignore all the files except txt file
    dir/* # ignore dir 
    dir/*/*.txt
    dir/**/*.txt # ** stands for all the subdir
git merger --no-ff master # no fast forward

``` 
