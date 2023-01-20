
Adding Burp certificate (android 7 and above):

https://blog.ropnop.com/configuring-burp-suite-with-android-nougat


Login -> abd shell

To extract APK installed in mobile phone
==================
adb shell pm list packages
adb shell pm path <packagename>
adb pull <path> app.apk
