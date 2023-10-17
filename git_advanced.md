## Understanding Git
v0.1.1-alpha
v1.0.0
Note: checking out 'v1.0.0'.

You are in 'detached HEAD' state. You can look around, make experimental changes and commit them, and you can discard any commits you make in this state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 0c0e5ff... Adding a title
 ...
$ git merge development
[Merge made by the 'recursive' strategy.
 ...
 1 file changed, 0 insertions(+), 0 deletions(-)
 ...]
$ echo "I'm in future-1" > conflicting.txt
$ git add conflicting.txt
$ git commit -m "Maybe will cause a conflict"

# Let's go back to master and redo the same in another branch
$ git checkout master

$ git checkout -b future-2
$ echo "I'm in future-2" > conflicting.txt
$ git add conflicting.txt
$ git commit -m "I'm sure it will cause a conflict!"
$ git merge future-1
Auto-merging conflicting.txt
CONFLICT (add/add): Merge conflict in conflicting.txt
Automatic merge failed; fix conflicts and then commit the result.
On branch future-2
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

	both added:      conflicting.txt

no changes added to commit (use "git add" and/or "git commit -a")
I'm in future-2
=======
I'm in future-1
>>>>>>> future-1
$ git commit -m "Resolve conflict"
$ git commit -m "Adding a title"
[master 0c0e5ff] Adding a title
 1 file changed, 1 insertion(+)
* master  0c0e5ff Adding a title
* master      0c0e5ff Adding a title
  development 0c0e5ff Adding a title
Switched to branch 'development'
$ git checkout -b development
Switched to branch 'development'
$ git add somefile
$ git commit -m "added somefile"
[development b894b84] added somefile
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 somefile
$ git branch -v
   master      0c0e5ff Adding a title
 * development b894b84 added somefile
Switched to branch 'master'
$ touch someotherfile
$ git add someotherfile
$ git commit -m "added someotherfile"
[master dc4a3e7] added someotherfile
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 someotherfile
$ git branch -v
 * master      dc4a3e7 added someotherfile
   development b894b84 added somefile
origin	git@github.com:[your_username]/[your_repo_name].git (fetch)
origin	git@github.com:[your_username]/[your_repo_name].git (push)
$ git remote -v
origin	git@github.com:[your_username]/[your_repo_name].git (fetch)
origin	git@github.com:[your_username]/[your_repo_name].git (push)
someRemote [url] (fetch)
someRemote [url] (push)
$ git remote rename non_existent newname
fatal: No such remote: non_existent
$ git remote rename non_existent newname
fatal: No such remote: non_existent
$ git remote remove non_existent
fatal: No such remote: non_existent
remote: Counting objects: 79, done.
remote: Compressing objects: 100% (23/23), done.
remote: Total 79 (delta 52), reused 74 (delta 52), pack-reused 4
Unpacking objects: 100% (79/79), done.
From git://github.com/[project_owner]/[your_repo_name]
   6b52ae6..5c53245  development -> [remote_name]/development
 * [new branch]      issue/876 -> [remote_name]/issue/876
 * [new tag]         v1.0     -> v1.0
[Merge made by the 'recursive' strategy.
 ...
 1 file changed, 10 insertions(+), 1 deletions(-)
 ...]
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

    git push --set-upstream origin test

$ git push --set-upstream origin test
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