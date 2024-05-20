adb: Android Debug Bridge
====

**Fingerprint of public key**

    $ awk '{print $1}' < ~/.android/adbkey.pub \
      | openssl base64 -A -d -a | openssl md5 -c | awk '{print $2}' | tr '[:lower:]' '[:upper:]'
**Install apk**

    $ adb install -r -t ./app/build/intermediates/apk/debug/app-debug.apk
    $ adb shell pm list packages | grep promex
**Start application**

    $ adb shell am start -n com.mmg.dev.promex/.MainActivity -a android.intent.action.MAIN
      [ -c android.intent.category.LAUNCHER -f 0x50200000 ]
    $ adb shell monkey -p com.mmg.dev.promex -v 500
**Logcat buffer size**

    $ adb logcat -b all -g
    $ adb logcat -G 64M (default: -b main,system,crash: 256 kiB)
