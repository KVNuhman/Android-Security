## Android Debug Bridge (adb)

It is a versatile command-line tool that lets you communicate with a device.The adb command facilitates a variety of device actions, such as installing and debugging apps. adb provides access to a Unix shell that you can use to run a variety of commands on a device.


1. **Client**: Sends commands. The client runs on your development machine. You can invoke a client from a command-line terminal by issuing an `adb` command.
2. **Daemon (adbd)**: Runs commands on a device. The daemon runs as a background process on each device. The daemon on the Android device connects with the server on the host PC over USB or TCP, which connects to the client that is used by the end-user over TCP.
3. **Server**: Manages communication between the client and the daemon. The server runs as a background process on your development machine. The default port number on which the `adb` server runs is 5037.

 adb is included in the Android SDK Platform Tools package, which is installed at `${ANDROID_HOME}/platform-tools/`

After the PATH environment variable is set appropriately, we verify the program execution by typing adb in the terminal

![image](https://github.com/ananthan05/Android-Security/assets/140697378/87b4c59f-6e03-4ad3-b8d9-c5854560ab96)

##  Android Virtual Device (AVD) is started by typing the following command-

 ```
emulator -list-avds
```
 ![image](https://github.com/ananthan05/Android-Security/assets/140697378/e0eb3bcc-97ec-43e7-81d5-2992ae92c933)

```
emulator -avd Pixel_3a_API_34 -gpu off
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/5b1d2a1d-6422-4abf-8675-1f586875c869)

## Basic ADB Commands
 
 ```
adb devices
```
![image](https://github.com/ananthan05/Android-Security/assets/140697378/aa932a51-7291-4152-ba8e-1769af7ee65b)

```
 adb-s emulator-5554 shell
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/3ff72eee-7c14-4b86-8f9c-cbc105b30bf3)

Basic commands-

![image](https://github.com/ananthan05/Android-Security/assets/140697378/9b76694c-682d-4682-ac84-a546430806ec)


pm (Package Manager) is an utility program for retrieving various kinds of information related to theapplication packages that are currently installed on the device.
 
```
pm list packages
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/a8569181-e487-492b-8ab3-3e6e11ee379d)

```
pm list packages | grep youtube
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/6b2362aa-70ac-48a6-87c7-3031cade0244)

> pm list packages has various options to configure the output.-3 option is used to filter and display only
show third party packages.-s option is used to filter and display only system packages

```
pm list packages -3
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/fdebde12-05ad-4267-95cb-7d859ad79991)


> To check the Process ID (PID) of the currently running applications, we use the ps-A command.
 
 ```
ps -A | grep youtube
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/f00bf598-bf52-4067-a1b4-17bf9fb15dca)

> pm path is used to get the path of the installed APK file.

```
pm  path com.google.android.youtube
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/70232106-71e0-4718-bebc-1639f5a2c75e)

then `Exit`

```
adb pull /product/app/YouTube/YouTube.apk
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/29989c6f-3f49-4e79-b15b-9545f943f535)

```
dir
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/b2d393d1-85b6-4045-afe0-cb37afb200f0)

```
echo "This is some file" > somefile.txt
```
```
adb push somefile.txt /sdcard/
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/1d945f0e-4bae-4194-be98-7dcf9d28db9b)

`somefile` got txt.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/c3f80efc-125c-4a7a-add0-a34d02d822a0)
