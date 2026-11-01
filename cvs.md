CVS practical
====
#### Show status
    $ cvs -q update -d [-A]

#### List added files, directories
    $ cvs ls

#### List committed files since date** (&#x1F534; BAD)
    $ cvs history -a -c -D YYYY-MM-DD | awk '{print $7}' | sort | uniq
   
#### Convert to git with the cvs-fast-export tool (traditional)
    $ cvs-fast-export <remoteCVSrepo> >/tmp/cvsrepo.exp
    $ grep -a -E '^(M |D )' /tmp/cvsrepo.exp        # --- Check folder paths exist (no -s CLI switch in traditional tool)
    
    $ mkdir -p .../qfgGIT/<...>/<...>               # --- Replicated git store
    
    $ mkdir -p <local-workdirs>/<workdir>           # --- Work
    $ cd <local-workdirs>/<workdir>
    $ git init --separate-git-dir .../qfgGIT/<...>/<...>
    $ ls -la
    
        $ cat /tmp/cvsrepo.exp | git fast-import    # --- Only when convert; Omit aniway      
    $ git switch master; ls -l
    $ git mv .gitignore dot.gitignore
    $ git config --local user.name <>; git config --local user.email <>@<>
