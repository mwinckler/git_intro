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
* After mastery, you can go search for a GUI


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

# Version Control Philosophy

## What goes in the repository?

* **_Everything_ that doesn't get created as part of your build process**
* **...and _nothing_ that does**


<!SLIDE >

# How do we keep stuff out?

[`.gitignore`](http://help.github.com/ignore-files/): A special file telling Git what to ignore.

Note that `.gitignore` will not ignore files that you've already told Git to care about.


<!SLIDE >

# Does Git Care About [filename]?

Git only keeps track of files it knows and cares about. 



<!SLIDE >

# A Warning

## **Git is safe, but you are not. And Git does what you tell it to.**

* Don't fool around with `rebase` until you understand what it's doing.
* Be wary of `git reset --hard`.
* When in doubt, back up: just copy your project folder!
