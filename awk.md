gawk: pattern scanning and processing language
====

**Selected items from two linked lines**

    $ cat ... | awk '
    /device_name{/ { print striD=gensub( /.*secureBT="([^"]*).*/, "\\1", "g", $1) " runs PromEx " striV }
    /export_info{/ { striV=gensub( /.*version="([^"]*).*/, "\\1", "g", $1) }'
    
