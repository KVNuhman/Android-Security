Install DIVA(Damn Insecure and Vulnerable APP) by using the following adb command.

``` abd install diva-beta.apk```

## 1. Insecure Logging

Insecure logging occurs when developers intentionally or unintentionally log sensitive information such as credentials, session IDs, financial details etc...

To get the logcat information type in ` adb logcat | grep-i "credit card" ` for Linux or `adb logcat | Select-String "credit card"` for Windows.

In the app type in some number in the EditText field and click `check out` button. A toast message saying an error occured is shown and this error has been logged in logcat along with the input entered.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/c09322c5-4345-4851-9426-4566f4bb8b8e)

The Decompiled source code can be viewed using JADX to see the LogActivity class where the vulnerability occurs.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/b13feb89-e720-4b08-97e2-017dafc9c3cb)

## 2. Hardcoding Issues- Part 1

Developers sometimes will hardcode sensitive information for ease.

If we observe HardcodeActivity in the decompiled source code, the vendor key has been hardcoded in to the source code. This can be used to gain unauthorised access.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/d3c0a896-acca-4821-8225-282eb49b39f2)

Enter the above vendor key in the app and toast message will apppear saying Access Granted.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/8a36b777-8c84-4551-a631-fe6df0719f7c)

## 3. Insecure Data Storage- Part 1

Insecure data storage is the result of storing confidential information insecurely on the system i.e. poor encryption , plain text, access control isseus etc...

Enter a username and password in the given EditText fields and click on `SAVE` button.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/124de054-9023-4361-a41b-7be37be55994)

Use the adb shell to explore the file sytem used by the application.

Inside the /data/data/jakhar.aseem.diva directory, notice that there are databases and shared_prefs directory.

Viewing the `.xml` reveals the username and passsword we used earlier to login to the application.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/5f672abc-99ff-49fe-9e06-b9dcfe739971)

The piece of code that cause this vulnerability can be seen by decompiling the app using JADX.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/ee45b494-3cc0-49bb-9c9e-f766d01f3bf1)

## 4. Insecure Data Storage- Part 2

Enter a username and password in the EditText section.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/c8300e17-2b2e-4323-a217-54a01e1f71eb)

Use adb shell to explore the file system used by the application.

The application data aswell as it's database and shared_prefs is stored in the location  `/data/data/jakhar.aseem.diva directory` .

There is a new file in the database folder.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/abc6d385-1f5d-4e75-87dd-4bef40d8baaf)

Use sqlite3 to interact with the database file tp reveal all the tables present and list the username and password. Open the `ids2` database  and enter `select * from myuser;` to view the saved username and password

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/1088a713-09f7-4ba6-bcc3-48a8a8e60e0f)

The piece of code that cause this vulnerability can be seen by decompiling the app using JADX.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/7fbd9399-1c21-4054-b031-d33889c0cb6d)

## 5. Insecure Data Storage- Part 3

Enter a username and password in the EditText field.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/f50c7cb8-cc7f-4db1-b14b-67265f14432e)

Use adb shell to explore the file system used by the application.

Inside the /data/data/jakhar.aseem.diva directory, observe that there is a new file with the name `uinfo-1455578291tmp`. Display the contents of the file using the `cat uinfo-1455578291tmp ` command to reveal the username and password.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/1fdd5881-016c-47b5-b41a-519c076d2b46)

The piece of code that cause this vulnerability can be seen by decompiling the app using JADX.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/b3d2c561-6323-4f57-9015-639ca2cedfd4)

## 6. Insecure Data Storage- Part 4

Enter a username and password in the EditText field.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/be93e3c0-3706-4318-bb99-1040a2429fa1)

The piece of code that cause this vulnerability can be seen by decompiling the app using JADX. It shows us the location and name of the file where the username and password is being stored.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/da3a2feb-b3cf-47f7-a6d9-078ddd213245)

The location of the file is in sdcard. Since it is hidden use `ls -a` to view the filename and use `cat` to view its contents.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/12bcf767-f1ce-4e34-ad18-f27d2b58d63b)


