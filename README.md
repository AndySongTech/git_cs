## Github Useful Commands
### 重要知识点
#### How to inital a Github Repo:
```python
git init 
git remote add origin reponame
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
