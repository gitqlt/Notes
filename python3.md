Python3 is a major revision of Python(2),  
a high-level, general-purpose programming language
====

### Relative import (namespace packages, no __init__.py)
    ├── ./p0.py
    └── ./D1
        ├── ./D1/p1.py
        └── ./D1/D2
            └── ./D1/D2/p2.py
    p0.py: import sys; print( f'--- 0 --- {sys.modules.keys()}' ); import D1.p1        # --- BAD: from .D1 import p1
    p1.py: import sys; print( f'--- 1 --- {sys.modules.keys()}' ); from .D2 import p2  # --- BAD: import D2.p2
    p2.py: import sys; print( f'--- 2 --- {sys.modules.keys()}' )
          
    $ python3 p0.py     - OK
    $ python3 D1/p1.py  - ERR
           
### pip,virtualenv with minimal system footprint and with minimal system dependency
    # apt update
    # apt install --no-install-recommends python3

    # python3 -m venv -h
    # python3 -m venv v30 (shall not work. OK)

    # apt install --no-install-recommends wget     ca-certificates openssl
        ## wget https://bootstrap.pypa.io/get-pip.py; python3 ./get-pip.py --break-system-packages

    # wget -O - https://bootstrap.pypa.io/get-pip.py | python3 - --break-system-packages
    # pip3 list -v
    # which pip3; ls -lrt /usr/local/bin

    # pip3 install --break-system-packages virtualenv
    # pip3 list -v
    # which virtualenv; ls -lrt /usr/local/bin

    # virtualenv -h
    # cd /tmp; python3 -m virtualenv v3 (or: virtualenv v3)

# python3 -m venv -h
# python3 -m venv v30 (shall not work. OK)
