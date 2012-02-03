<!SLIDE subsection>

# Introducing Git
[git-scm.com](http://git-scm.com/)


<!SLIDE bullets incremental>

# What is it?

* Git is **distributed version control system** software written by our favorite penguin-loving Finn, Linus Torvalds. 

* Think of it as Subversion without the server. And with better branching. And merging that won't make you old. And faster. And without `.svn` folders littered about the place. 

* But other than that, it's just like Subversion.

<!SLIDE >

# What's it good at?

Managing large numbers of text files...for instance, source code. (It was written for the Linux kernel.)

<!SLIDE >

# What's it bad at?

Handling enormously large files.

Possible remedy: [git annex](http://git-annex.branchable.com/). Disclaimer: I don't know anything about the git annex project.

<!SLIDE >

# Installation

* Ubuntu: `apt-get install git-core`
* OSX: [git-osx-installer](http://code.google.com/p/git-osx-installer/downloads/list?can=3)
* Windows: [msysgit](http://code.google.com/p/msysgit/downloads/list)

.notes If you Google and install Git right now, by the end of this presentation you'll be able to use it to download...this presentation!

<!SLIDE >

# Basic Workflow Commands

1. Open a command prompt

<!SLIDE >

# Wait a minute, this is 2012. _Command prompt?!_

<!SLIDE bullets incremental>

# You're going to _use_ the command prompt, and _like_ it.

* Learn it the hard way first
* After mastery, you can go find a GUI
* ...but you may not want to.


<!SLIDE smbullets incremental left>

# Basic Commands

`git <command>`

* `git init` or `git clone` a new repository
* `git add` files to the repository
* `git commit` changes
* `git show` a particular commit's details
* `git log` to view past commits
* `git status` to show the status of your working copy


<!SLIDE >

# Create a new repository...

	cd <project-folder>
	git init
	git add .
	git commit -am "Initial commit"


<!SLIDE >

# ...or clone an existing repo

	git clone <remote-location>

Example:

<pre class='smaller'><code>git clone git@github.com:mwinckler/libMatt.git</code></pre>

<!SLIDE >

# Do Some Work

1. Change some files
2. Add a new file
3. What does Git think about that?
	* `git status`


<!SLIDE bullets incremental>

# Commit those changes!

## Wait. First, what's a commit?

* An atomic snapshot of files as they existed at the time of the commit.
* Identified by a SHA1 hash.
* Stores metadata (author, date, etc.).

<!SLIDE >

# Commit those changes!

	git add .
	git commit

<!SLIDE >

# `git add`? I thought we added these already!

<!SLIDE >

# Let us discuss the sensitive subject of What Git Cares About.

<!SLIDE subsection>

# Things Git Cares About

(you're not one of them)

<!SLIDE >

# Git cares about<br />the things you tell it to.

`git add`

<!SLIDE >

# `git status` gives us clues.

.notes Switch to terminal, git status.

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

.notes By default, before ever running "git add", this is all your files.

<!SLIDE bullets incremental left>

# Changed but unstaged

`git status` shows these as "Changes not staged for commit"

## These are files that:

* have been added to the repository,
* have changed since the last commit, and
* you have _not_ yet told Git to include them in the next `git commit`

<!SLIDE bullets incremental left>

# Changed and staged

`git status` shows these as "Changes to be committed"

## These are files that:

* have been added to the repository,
* have changed since the last commit, and
* you *have* told Git (via `git add`) to include next time you `git commit`

<!SLIDE bullets incremental left>

# Ignored

* `git status` will never show these.
* These are files you've told Git to ignore via `.gitignore` (repo-based or global).
* Git will never ignore files that have been added to the repository, even if they match a `.gitignore` entry.


<!SLIDE >

# Back on topic: committing

	git add .
	git commit

.notes Switch to terminal, demonstrate

<!SLIDE >

# A commit shortcut

	git commit -a

The `a` stands for "all" and will commit all changed files, staged or unstaged (but not _untracked_ ones).

<!SLIDE >

# An even shorter cut

	git commit -am "your message"

The `m` stands for "message" and lets you specify your commit message on the command line.


<!SLIDE >

# What's our status now?

	git status

# What's our history?

	git log

<!SLIDE smbullets incremental left>

# Rollbacks

What kind of rollback do you want?

* Change the most recent commit?<br />`git commit --amend`
* Revert an entire commit?<br />`git revert <commit-hash>`
* Check out a particular file?<br />`git checkout <commit-hash> -- <file>`
* Don't know for sure? Find differences:<br />`git diff <commit1>..<commit2>`

<!SLIDE >

# Amending the last commit

Go ahead and make the changes, then:

	git commit --amend

**DO NOT** use `--amend` if you have already pushed to a remote repository! Your collaborators will curse your name!

<!SLIDE >

# Check out a particular version

	git checkout <commit-hash> -- filename

retrieves `filename` as it existed in that commit

	git checkout HEAD^4 -- filename

retrieves `filename` from 4 versions ago

<!SLIDE >

# Revert an entire commit

(the "Matt must have been drinking during that commit" option)

	git revert <commit-hash>

<!SLIDE >

# Finding differences

	git diff <file>

shows uncommitted changes in your working copy.

	git diff <commit1>..<commit2> -- <file>

shows the differences in `<file>` between `commit1` and `commit2`.

<!SLIDE >

# Need your GUI?

_(diffs are hard; let's go shopping!)_

It's okay. I understand. Just replace `diff` with `difftool`.

First you may need to [configure a difftool](http://duckduckgo.com/?q=git+difftool), which is left as an exercise for the reader.


<!SLIDE subsection>

# A Brief Review

<!SLIDE bullets incremental>

# Basic commands

* Create a repository via `git init` or `git clone`
* Add stuff via `git add`
* Make changes, then `git commit` them

<!SLIDE bullets incremental>

# Were you paying attention earlier?

## What goes in the repository?

* Everything the build _doesn't_ create, and _nothing_ that it does

<!SLIDE >

# How do we ignore stuff like build results?

[`.gitignore`](http://help.github.com/ignore-files/): A special file telling Git what to ignore.