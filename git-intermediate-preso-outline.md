# Outline for the intermediate Git presentation

## Commits

* Commit messages
  * new format for bug numbers?
  * show examples where space is constrained -- making 50 char limit sensible
* Squashing commits
  * how to know when you should have had one commit instead of N
    * maybe...
      * when they all have the same commit message
      * when they're all commits for the same bug
    * definitely...
      * when two commits depend on each other
      * when, if you were going to back out a change, you'd have to revert all of them
      * when checking out a particular commit wouldn't produce a working app
      * when a commit just fixes a typo or missing file in the previous commit
* Committing to save your work, then "uncommitting", leaving the changes from that commit in the tree

## Branches

* Kinds of branches
  * Why make a branch in the first place?
  * Private, (local-only) branches
    * Private, but you pushed it anyway
  * Code-review branches
  * Shared branches
  * Release branches

  * How to work on a branch
    * How to merge your branch back into master
  * <https://learngitbranching.js.org/> -- thanks to several people for pointing out this resource

## How to undo mistakes

* <https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/>
* Kinds of mistakes
  * pushed problem
    * entirely bad commit -- answer: revert
  * un-pushed problem with tip commit
    * entirely bad commit -- answer: reset
    * bad commit message -- answer: edit commit message
    * missing a file or change to an included file -- answer: commit --amend
  * un-pushed problem with non-tip commit
    * entirely bad commit -- answer: rebase -i
    * bad commit message -- answer: rebase -i
    * missing a file or change to an included file -- answer: rebase -i
    * you made commits on master that now you've decided should be on a branch instead -- answer: rebase
  * do I want to talk about it this way?  or just cover rebase -i and mention the problems as we fix them
* Everything is fixable as long as you committed
* The worst case: uncommitted changes that you lost cannot be retrieved by Git

* The reflog
  * the reflog for a given branch
  * the reflog for HEAD

* Using changelists
  * controlling what goes in your next commit
  * using branches instead
* things you can do in IntelliJ with the log pane
* the power of git log on the command line (things you _can't_ do in IntelliJ)
  * -S (pick-axe)
  * -L
