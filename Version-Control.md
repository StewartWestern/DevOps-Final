# Version Control
### 1. Initializing a Repository


Below are basic commands for creating a folder entering into the folder, and initializing the project.
```bash
mkdir foldername
cd foldername
git init
touch README.md 
git add .
git commit -m "first commit"
```
You can create a branch of the current project with the below commands
```bash
git branch branch-name-here
```
The branch can be entered with ```git checkout "branch-name"```

These commands will push changes to github, keep in mind to specify if you are pushing the main or branch.
```bash
git push origin master/main
git push origin the-branch-you-named
```
If there is no connection you can connect a folder to a repository on github with 
```
git remote add origin https://github.com/username/example-link
```

Changes can be pulled from github with 
```bash
git pull origin main/master
```

The merge command can be use to resolve conflicts between file versions
```
git merge branch-you-named
```