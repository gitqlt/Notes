adb: Android Debug Bridge
====

**Fingerprint of public key**

    $ awk '{print $1}' < ~/.android/adbkey.pub \
      | openssl base64 -A -d -a | openssl md5 -c | awk '{print $2}' | tr '[:lower:]' '[:upper:]'
