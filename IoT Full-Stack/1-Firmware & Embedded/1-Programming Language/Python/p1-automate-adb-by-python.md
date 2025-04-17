# Automate Android testing by Python
 To automate Android testing and its application testing, the best way to do that is by creating a Python script to handle it. In this project, we will explore the ADB commands and how to integrate them with a Python script.  
  
## Prerequisites  
  
This project requires the following elements:  
  
1.  **NOX emulator**: to emulate the Android environment, you can download it from the NOX OFFICIAL website.   
2.  **ADB**: Android Debug Bridge: it is to control the Android environment.  
3.  **Python3**: to automate the test  
  
## Steps  
  
Follow these steps to automate Android testing using Python:  
  
### 1- Enable X, Y positions on the screen:  
  
- Download and run the NOX emulator.  
- Go to Settings of the Android environment.  
- Navigate to About tablet and tap on Build number 5 to 6 times to enable the developer mode.  
- Go back to the main settings and select Developer options.  
- Scroll down and find Pointer location, then enable it. You should now see X and Y bars at the top of your emulator. We will use these X and Y positions to control the screen from ADB.  
  
### 2- ADB commands  
  
| Command | Description |  
|:----------------|:-------------------|  
| adb devices | list all adb devices available to connect |  
| adb connect 127.0.0.1:62001 | connect to the device with address 127.0.0.1:62001 |  
| adb install my\_apk.apk | Install **apk\_file.apk** |  
| adb shell pm list packages -f google | list all **app.package.name** name for application with name **google** |  
| adb shell monky -p app.package.name -c android.intent.category.LAUNCHER 1 | To start an application by its own **app.package.name**|  
| adb shell input tap 500 430 | Make an input touch on the touch screen on X: 500, and Y: 430 points.  
| adb shell input swap 500 430 500 230 100 | Make a swap action form X1:500, Y1:430 point to X2:500, Y2 230 in 100 ms|  
| adb shell input swap 500 430 500 430 250 | Make a long press at the same point for 250 ms|  
| adb shell input text \\"Amr%sAbdelghafar\\" | Insert text (%s - for spaces) |  
| adb shell input key event 82 | Push **menu** key |  
  
Some key events:  
  
- 0 --> \\"KEYCODE\_UNKNOWN\\"  
- 1 --> \\"KEYCODE\_MENU\\"  
- 2 --> \\"KEYCODE\_SOFT\_RIGHT\\"  
- 3 --> \\"KEYCODE\_HOME\\"  
- 4 --> \\"KEYCODE\_BACK\\"  
- 5 --> \\"KEYCODE\_CALL\\"  
- 6 --> \\"KEYCODE\_ENDCALL\\"  
  
The complete list of commands can be found on
[[https://developer.android.com/reference/android/view/KeyEvent.html]]
  
### 3- Python scripting  
  
Automate a sequence of orders by python on the NOX emulator  
```python  
import os  
import time  
  
# path for the ADB which comes with NOX emulator.  
path = "C:\\Program Files (x86)\\ox\\bin"  
  
# Change the directory to it.  
os.chdir(path)  
  
# checking for connected devices  
device = os.popen('adb devices').read().split('\', 1)[1].split('device')[0].strip()  
  
# connect to the selected device 172.0.0.1:62001  
print("Waiting for connection ...")  
connect = os.popen("adb connect " + device ).read()  
print(connect)  
  
#start Epic application  
os.system("adb shell monkey -p com.getepic.Epic -c android.intent.category.LAUNCHER 1")  
  
# select the PARENTS button  
time.sleep(3)  
os.system("adb shell input tap 340 1030")  
  
# swipe the page  
time.sleep(5)  
os.system("adb shell input tap 340 1030 340 650 100")  
  
# press the back key   
os.system("adb shell input keyevent 4")  
```  
  
By running this Python script, you can automate a sequence of commands on the NOX emulator for Android testing.  
  
Now you have the knowledge and tools to automate Android testing using Python and ADB commands.