gawk: pattern scanning and processing language
====

**Selected items from two linked lines**

    $ cat ... | awk '
    /device_name{/ { print striD=gensub( /.*secureBT="([^"]*).*/, "\\1", "g", $1) " runs PromEx " striV }
    /export_info{/ { striV=gensub( /.*version="([^"]*).*/, "\\1", "g", $1) }'
**Count of words line-by-line**

    $ awk '{print FILENAME, NR, NF}' /tmp/l3*.txt
    
