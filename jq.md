jq: JSON processor
====

**Select a single item**

    $ cat ... | jq -r '.[].targets[0] | split(":")[0]'
    $ cat ... | jq -r '.[].targets[0] | split(":")[0][1:-1]' (shorten the output text example)
    
