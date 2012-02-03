<!SLIDE subsection>

# Collaboration Using Git


<!SLIDE bullets incremental left>

# Collaboration Commands

* `git remote` to view/change remotes
* `git push` changes to a remote
* `git pull` changes from a remote

<!SLIDE bullets>

# What is a remote?

A _remote_ is a repository located somewhere else that your Git client knows and cares about.

<!SLIDE >

# Creating Remotes

The easy way:

	git clone <remote-location>

`clone` does two things: copies the remote repository and sets up a remote named `origin` so that you can push/pull changes to/from it.

.notes Switch to terminal for demo.

<!SLIDE >

# Creating Remotes

The manual way:

	git remote add <remote-name> <remote-url>

Do this if you already have a copy of the repository locally and you want to tie it to a copy at a remote location (or push it to a remote server).

<!SLIDE >

# Viewing remotes

To see what remotes you have set up, run:

	git remote show

To get more details on a particular remote, use:

	git remote show <remote-name>

<!SLIDE >

# Push and Pull

* `git pull` retrieves changes from a remote and `merges` them into your working copy.
* `git push` sends your changes up to a remote.


<!SLIDE bullets>

# Push

Do this when you want to send your local changes up to a server for others to pull.

* **In order to `push`,**
	1. Your working copy must be clean (no uncommitted changes)
	2. Your working copy must be up-to-date with the remote you're pushing to (no changes you haven't yet `pull`ed)

.notes Switch to terminal for demo.

<!SLIDE bullets >

# Pull

Do this when you want to retrieve other people's changes.

* In order to `pull` your working copy must be clean (no uncommitted changes).
* **`pull` performs the following actions:**
	1. Retrieves changes from the specified remote
	2. Applies them to the local copy:
		1. If there are no local changes, "fast-forward" the remote changes
		2. If there are local changes, perform a `merge`

<!SLIDE >

# Pull

	git pull <remote-name> <refspec>

Example: If I have a remote called `origin` and I want to retrieve the branch called `master`:

	git pull origin master

.notes Switch to terminal for example
