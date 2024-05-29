
## Reverse Engineering of Android App

1. APK Tool
   
![image](https://github.com/ananthan05/Android-Security/assets/140697378/d95e8520-5fff-4c22-8641-f6af80a05fc0)


Decomiplation: Trying to reach to Source Code From Executable File. Here .dex means Dalvik Executable Code Format

```
apktool d .\app-debug.apk -o test
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/a65b714b-c183-4e72-879d-9a2900f119d2)

We observe that the testsample directory does not contain the classes.dex and resources.arsc files previously present in the ZIP file. We observe that there is a apktool.yml file created in the directory. We also observe that there is another AndroidManifest.xml in a new directory called original. We also observe that there is a new directory called smali which was decompiled from the classes.dex file present in the original APK ZIP archive.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/3c21832e-57a0-4f43-aafd-67080026c3b2)

![image](https://github.com/ananthan05/Android-Security/assets/140697378/86d74ceb-f61b-4d8b-bce9-b8891bf253ad)

![image](https://github.com/ananthan05/Android-Security/assets/140697378/b6cdbe8f-af0e-4e7d-8058-902b81b8eccf)

## Now Jadx Tool

jadx is a Dex to Java decompiler. It is a command line and GUI tools for producing Java source code from Android Dex and Apk files

![image](https://github.com/ananthan05/Android-Security/assets/140697378/9ba325fc-b944-4488-bc31-be6db71a708e)

The decompiled JAVA source code is seen in the JADX window.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/2e2c4ac1-bad8-46b9-a87b-488a39142c49)


We can save the decompiled JAVA source code as a Gradle project.
