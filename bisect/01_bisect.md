!SLIDE commandline incremental
# So You Have An Error

    $ git bisect start

    $ git bisect bad

!SLIDE commandline incremental

# Find a Good Revision

    $ git checkout e8adad403f52c

    Note: checking out 'e8adad403f52c4'.

    You are in 'detached HEAD' state. You can look around, make experimental
    changes and commit them, and you can discard any commits you make in this
    state without impacting any branches by performing another checkout.

    If you want to create a new branch to retain commits you create, you may
    do so (now or later) by using -b with the checkout command again. Example:

      git checkout -b new_branch_name

    HEAD is now at e8adad4... history and roundup

!SLIDE commandline incremental

# Mark Revisions As Good Or Bad

    $ git bisect good

    Bisecting: 1 revision left to test after this (roughly 1 step)
    [5525ce7f14c667a9b63b17fab700395016db78f4] about and bullets

    $ git bisect good

    Bisecting: 0 revisions left to test after this (roughly 0 steps)
    [d9a77ce4e413fae35bff64d072232bbad951a4f1] remotes and tools
    
!SLIDE commandline incremental

# Mark the Final Revision

    $ git bisect bad

    d9a77ce4e413fae35bff64d072232bbad951a4f1 is the first bad commit
    commit d9a77ce4e413fae35bff64d072232bbad951a4f1
    Author: Marcus Ahnve <marcus@ahnve.com>
    Date:   Wed Mar 9 19:44:26 2011 +0100

        remotes and tools

    :100644 100644 b777d11f846fb6be51c1ddde1195d0496929c005 f6a8bb613ab2f51582444a443abe808fdaf2a90b M	notes.md
    :000000 040000 0000000000000000000000000000000000000000 3a05fdf21845da07668d49fbb350f856d3ccd25d A	remotes
    :000000 040000 0000000000000000000000000000000000000000 8e6702d84866839729eb6b734e9db1f591aa7c4e A	tools

!SLIDE commandline incremental

# Finish the Bisecting

    $ git bisect reset
    
    Previous HEAD position was d9a77ce... remotes and tools
    Switched to branch 'master'
    Your branch is ahead of 'origin/master' by 1 commit.




