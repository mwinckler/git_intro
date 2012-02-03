<!SLIDE subsection>
# Repo Man #
## The Adventurous Life of a Version Controller

_or_

### How I Learned To Stop Subverting And Love The DVCS
<br /><br /><br /><br />
by Matt Winckler  
_(mwinckler@intera.com)_

3 Feb 2012

<!SLIDE bullets incremental>
# What is version control?

## Version control is...

* A way to keep track of changes in files
* A structured way to collaborate between developers
* Never having to say "I'm sorry"


<!SLIDE bullets incremental>

# Why should I use version control?

## Some obvious reasons:

* It keeps previous versions of files
* It merges other people's changes for you
* It shows a history of the code


<!SLIDE bullets incremental>

# Why should I use version control?

## Some less obvious reasons:

* It helps you fix bugs in deployed code
* It gives you freedom to experiment
* It can make audits easier to handle

<!SLIDE bullets incremental>

# What sorts of things should be controlled?

* **_Everything_ that doesn't get created as part of your build process**
* **...and _nothing_ that does**

<!SLIDE bullets incremental>

# The traditional model of version control

* Centralized version control systems rely on one central server keeping the "canonical" version.
* There are several downsides to this.

<!SLIDE bullets incremental>

# What does "DVCS" mean?

* A **Distributed Version Control System** is a VCS that doesn't rely on a central server.
* Instead, each copy of the repository is a _full_ repository--including history.
* Distributed repositories can swap changes with each other.

<!SLIDE >

# No server?<br />What madness is this?!

.notes No server. If this is madness, I don't want to be sane.

<!SLIDE bullets incremental>

# What about collaboration?

* Well, what about it?
* DVCS repositories communicate as peers.
* [You don't even need a special server for collaboration.](http://www.jedi.be/blog/2009/05/06/8-ways-to-share-your-git-repository/#fileshare) (But it's good to have one.)

<!SLIDE bullets incremental left>

# Why should I use a **_D_**VCS?

* **Speed:** The Tortoise[SVN] versus the...Git
* **Redundancy:** Each clone is a full repository
* **Mobility:** Work on an airplane? No problem.
* **Scaling:** Large numbers of files