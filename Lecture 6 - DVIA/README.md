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

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/f060a07a-d440-4e0f-80cd-dcab94ce2901)


