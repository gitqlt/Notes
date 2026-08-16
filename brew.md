brew.sh: Homebrew - The Package Manager for Everywhere
====

#### Check local modifications in a (PR) branch or main
    $ export HOMEBREW_NO_INSTALL_FROM_API=1
    $ cd "$(brew --repository homebrew/core)"
    $ brew style --fix --formula kpcli
    $ brew audit --strict --online kpcli
    $ brew reinstall --build-from-source kpcli
    $ brew test kpcli
    $ brew linkage kpcli
    $ brew lgtm --online

#### Modifying PR
    $ brew tap --force homebrew/core
    $ cd $(brew --repository homebrew/core)
    $ git remote -v; git branch -vv
    $ git remote add Jos https://github.com/josk/homebrew-core.git
    
    $ git fetch Jos kpcli-xml-parser-fix
    $ git switch --track Jos/kpcli-xml-parser-fix
    $ git config --local user.name jos; git config --local user.email 87870000+josk@users.noreply.github.com
    $ git remote -v; git branch -vv
    $ git fetch origin
    $ brew test kpcli
    $ brew lgtm                                                  # Looks Good To Me
    $ [ git rebase origin/main; ] brew lgtm; brew lgtm --online
    ... edit
    $ git status; git diff
    $ HOMEBREW_NO_INSTALL_FROM_API=1 brew reinstall --build-from-source kpcli
    $ brew test kpcli
    $ brew lgtm --online
    $ git commit [--amend]
    $    git push --force-with-lease Jos kpcli-xml-parser-fix (https auth with PAT)
    $    or
    $    git remote set-url Jos git@github.com:joseph2021k/homebrew-core.git
    $    git push --force-with-lease Jos kpcli-xml-parser-fix  (SSH auth)
