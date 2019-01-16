# GIT BASICS CHEAT SHEET
## HOW TO START
```
git init test-repo
cd test-repo
```
## GIT STATES AND SECTIONS
```
cd .git
ls -al
cd ..
echo "Hello World" > README.md
git status
git add README.md
git commit --help 
git commit -m "Initial commit"
```
## GIT PULL AND GIT PUSH

After creating a new repository on GitHub called test-repo

```
git remote
git remote add origin https://github.com/andresrrey/test-repo.git
git remote
git remote -v
git push -u origin master
```
After doing another change using GitHub interface

```
git pull origin master
git log -p
```

## GIT BRANCHES

```
git branch
git branch -r
git branch -a
git branch featurea
git checkout featurea
echo "Hello from User 1" > featurea.txt
git add *
git commit -m "Adding feature A"
git push origin featurea
ls -al
git checkout master
ls -al
git merge --ff-only featurea
```

## MERGE V.S. REBASE

### MERGE

```
git branch featureb
echo "Hello from master branch" >> README.md
git add *
git commit -m "Editing README.md"
git push origin master
git checkout featureb
echo "Hello from featureb" >> README.md
git add *
git commit -m "Adding feature B"
git checkout master
git merge featureb
git status
```

### REBASE

```
git merge --abort
git checkout featureb
echo "Hello from featureb" >> featureb1.txt
git add *
git commit -m "Adding feature B1"
echo "Hello from featureb" >> featureb2.txt
git add *
git commit -m "Adding feature B2"
git checkout master
```

## PULL REQUEST

After doing a fork of your partner's repo
```
git clone https://github.com/andresrrey/test-repo-1.git
cd test-repo-1
echo "Hello from andresrrey" >> README.md
git add *
git commit -m "Adding comment from andresrrey to README.md"
git push origin master
```
Then you should do a pull request on GitHub

After approving your partner pull request to your own repo on GitHub
```
cd ../test-repo
git pull
git log -p
```
