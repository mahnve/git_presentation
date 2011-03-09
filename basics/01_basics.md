!SLIDE commandline incremental

# Settings

    $ cat ~/.gitconfig

    [user]
	name = Marcus Ahnve
	email = marcus@ahnve.com
    [color]
            diff = auto
            status = auto
            branch = auto
            ui = true
    [apply]
            whitespace = nowarn
    [alias]
            ci = commit -a
            co = checkout
            st = status
            br = branch
    [github]
            user = mahnve
            token = <secret>
    [merge]
            tool = vimdiff3
    [mergetool "gvimdiff3"]
            cmd = gvim -f -d -c \"wincmd J\" \"$MERGED\" \"$LOCAL\" \"$BASE\" \"$REMOTE\"
    [mergetool "vimdiff3"]
            cmd = vim -f -d -c \"wincmd J\" \"$MERGED\" \"$LOCAL\" \"$BASE\" \"$REMOTE\"
    [core]
            autocrlf = input
            safecrlf = true

!SLIDE commandline incremental

#  List settings with git command

    $ git config --global -l

    user.name=Marcus Ahnve
    user.email=marcus@ahnve.com
    color.diff=auto
    color.status=auto
    color.branch=auto
    color.ui=true
    apply.whitespace=nowarn
    alias.ci=commit -a
    alias.co=checkout
    alias.st=status
    alias.br=branch
    github.user=mahnve
    github.token=<secret>
    merge.tool=vimdiff3
    mergetool.gvimdiff3.cmd=gvim -f -d -c "wincmd J" "$MERGED" "$LOCAL" "$BASE" "$REMOTE"
    mergetool.vimdiff3.cmd=vim -f -d -c "wincmd J" "$MERGED" "$LOCAL" "$BASE" "$REMOTE"
    core.autocrlf=input
    core.safecrlf=true

!SLIDE commandline incremental

#  Change settings with git command

    $ git config --global --add user.name 'Marcus Ahnve'

!SLIDE commandline incremental

# Make a repository

    $ git init

    Initialized empty Git repository in /home/mahnve/src/test/.git/

    $ touch tmp.txt
    
    $ git status

    # On branch master
    #
    # Initial commit
    #
    # Untracked files:
    #   (use "git add <file>..." to include in what will be committed)
    #
    #	tmp.txt

!SLIDE commandline incremental

# Add files

    $ git add .

    $ git status

    # On branch master
    #
    # Initial commit
    #
    # Changes to be committed:
    #   (use "git rm --cached <file>..." to unstage)
    #
    #	new file:   tmp.txt
    #

!SLIDE commandline incremental

# Commit changes

    $ git commit -m 'initial commit'                                                                                                                                                              ──master(Tue,Mar08)─┘

    [master (root-commit) 21a58a0] initial commit
    0 files changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 tmp.txt

!SLIDE commandline incremental

# Logs

    $ git log                                                                                                                                                                                     ──master(Tue,Mar08)─┘

    commit 21a58a0d71b1e2b2da47999a43b2bffacfc354af
    Author: Marcus Ahnve <marcus@ahnve.com>
    Date:   Tue Mar 8 22:59:42 2011 +0100

!SLIDE commandline incremental

# Change a file

    $ echo foo >| tmp.txt

    $ git status

    # On branch master
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    #	modified:   tmp.txt
    #

!SLIDE commandline incremental

# Add and commit again

    $  git commit -am 'change'

    [master d9bc3ef] change
    1 files changed, 1 insertions(+), 0 deletions(-)

!SLIDE commandline incremental

# Detailed logs

    $ git log --stat

    commit d9bc3ef1d51797517cc0bcc647cdd2e34d63ad3a
    Author: Marcus Ahnve <marcus@ahnve.com>
    Date:   Wed Mar 9 10:08:15 2011 +0100

        change

      tmp.txt |    1 +
      1 files changed, 1 insertions(+), 0 deletions(-)

    commit 21a58a0d71b1e2b2da47999a43b2bffacfc354af
    Author: Marcus Ahnve <marcus@ahnve.com>
    Date:   Tue Mar 8 22:59:42 2011 +0100

        initial commit

    0 files changed, 0 insertions(+), 0 deletions(-)

!SLIDE commandline incremental

# Logs with graphs

    $ git log --graph 

    * commit d9bc3ef1d51797517cc0bcc647cdd2e34d63ad3a
    | Author: Marcus Ahnve <marcus@ahnve.com>
    | Date:   Wed Mar 9 10:08:15 2011 +0100
    | 
    |     change
    |  
    * commit 21a58a0d71b1e2b2da47999a43b2bffacfc354af
      Author: Marcus Ahnve <marcus@ahnve.com>
      Date:   Tue Mar 8 22:59:42 2011 +0100
      
          initial commit

!SLIDE commandline incremental

# Short logs

    $ git log --pretty=oneline

    d9bc3ef1d51797517cc0bcc647cdd2e34d63ad3a change
    21a58a0d71b1e2b2da47999a43b2bffacfc354af initial commit
