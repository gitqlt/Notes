Unbuffering the stdio
===
**Long running command**

    $ long_running_command | unbuffer -p grep 'pattern' | cat

**For longer pipelines, unbuffer each command (except the final one)**

    $ unbuffer xx | unbuffer -p yy | zz
