# Merge and Rebase
Is when I want merge 2 branch.

## Git ReReRe Reuse Record Resolution
Git will save how I resolve conflict
At next conflict, git will do the same
-> use in : rebasing and refactor

## config
* in the project : `git config rerere.enable true`
* use `--global` to enable in all project


## History and diff

### Useful commit message

1. Good commit message:
    * Commit message in future tense. fixed => fix.
    * Short subject, followed by a blank line.
    * A description of the current behavior, a short summary of __why__
      the fix is needed. Mention side effect. I explain the why, not the what.
    * limit description to 72 chars.
2. Encapsulate one logical idea.
3. Doesn't introduce breaking changes.

### Git log
Vanilla log is not very helpful

* Git log --since
  - `git log --since="yesterday"`
  - `git log --since="2 weeks ago"`

* Git log --follow
  keep track of the file event after a renaming
  `git log --name-status --follow -- <file>

* Git log -grep <regex>
  `git log --grep=mail --author=nina --since=2.weeks`

* Git log diff -filter
  exclude some file that have been (A)dded, (D)eleted, (M)odified & more...
  `git log --diff-filter=R --stat`

#### Git Log: referencing commits
git at each merge, keeps track of witch parent is first.
* ^
  - no args == ^1, the first __parent__ commit
  - n the n th parent commit
* ~
  - the first commit back, on the first parent
  - ~ ~ : 2 commit back on the first parent

#### Git diff
`git diff A..B` will show the diff on B that not on A

#### Diff branch
`git branch --merged master` show the branch that are already merged on master
`git branch --no-merged master` show the branch that are not on master

## Fixing Mistakes

### Git Checkout
Restore working tree files or switch branches.

#### What happens when you git checkout a branch?
1. Change the HEAD to point to the new branch.
2. Copy the commit snapshot to the staging area ( or index ).
3. Update the working area with the branch contents.
That's a pretty no dangerous operation.

#### When I do git checkout --file
I will overwrite my file without any __warning__.
It only interact with the file.

#### Clean the working area
I can delete all the file that are not track, by deleting them,
`git clean`
`git clean --dry-run` will show what will be deleted, -d for dir, -f file.

#### Git reset
* Reset modify the HEAD ptr.
* if I give path, I not move the HEAD ptr, but __only__ modify files

1. Move HEAD and current branch
2. Reset the staging area
3. Reset the working area

--soft = (1)
--mixed = (1) & (2)
--hard = (1) & (2) & (3)


__undo a git reset__
git keep the previous value of HEAD in a ORIG-HEAD
`git reset ORIG_HEAD`


### git Revert, the safe reset
* git create a new commit at the same place that revert the specified
  commit.
* the original commit stays in the repository

* use revert if the commit is push, __it does not change history__

## Rebase, Amend

### Amend
Amend is a quick way that lets make changes to the previous commit.
Amend create a new commit, and put Head on it, so the previous one
will be garbage collected.

### Rebase
Rebase = give a commit a new parent ( new base commit ).
Rebase like a fast forward

#### Interactive Rebase ( Rebase -i)
* will open an editor with a list of "todos"
* git will pick the commits in the specified order, or stop to take
  an action.
* 




# End
Best practice:
    commit ofter, perfect later, publish once.
Commit all the change
Always rebase before push

if I really mess up, look at reflog command





