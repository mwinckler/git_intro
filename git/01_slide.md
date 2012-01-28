<!SLIDE >

# Introducing Git ([git-scm.com](http://git-scm.com/))

* Installation
* Basic Workflow Commands
* Informational Commands
* Advanced Workflow Commands

<!SLIDE >

# Installation

* Ubuntu: `apt-get install git-core`
* OSX: [git-osx-installer](http://code.google.com/p/git-osx-installer/downloads/list?can=3)
* Windows: [msysgit](http://code.google.com/p/msysgit/downloads/list)

<!SLIDE >

# Basic Workflow Commands

1. Open a command prompt

<!SLIDE >

# Wait a minute, this is 2012. _Command prompt?!_

* Learn it the hard way first
* After mastery, you can go find a GUI

If you start with a GUI but don't have a clue about the basics of the underlying system, you're asking for trouble.


<!SLIDE >

# Basic Workflow Commands

* `init` or `clone` (one time only)
* `add` files to the repository
* `commit` changes
* `push` or `pull` to/from "remotes"

<!SLIDE >

# Informational Commands

* `show` a particular commit's details
* Display a `log` of past commits
* Get the `status` of your working copy

<!SLIDE >

# Git Advanced Workflow

* `branch` to work on stuff in isolation
* `merge` to bring outside changes into your working copy
* `stash` to tuck changes away temporarily
* `tag` to put a label on a version for easy lookup later
* `rebase` to clean up your revision history


<!SLIDE >

# Creating a Repository

	cd [project folder]
	git init
	git add .
	git commit -am "Initial commit"


<!SLIDE >

# Clone an Existing Repository

	git clone [remote location]

Example:

	git clone git@github.com:mwinckler/libMatt.git


<!SLIDE >

# Do Some Work

1. Change some files
2. Add a new file
3. What does Git think about that?
	* `git status`


<!SLIDE >

# Commit those changes!

	git add .
	git commit

<!SLIDE >

# git add? I thought we added these already!

## And now, a brief digression into the subject of What Git Cares About. 

(Hint: only what you've told it to)

<!SLIDE >

# The Various And Divers States Of A File

## A file with changes falls into one of four categories:

* Untracked
* Changed but _unstaged_ for commit
* Changed and _staged_ for commit
* Ignored


<!SLIDE >

# Untracked files

## These are files that are present in your repository directory but that you have not told Git to keep track of (via `git add`).

<!SLIDE >

# Changed but unstaged

`git status` shows these as "Changes not staged for commit"

## These are files that:

* have been added to the repository,
* have changed since the last commit, and
* you have _not_ yet told Git to include them (via `git add`) next time you run `git commit`

<!SLIDE >

# Changed and staged

`git status` shows these as "Changes to be committed"

## These are files that:

* have been added to the repository,
* have changed since the last commit, and
* you have told Git (via `git add`) to include next time you `git commit`

<!SLIDE >

# Ignored

`git status` will never show these.

* These are files you've told Git to ignore via `.gitignore`.
* Git will never ignore files that have been added to the repository, even if they match a `.gitignore` entry.


<!SLIDE >

# Back on topic: committing

	git add .
	git commit

A shortcut:

	git commit -a

<!SLIDE >

# An even shorter cut:

	git commit -am "your message"

<!SLIDE >

# What's our status now?

	git status

# What's our history?

	git log

<!SLIDE >

# Wait, I didn't mean to do that!

## Need to fix the most recent commit?

	[make the changes]
	git commit --amend

**DO NOT** use `--amend` if you have already pushed to a remote repository! Your collaborators will curse your name!

<!SLIDE >

# Wait, I didn't mean to do that! (pt. 2)

## Want to revert to a specific version of a file?

	git checkout HEAD^4 -- filename

retrieves `filename` from 4 versions ago

	git checkout [commit-hash] -- filename

retrieves `filename` as it existed in the commit identified by `commit-hash`

<!SLIDE >



<!SLIDE >

# Version Control Philosophy

## What goes in the repository?

* **_Everything_ that doesn't get created as part of your build process**
* **...and _nothing_ that does**


<!SLIDE >

# How do we keep stuff out?

[`.gitignore`](http://help.github.com/ignore-files/): A special file telling Git what to ignore.

Note that `.gitignore` will not ignore files that you've already told Git to care about.


<!SLIDE >

# A Warning

## **Git is safe, but you are not. And Git does what you tell it to.**

* Don't fool around with `rebase` until you understand what it's doing.
* Be wary of `git reset --hard`.
* When in doubt, back up: just copy your project folder!
