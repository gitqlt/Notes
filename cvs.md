CVS practical
====
**Show status**

    $ cvs -q update -d [-A]    
**List added files, directories**

    $ cvs ls
**List committed files since date**

    $ cvs history -a -c -D YYYY-MM-DD | awk '{print $7}' | sort | uniq
