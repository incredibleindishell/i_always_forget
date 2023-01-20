
Adding Burp certificate (android 7 and above):

https://blog.ropnop.com/configuring-burp-suite-with-android-nougat


Login to mobile device:

`abd shell`

To extract APK installed in mobile phone
==================
`adb shell pm list packages`

`adb shell pm path <packagename>`

`adb pull <path> app.apk`

  
Frida
=====

<h5>Install</h5>

`pip3 install frida==15.2.2`


Upload frida server to the mobile device to 

`/data/local/tmp/`

<h5>On mobile device:</h5>

start frida start:

`./frida-server`

<h5>Using frida script to hook a mobile app:</h5>

`frida --codeshare sowdust/universal-android-ssl-pinning-bypass-2 -f com..app_ -U --no-pause`




