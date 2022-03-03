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
