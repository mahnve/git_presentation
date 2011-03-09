Intro
-----

We will talk about Distributed Version Control Systems, how they work and why
you should use them. Does that match your expectations?

Q: Anybody in here using DVCS today?
Q: How many are not using version control at all?
Q: Subversion
Q: CVS, TFS, Clearcase ...

About me
--------

Started working for a startup a few years back, as only developer.  Wanted to
be able to work offline, and wondered if I could take svn repo offline.
Started looking into it.

Main contenders back then was git, Mercurial, bzr and svk. Svk seemed like a
mutant, bzr was slow and git was incredibly complex and Mercurial was just
right. 

Used hg for a year, during a time where git got a lot easier to use, and a
large number of people migrated to it.

These days I favor git, but don't mind using Mercurial. I do have a very hard
time accepting centralized VCS though.

How centralized VCS work
------------------------

Problems: 

* Offline - No such thing
* Branching - Big things 
* Small commits - implemented in IDE's instead
* Merging - Normally suck at branching

How Decentralized VCS work
--------------------------

* Pull style collaboration
* Central master repository

Projects using Git
------------------

Size
----

After converting to Git, a Rails checkout in is 13M. A single checkout is 9M.
Rails svn repo was 115 M.


git commit -a -m 'minor edit' git checkout master vim test.txt
| Whoah! Where did the text go?
git log git merge something_else git log git branch -d something_else
Remote
Deleting branches
git -d branchname
| asserts that changes are merged
git -D branchname
| hard delete
Resetting merges
git reset --hard HEAD
git reset --hard ORIG_HEAD
| if you already commited
Remote branches
| git can follow remote branches, will not get into details
| ssh, http,  https or git
| a clone is a complete copy
GitHub
Copying files
git cp
git mv
Fixing history
| [image: git_workflow_overview.svg]
git co <old>
vim test.txt
git commit -m 'message'
git st
| Detached head
| Will get back to branches
gitk
git co -b 'a branch'
gitk
git rebase master
git co master
git merge b
git branch -d b
Recovering files
git checkout <filename>
| for one file
git reset --hard HEAD
| soft leaves index and working tree
| mixed resets index but not working tree
git stash <message>
| working on something, need to put it away temporarily
git stash apply
| to go back to where you were
Ignoring files
| .gitignore
|
| log/* etc
git bisect
git bisect start
git bisect bad <rev>
git bisect good master
git bisect bad
git bisect good
Working remote
remotes
git add remote another /home/mahnve/tmp/gittmp2
git pull another
GitHub
| [image: github.svg]
Set up new repo at github
git-svn
Problems deciding?
| [image: gitvsmercurial.svg]
| Help can be found at http://www.gitvsmercurial.com
Thankyou!
| [image: thankyou.svg]
