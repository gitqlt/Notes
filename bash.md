bash: Bourne-Again SHell, a UNIX command interpreter
====

**Find any difference in loop, exit at error**

    $ for Fi in $(find . -name \*.py | egrep -v 'dir1/hg|dir2/thirdparty') ; do 
      diff $Fi /tmp/QZ/mergeserver_hgc/$Fi || { echo "ERROR $Fi"; break; }; done
      
**List**

    $ ./gggg
