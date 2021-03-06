# ADB, Emulator and Git commands
- [ADB Commands](#adb-commands)
- [Emulator](#emulator)
- [Git commands](#git-commands)

## ADB Commands

#### Basics
- `adb start-server` - Start ADB server

- `adb kill-server` - Stop/Kill server  
- `adb devices` - Lists the connected android devices  
- `adb get-state` - state of the device  
- `adb get-serialno` - Get device serial number  
- `adb push [source] [destination]` - Copy files from computer to phone.   
eg, adb push `E:\Path\to\file.mp4" "/sdcard/Downloads/video.mp4`   
- `adb pull [source] [destination]` - Copy files from phone to computer.  
- `adb backup -all` - backup the app data  
- `adb restore "path/to/backup.adb"` - Restored the files  
- `adb reboot-recovery` - Reboot device on recovery mode  
- `adb reboot-bootloader` - Reboot on bootloader mode  
- `adb fastboot` - Reboot on fastboot mode 
#### Remote device connection 
- `adb tcpip 5555` - Start adb in 5555 port  

- `adb shell ip addr show wlan0` - Get the IP address of connected smartphone, copy inet address from result  
- `adb connect [ip-address]` - connects the device to computer remotely if both devices shares same wifi network  
- `adb disconnect` - ends session 
#### Util commands
- `adb install "path/to/file.apk"` - Install apk  

- `adb -s [serial-number] install "path/to/file.apk"` - If multiple devices connected, install app to specific device using serial number.-   
- `adb uninstall -k <package-name>` - Uninstall apk without deleting data
- `adb shell screencap -p "/path/to/screenshot.png"` - Take screenshot from device
- `adb shell screenrecord "/path/to/record.mp4"` - Screen Record from device
- `adb shell logcat` - Pull logs from device  
- `adb shell monkey -p com.myAppPackage -v 10000 -s 100` - monkey tool is generating 10000 random events on the real device
- `adb shell dumpsys activity activities | sed -En -e '/Running activities/,/Run #0/p'` - prints current tasks and activity backstack
- `adb shell pm uninstall com.example.MyApp` - Uninstalls app
- `adb shell pm clear [package-name]` - Deletes all data associated with a package.
- `adb shell am start -W -c android.intent.category.HOME -a android.intent.action.MAIN` or `adb shell input keyevent 3` - Goto HOME
- `adb shell am start -a android.intent.action.CALL -d tel:+972527300294` - Make a call

#### Key events
- `adb shell input keyevent 3` - Home btn

- `adb shell input keyevent 4` - Back btn
- `adb shell input keyevent 5` - Call
- `adb shell input keyevent 6` - End call
- `adb shell input keyevent 26`  - Turn Android device ON and OFF. It will toggle device to on/off status.
- `adb shell input keyevent 27` - Camera
- `adb shell input keyevent 64` - Open browser
- `adb shell input keyevent 66` - Enter
- `adb shell input keyevent 67` - Delete (backspace)
- `adb shell input keyevent 207` - Contacts
- `adb shell input keyevent 220 / 221` - Brightness down/up
- `adb shell input keyevent 277 / 278 /279` - Cut/Copy/Paste
Refer [KeyEvent](https://developer.android.com/reference/android/view/KeyEvent.html) for more. 


#### Quick links
- Connect multiple devices remotely using adb [Ref link](https://android.stackexchange.com/a/137615/263737)

- `adb exec-out run-as YOUR.APP.ID cat /data/data/YOUR.APP.ID/shared_prefs/SHARED_PREF_NAME.xml` - Read SharedPref file from device 

## Emulator
- When internet/wifi not working in the emulator - Go to your android-sdk/emulator and run, this will start the emulator `./emulator -avd YOUR_EMULATOR_NAME -dns-server 8.8.8.8,8.8.8.4`

- To know the name of emulator - `./emulator -list-avds`

## Git commands
- `git reset --soft HEAD~1` - Undo local commit

- `git config user.name` - Username, Can be updated like `git config user.name "Naveen"`, To globally update use `git config --global user.name "Naveen"` 
- `git config user.email` - Email address, Can be updated like `git config user.email "something@gmail.com"`, To globally update use `git config --global user.email "something@gmail.com"` 

#### Quick links
- [GitReady](http://gitready.com/) - Learn git one commit at a time