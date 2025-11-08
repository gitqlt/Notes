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
           
