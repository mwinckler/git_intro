<!SLIDE subsection>

# Advanced Workflow


<!SLIDE smbullets incremental left>

# Git Advanced Workflow

* `git branch` to work on stuff in isolation
* `git merge` to get outside changes into your copy
* `git stash` to tuck changes away temporarily
* `git tag` to put a label on a version for easy lookup later
* `git rebase` to destroy your sanity*
* <br /><br /><small>* results may vary</small>

<!SLIDE >

# Branches

(image of branching goes here)

A branch is a copy of the code you can work on while leaving other branches untouched.

<!SLIDE >

# Branches

Each branch keeps track of the changes that have been made in it so that it can be `merge`d back into the branch it came from, or vice versa.

<!SLIDE >

# Branches

Branches are cheap - Git only stores "deltas", not full copies. Make branches!


<!SLIDE >

# Creating a Branch

	git checkout -b <branch-name>

<!SLIDE >

# Switching between branches

	git checkout <branch-name>

**Note:** Your working directory need not be clean. This may or may not be desirable.

.notes Switch to terminal for demo.

<!SLIDE >

# Merging

A merge grabs changes from a **different** branch and merges them into the **current** branch.


<!SLIDE bullets incremental>

# Merging

* If the relevant files only changed on the branch being merged, it's a *fast-foward* merge.

* If both files changed, it's a *non-fast-forward* merge, but Git might still do it without user interaction.

* If both files changed the same lines, it's a *conflict* and requires user intervention.

<!SLIDE >

# Merging

First checkout the branch you want to merge **onto**, then:

	git merge <branch-name>

<!SLIDE >

# Stashing

Forget about the changes in your working directory...temporarily.

<!SLIDE >

# Stashing

With *unstaged* changes in your working directory:

	git stash

Warning: `stash` only stashes changes to files that Git already cares about.

<!SLIDE >

# Get the stash back

	git stash pop

Note: This pops onto whatever your working directory currently is...even if it&rsquo;s not the one you stashed from.

<!SLIDE >

# Branch from the stash

	git stash branch <branch-name>


<!SLIDE >

# Tagging

A tag is a convenient way to label a commit.

You don't *need* a tag to retrieve old versions - but they can be handy if you know you'll need to reference a commit later.
