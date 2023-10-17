## Getting Started with Git
Cloning into '[your_project_name]'...
remote: Counting objects: 11082, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 11082 (delta 2), reused 6 (delta 2), pack-reused 11076
Receiving objects: 100% (11082/11082), 4.35 MiB | 1.22 MiB/s, done.
Resolving deltas: 100% (4063/4063), done.
Checking connectivity... done.
$ touch project.txt
...
project.txt README.md
# Done
 - created the repository
 - ==git== clone
 - created this file
 
# To do
 - commit this file
 - push it to my remote repository
#My Project

This project is an example ==git== repository used to learn ==git==.
Check the project.txt file for information about pending tasks.
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	project.txt

no changes added to commit (use "git add" and/or "git commit -a")
$ git status
On branch master
nothing to commit, working tree clean
On branch master

Initial commit

Untracked files:
	README.md
	project.txt

nothing added to commit but untracked files present
$ git  add project.txt
$ git  status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
	new file:   project.txt
[master a93c016] first version
 2 files changed, 12 insertions(+), 1 deletion(-)
 create mode 100644 project.txt
On branch master
nothing to commit, working directory clean
# Done
 - created the repository
 - ==git== clone
 - created this file
 - commit this file
 
# To do
 - push it to my remote repository
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   project.txt

no changes added to commit (use "git add" and/or "git commit -a")
$ git  commit -m "Commit is not in ToDo anymore"
[master e14a09f] Commit is not in ToDo anymore
 1 file changed, 1 insertion(+), 1 deletion(-)
remote: Counting objects: 2, done.
remote: Compressing objects: 100% (1/1), done.
remote: Total 2 (delta 1), reused 2 (delta 1), pack-reused 0
Unpacking objects: 100% (2/2), done.
From https://github.com/guillep/test
   1656797..a2dbd8b  master     -> origin/master
Updating 1656797..a2dbd8b
Fast-forward
 newfile | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newfile
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 271 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:[your_username]/[your_repo_name].git
   b6dcc3f..f269295  master -> temp
  development   1656797 This commit adds a new feature
  master        f269295 [origin/master] First commit
fatal: The current branch test has no upstream branch.
To push the current branch and set the remote as upstream, use

    ==git== push --set-upstream origin test

$ git  push --set-upstream origin test
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 271 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:[your_username]/[your_repo_name].git
   b6dcc3f..f269295  master -> test
To git@github.com:guillep/test.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:[your_username]/[your_repo_name].git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.