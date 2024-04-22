jq: JSON processor
====

**Select a single item from a list**

    $ cat ... | jq -r '.[].targets[0] | split(":")[0]'
    $ cat ... | jq -r '.[].targets[0] | split(":")[0][1:-1]' (then shorten the output text)
    
