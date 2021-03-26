## Useful git commnands ##
See https://github.com/github/training-kit/blob/master/downloads/github-git-cheat-sheet.pdf for cheat sheet.

1. `git diff [commit ID 1] [commit ID 2]` - comparing different versions of commits across file(s)

1. `git diff` with no commit IDs will compare files between "Working Directory" and "Staging Area" (see point below on these 2 notions)

1. `git diff --staged` will compare files in "Staging Area" and the "git repo". This is useful for checking changes before you commit to the repo.

1. `git log --stat` - gives an overview and stats incuded on which files are changed in each commit in a repo and the ID of commit hash for specific changes

1. `git config -global color.ui auto` - turns on the color scheme so that git diff gives you the colored differences

1. `git checkout [commit ID to revert to]` - not the same as "checkout of code" in the SVN sense. Instead this means resetting the changes to a previous commit, possibly for example to debug a previous commit / version.

1. Git doesn't allow you to save a new commit if no files have been updated.

1. Use `git init` to initialize a new git repo from a local directory, which creates the hidden meta folder ".git". No commit will done when you 1st init a new git repo.

1. Use `git status` to find out about the most current commits of a repo etc.

1. Note the mental model for assets to version control: "Working Directory" --> "Staging Area" (git managed) --> "git repo" (git managed; the one u get when u run git init on your working directory)

1. Use `git add [filename]` to add files to the "Staging Area". You can then commit the added file(s) in a logical unit later on to the local git repo.  
**Note 1:** At this stage, because the changes are not yet committed, there are no commit IDs  
**Note 2:** If you do a `git diff` (i.e. with no commit IDs), this will compare files across "Working Directory" & "Staging Area" for files NOT YET added to the "Staging Area"

1. `git commit` will batch all the files added to staging in one single commit.

1. Use `git reset [filename]` to remove files from the "Staging Area".

1. Use `git reset --hard` to discard ALL CHANGES in "Working Directory" and "Staging Area"; use this carefully!!!

1. Git uses labels to tag your commits. These labels are known as *branches*. `master` is a branch which Git creates for you when u create a new repo.

1. Use `git branch` to query all your current branches. If you have no branches created, you will only see *master* being listed. This command can also tell you which branch is the one currently checked out (seeing the * beside it).

1. Use `git branch [new branch or label name]` to create a new branch. But this will not automatically checkout the new branch; use `git checkout [new branch name]` to switch to the new branch before doing your changes. Then use `git log` to visualise all the commits for that branch.

1. Or use `git checkout -b [new branch name]` to create a new  branch and running a checkout on that branch as a 2-in-1 step.

1. Use `git log --graph --oneline [branch name 1] [branch name 2]` to visualise the commit history and compare changes between branches.

1. If a branch is deleted and leaves some commits unreachable from existing branches, those commits will continue to be accessible by commit id, until Git’s garbage collection runs. This will happen automatically from time to time, unless you actively turn it off. You can also run this process manually with `git gc`.

1. Deleting a branch is simply deleting the label for that branch.

1. Use `git merge [branch 2] [branch 3]` to merge branches into your currently checked out branch (in this case branch 1) and creating a new commit for branch 1; `git merge` will include the currently checked-out branch in the merged version.
`git merge` provides a default commit message and using it as it is recommended.

1. Restore your files to their state before you started the merge by running `git merge --abort`.

1. Comparing a commit to its parent, without knowing its parent commit id, use `git show [commit ID]`.

1. When there is a merge conflict on any of the files, inspect the fie contents and look for line(s) labelled `|||||| merged common ancestors`. Line(s) labelled `<<<<<< HEAD` are those changes made in current checked out branch; while line(s) labelled `>>>>>> master` are those changes made in master branch.

1. Remote repo (e.g. in Github) are called **remotes**. Sync (via `git push`) between local repo and remote happens at the commit IDs (history) level and that's how we will reason about changes in our code changes. Those commits which are already on remote will not be synced.

1.  


