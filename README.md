# GIT
Git is VCS, and it stores files as continous snapshots.
There are three main states of your files in **Git**
1. modified
2. stages
3. commited

# GIT BASICS
1. you can initialize repository by cloning or **git init** command.
## Initializing git repository
# Git commands
1. git init
2. git clone <`url`>
3. git add <`filename`>
4. git status 
5. git status -s 
6. git status --short --> for short status 
7. .gitignore [git ignore templates](https://github.com/github/gitignore)
8. git status shows what files changed
9. **git diff** shows what lines you have exactly changed.
10. **git** diff --staged (to see what will go into your next commit)
11.  **git diff** shows changes you have not staged if you staged then this will show no output.
12.  __git diff --cached__ and __git diff --staged__ are the synonyms.
13.  __git commit -m "message of commit"__
14.  __git commit__ this will open your default editor and if you write __git commit -v__ then this will the changes you have made also.
15.  If you wan to skip staging area then you can pass flag with __git commit__ command  __-a__
16.  If you want to remove a file, that git no longer track that file then __git rm fileName__ and if you have made chagnes to your file then git will not allow you, but you can pass -f flag i.e __git rm fileName -f__
17. If you want to keep the file in your working directory and want to no tracked by git then pass __--cached__ flag i.e __git rm --cached fileName__
18.  __git log__ to see the all commit history of project
19.  __git log -p__ which shows the difference introduced in each commit.
20. __git log -p -2__ which shows the last 2 commits
21.  If you want to see the abbreviated stats you can use __git log --stat__
22.  __git log --pretty=oneline__ shows each commit in one line with hash value and message. more available options are __short, full, fuller__
23.  __git log --pretty=format:"%h - %an, %ar : %s"__ to format as you desires.
24.  Table specifiers [Pretty output specifiers image](https://i.ibb.co/6rfVR4p/git.png)
25.  __git log --pretty=format:"%h %s" --graph__
26.  __since and --untill__ are very useful.
27. __git log --since=2.weeks__
28.  ### Undoing Things
29.  
30.  Undo all changes made to the file and revert back to previous commit version.
~~~
git checkout - - <file_name>
~~~
31.  Unstaging a staged file with Git restore command
~~~
git restore --staged fileName
~~~
32. Undo or discard changes using checkout command
~~~
git checkout <fileName>
~~~
33. Unmodifying a Modified File with git restore
~~~
git restore fileName
~~~
34. __Origin__ is the default name given by git to the repository you have cloned from. To show all remotes use:
~~~ 
git remote -v 
~~~
35. Adding Remote Git Repositories
~~~
git remote add name http://github.com/etc
~~~
36.  Git fetch origin branch ( fetch the changes then we merge the branch) git pull fetch and merge both. 
37.  git push origin master
38.  show origin => git remote show origin
39. __renaming and removing remotes__
~~~
git remote rename oldName newName
git remote remove remoteBranchName
~~~
### Git Aliases
Make your own aliases and use them instead of writing long commands each time.
~~~
git config --global.co checkout
git config --global.ci commit
git config --global.br branch
~~~
# Branching
## create New Branch
1. Creating new branch mean create new pointer on the same commit you'r on.
~~~
git branch branchName
~~~
[branching Image](https://i.ibb.co/QpHsPWB/2022-03-07-17-02.png)
2. **HEAD** is the pointer which shows current branch.
## Switching Branches
~~~
 git checkout branchName
~~~
1. If you want to commit all changes then run - this will add and commit files (not recommended)
~~~
git commit -a -m "made a change"
~~~
2. You can create and checkout branch at the same time by using following command:
~~~
git checkout -b <branchName>
~~~
3. switch can be used to switch branch
~~~
git switch branchName
git switch -c branchName
~~~
__Origin : the default name Git gives to the server you cloned from__
**Merging**
~~~
git checkout targetBranch
git merge sourceBranch
~~~
**Delete the branch**
~~~
git branch -d branchName
~~~
**branch details**
~~~
git branch 
git branch (--merged || --no-merged)
~~~
**Change Branch Name**
~~~
git branch --move bad-branch-name correct-branch-name
~~~
to Push branch corrected branch name push it. 
~~~
git push --set-upstream origin corrected-branch-name
~~~
**Pushing**
when you want to know the branch to the world, you need to push the branch to the repository where you have write access.
~~~
git push <remote> <branch>
~~~
This mean take my local branch to the server and make it remote branch.
**tracking branches**
**Setup Local Branch to Remote**
~~~
git branch -u origin/serverfix
~~~
**to check which tacking branches you setup**
~~~
git branch -vv
~~~
### Pulling 
~~~
git pull
~~~
1. it fetches from remote server and merge it.

```
While the git fetch command will fetch all the changes on the server that you don???t have yet, it will not modify your working directory at all. It will simply get the data for you and let you merge it yourself. However, there is a command called git pull which is essentially a git fetch immediately followed by a git merge in most cases. If you have a tracking branch set up as demonstrated in the last section, either by explicitly setting it or by having it created for you by the clone or checkout commands, git pull will look up what server and branch your current branch is tracking, fetch
from that server and then try to merge in that remote branch.
Generally it???s better to simply use the fetch and merge commands explicitly as the magic of git pull can often be confusing.
```
