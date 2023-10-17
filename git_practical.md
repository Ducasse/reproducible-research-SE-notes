## Practical Git Scenarios 
# Or everything
$ git reset HEAD .
commit 0c0e5ff55b56fe8eabc1661a1da64b41f9d74472
Author: Guille Polito <guillermopolito@gmail.com>
Date:   Wed Mar 21 15:37:32 2018 +0100

    Adding a title

commit 37adf4eaa945cbd7460991f88bff5aa902db06ce
Author: Guille Polito <guillermopolito@gmail.com>
Date:   Wed Mar 21 14:02:43 2018 +0100

    first version
commit 0c0e5ff55b56fe8eabc1661a1da64b41f9d74472
Author: Guille Polito <guillermopolito@gmail.com>
Date:   Wed Mar 21 15:37:32 2018 +0100

    Adding a title

diff --==git== a/README.md b/README.md
index e69de29..cad05f1 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1 @@
+! a title
\ No newline at end of file
* 4eb8446 Documenting
* e5a3e2e Add tests
* 680a79a Some other
| *   ed4854f Merge pull request #1137
| |\
| | * 9e30e37 Some feature
| * |   ba7f65c Merge pull request #1138
| |\ \
| | * | 31a40c4 Some Enhancement
| | |/
| * |   2d4698d Merge pull request #1139
| |\ \
| | * | 20c0ff4 Some fix
| | |/
| * |   ae3ec45 Merge pull request #1136
$ git clean -df

# Lines starting with hashtags are comments

# A file name will ignore that file
someignoredfile.txt

# A file name will ignore that file
someignoredfile.txt

# A file pattern will ignore all pdf files
*.pdf
$ git commit -m "Added gitignore"
$ git commit -m "that file is still important"
$ git  commit --amend -m "Updated commit message"
$ git  log --oneline

eae7846 New
71c0c64 Intermediate
f039832 Old
cca92f1 Even older

pick f039832 Old
pick 71c0c64 Intermidiate
pick eae7846 New
squash 71c0c64 Intermidiate
pick eae7846 New
# This is the 1st commit message:

Old

# This is the commit message #2:

Intermediate

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.

eae7846 New
651375a Merge intermediate + old
cca92f1 Even older
To git@github.com:REPOSITORY_OWNER/YOUR_REPOSITORY.git
 ! [rejected]        YOUR_BRANCH -> YOUR_BRANCH (non-fast-forward)
error: failed to push some refs to 'git@github.com:REPOSITORY_OWNER/YOUR_REPOSITORY.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: '==git== pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in '==git== push --help' for details.
Total 0 (delta 0), reused 0 (delta 0)
To git@github.com:REPOSITORY_OWNER/YOUR_REPOSITORY.git
+ a1713f3...6e0c7bf YOUR_BRANCH -> YOUR_BRANCH (forced update)