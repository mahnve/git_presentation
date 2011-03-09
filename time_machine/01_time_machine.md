!SLIDE commandline incremental
# Git reset 

    $ cat tmp.txt

    foo
    another edit
    minor edit

    $ git reset 40fd97

    HEAD is now at 40fd970 another edit

    $ cat tmp.txt

    foo 
    another edit
    
!SLIDE bullets

# Reset options

* hard - resets index and working tree
* mixed - resets index, leaves working tree
* soft - leaves both index and working tree
