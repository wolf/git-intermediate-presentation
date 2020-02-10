# Outline for the intermediate Git presentation

## Branches

* On our wiki: <http://wiki.learninga-z.com/index.php/Git_Branching_at_LAZ>
* Why make a branch in the first place?
* Kinds of branches
  * Private, (local-only) branches
    * Private, but you pushed it anyway
  * Code-review branches
  * Shared branches
  * Release branches

* How to work on a branch
  * How to merge your branch back into master
* <https://learngitbranching.js.org/> -- thanks to several people for pointing out this resource

## Commits

* Commit messages
  * new format for bug numbers?
  * show examples where space is constrained -- making 50 char limit sensible
  * On our wiki: <http://wiki.learninga-z.com/index.php/Git_Commits_at_LAZ>
  * <https://chris.beams.io/posts/git-commit/>
  * <https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>
* Squashing commits
  * how to know when you should have had one commit instead of N
    * probably...
      * when they all have the same commit message
      * when they're all commits for the same bug
    * definitely...
      * when two commits depend on each other
      * when, if you were going to back out a change, you'd have to revert **all** of them
      * when checking out a particular commit wouldn't produce a working site
      * when a commit just fixes a typo or missing file in the previous commit
  * how to squash the commits
* Committing to save your work, then "uncommitting", leaving the changes from that commit in the tree

## How to undo mistakes

* Everything is fixable as long as you committed
* The worst case: uncommitted changes that you lost cannot be retrieved by Git
  * ...but maybe can be retrieved through local history in IntelliJ
* <https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/>
* Kinds of mistakes
  * un-pushed problem with tip commit
    * entirely bad commit -- answer: reset
      * note that "Reset Current Branch to Here..." is --hard whereas
        VCS -> Git -> "Reset HEAD..." lets you choose
    * bad commit message -- answer: edit commit message
    * missing a file or change to an included file -- answer: commit --amend
    * you've made commits on master that now you've decided should be on a branch instead -- answer: create
    a branch + reset HEAD of master
  * un-pushed problem with non-tip commit
    * entirely bad commit -- answer: rebase -i
    * bad commit message -- answer: rebase -i
    * missing a file or change to an included file -- answer: rebase -i
    * you've made commits on master that now you've decided should be on a branch instead -- answer: rebase
  * pushed problem
    * entirely bad commit -- answer: revert

* The reflog
  * the reflog for a given branch
  * the reflog for HEAD

* Using changelists
  * controlling what goes in your next commit
* things you can do in IntelliJ with the log pane
* the power of git log on the command line (things you _can't_ do in IntelliJ)
  * -S (pick-axe)
  * -L
