# Git configuration
```
git config --global --list
git config --global user.name "John Doe"
git config --global user.email johndoe@myemail.com 
git config --global core.editor vim
git config --list
git config user.name
git config --global color.status auto
git config --global color.branch auto
git config --global color.interactive auto
git config --global color.diff auto
git config --global alias.adog "log --all --decorate --oneline --graph"
git config --list
```

## Working with your first repo
```
mkdir sample-repo
cd sample-repo
ls -la 
git init 
ls -la 
ls -la .git
git status
touch example.txt && echo 'Hello World' > example.txt
git status
git add example.txt
git status
git commit -m "my first commit"
mkdir firstDir secondDir
touch firstDir/firstfile.txt
git status
git add .
git commit -m 'my second commit'
```

## Removing files from stage, commit, revert to specific commit
```
mkdir test-repo
cd test-repo
git init 
touch testfile-1 testfile-2 testfile-3 testfile-4
git status
git add . 
git status

git rm --cached testfile-1
git status
git rm --cached -r .
git status

echo 'first commit' > testfile-1
echo 'first commit' > testfile-2
echo 'first commit' > testfile-3
git add . 
git commit -m 'first commit'
echo 'changes made after commit' >> testfile-1
echo 'changes made after commit' >> testfile-2
echo 'changes made after commit' >> testfile-3

git status
cat testfile-1
git checkout testfile-1
cat testfile-1
git status 
git checkout . 
git status

echo 'second commit' >> testfile-1
git status
git add .
git commit -m 'second commit'
echo  'third commit' >> testfile-2
git status
git add .
git commit -m 'third commit'

git reset --soft HEAD~1
git status
git log
git reset --hard HEAD~1
git status
git log

```
