!SLIDE commandline incremental
# Stashing

    $ echo temp change >> tmp.txt    

    $ git stash 

    Saved working directory and index state WIP on master: 40fd970 another edit
    HEAD is now at 40fd970 another edit

    $ git status

    # On branch master
    nothing to commit (working directory clean)

    $ git stash pop

    # On branch master
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    #	modified:   tmp.txt
    #
    no changes added to commit (use "git add" and/or "git commit -a")
    Dropped refs/stash@{0} (254470f2880fce9f95df249a15cd29d3a7c5f863)

    



