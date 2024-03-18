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
