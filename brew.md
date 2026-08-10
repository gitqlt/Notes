brew.sh: Homebrew - The Package Manager for Everywhere
====

#### Modifying my PR
    $ brew tap --force homebrew/core
    $ cd $(brew --repository homebrew/core)
    $ git remote -v; git branch -vv
    $ git remote add Jos https://github.com/jos/homebrew-core.git
    
    $ git fetch Jos kpcli-xml-parser-fix
    $ git switch --track Jos/kpcli-xml-parser-fix
    $ git config --local user.name jos; git config --local user.email 87870000+jos@users.noreply.github.com
    $ git remote -v; git branch -vv
    $ git fetch origin
    $ git rebase origin.main
    $ brew test kpcli
    $ brew lgtm --online
    ... edit
    $ git status; git diff
    $ HOMEBREW_NO_INSTALL_FROM_API=1 brew reinstall --build-from-source kpcli
    $ brew test kpcli
    $ brew lgtm --online
    $ git commit [--amend]
    $ git push --force-with-lease Jos kpcli-xml-parser-fix
