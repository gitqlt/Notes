gsettings: GSettings configuration tool
====

**List all keys recursively**

    $ gsettings list-recursively [schema]
      
**List all keys (excluding keys with relocatable schemas)**

    $ for sch in $(gsettings list-schemas); do for key in $(gsettings list-keys $sch); do val=$(gsettings get $sch $key); printf "Schema=%-50s Key=%-50s Value=%s\n" "$sch" "$key" "$val"; done; done
      
