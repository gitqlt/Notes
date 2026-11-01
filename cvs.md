CVS practical
====
#### Show status
    $ cvs -q update -d [-A]

#### List added files, directories
    $ cvs ls

#### List committed files since date** (&#x1F534; BAD)
    $ cvs history -a -c -D YYYY-MM-DD | awk '{print $7}' | sort | uniq
   
#### Convert to git with legacy tool
    $ cvs-fast-export <remoteCVSrepo> >/tmp/cvsrepo.exp
    $ grep -E '^(M |D )' /tmp/cvsrepo.exp           # --- Check folder paths exist ! (no -s CLI switch)
    
    $ mkdir -p .../qfgGIT/<...>/<...>               # --- Replicated 
    
    $ mkdir -p <local-workdirs>/<workdir>           # --- Work
    $ cd <local-workdirs>/<workdir>
    $ git init --separate-git-dir .../qfgGIT/<...>/<...>
        $ cat /tmp/...exp | git fast-import         # --- Only when convert; Omit aniway
    $ git mv .gitignore dot.gitignore        
    $ git switch master; ls -l
