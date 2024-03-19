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
git config --global core.editor vi
git config --global alias.adog "log --all --decorate --oneline --graph"
git config --global alias.lg 'log --color --graph --pretty="%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" --abbrev-commit'
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

## Removing files from stage, commit, reset to specific commit
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

## Revert changes
```
mkdir revert-repo
cd revert-repo
git init
touch filename-1
echo 'first-commit' > filename-1
git add filename-1
git commit -m 'first commit'
touch filename-2
echo 'second-commit' > filename-2
git add filename-2
git commit -m 'second commit'
touch filename-3
echo 'third-commit' > filename-3
git add filename-3
git commit -m 'third commit'
git log
ls -l
git revert --no-edit HEAD
git log
ls -l
git revert --no-edit HEAD
git log
ls -l
git revert --no-edit HEAD~3
git log
ls -l
```

## Git Diff examples
```
mkdir diff-repo
cd diff-repo
git init
touch filename-1
echo 'first-commit' > filename-1
git add filename-1
git commit -m 'first commit'
touch filename-2
echo 'second-commit' > filename-2
git add filename-2
git commit -m 'second commit'
git diff
git diff HEAD~1
touch filename-3
echo 'third-commit' > filename-3
git add filename-3
git diff --staged
```

## Git Tag examples
```
mkdir tag-repo
cd tag-repo
git init
touch filename-1
echo 'first-commit' > filename-1
git add filename-1
git commit -m 'first commit'
touch filename-2
echo 'second-commit' > filename-2
git add filename-2
git commit -m 'second commit'
touch filename-3
echo 'third-commit' > filename-3
git add filename-3
touch filename-4
echo 'fourth-commit' > filename-4
git add filename-4
git commit -m 'fourth commit'
touch filename-5
echo 'fifth-commit' > filename-5
git add filename-5
git commit -m 'fifth commit'

git tag
git tag -a v1.0 -m "version 1.0. initial state"
git tag
echo 'sixth-commit' > filename-6
git add filename-6
git commit -m 'sixth commit'
git tag -a v2.0 -m "version 2.0. new feature"
git tag

git tag -d v1.0
git tag
git tag -a v1.5 -m 'version 1.5 tag' <commitID>
git tag
```

## Merge Example
```
git config --global alias.adog "log --all --decorate --oneline --graph"
mkdir merge-repo
cd merge-repo
git init
git branch
touch filename-1
echo 'first-master-commit' > filename-1
git add filename-1
git commit -m 'first master commit'
touch filename-2
echo 'second-master-commit' > filename-2
git add filename-2
git commit -m 'second master commit'
git adog

git checkout -b newbranch
git branch

touch filename-3
echo 'first-branch-commit' > filename-3
git add filename-3
git commit -m 'first branch commit'

echo 'second-branch-commit' >> filename-2
git add filename-2
git commit -m 'second branch commit'
git adog

git checkout master
git merge newbranch --no-edit
git branch -d newbranch

git adog
git checkout -b anotherbranch
git branch
touch filename-4
echo 'first-branch-commit' > filename-4
git add filename-4
git commit -m 'first another branch commit'
echo 'second-branch-commit' >> filename-2
git add filename-2
git commit -m 'second another branch commit'
git merge master --no-edit
git checkout master
git merge anotherbranch --no-edit
git branch -d anotherbranch
git branch

git adog

```
