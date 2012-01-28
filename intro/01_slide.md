<!SLIDE >
# Repo Man #
## The Adventurous Life of a Version Controller

<!SLIDE bullets incremental>
# What is revision control?

## Revision control is...

* Software to keep track of changes
* Safeguard against data loss
* Never having to say "I'm sorry"

<!SLIDE >

# Why should I use version control?

## Some obvious reasons:

* It keeps previous versions of files
* It facilitates collaboration
* It shows a history of what you've done

<!SLIDE >

# Why should I use version control?

## Some less obvious reasons:

* It helps you fix bugs in deployed code
* It gives you freedom to experiment
* It can make audits easier to handle

<!SLIDE >

# The traditional model

(insert picture of server-based VCS here)

<!SLIDE >

# What does "DVCS" mean?

A **Distributed Version Control System** is a VCS that doesn't rely on a central server.

Examples: Git, Mercurial, Bazaar

<!SLIDE >

# No server?<br />What madness is this?!

No server. A DVCS stores the entire repository locally in its own special hidden folder in the root directory of your project.

<!SLIDE >

# What about collaboration?

Okay, fine: *sometimes* there's a server. DVCSes like Git can connect to remote servers to share changes - but they do so as peers, not the traditional client-server relationship you're familiar with.

Git can also share changes with no special server involved.

<!SLIDE >

# Why should I use a **_D_**VCS?

1. **Speed:** The Tortoise[SVN] versus the Hare
2. **Redundancy:** Each clone is a full repository
3. **Mobility:** Work on an airplane? No problem.
4. **Scaling:** Large numbers of files (not large files)