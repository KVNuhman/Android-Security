# CRYLOGGER

CRYLOGGER is a tool that checks Android apps for mistakes in how they use cryptography, which is a way to secure data. These mistakes, called crypto misuses, happen when the encryption methods aren't used correctly according to security guidelines.

## Here's how CRYLOGGER works:

1. **Automatic Detection:** CRYLOGGER finds crypto misuses in your Android app automatically.
2. **No Code Analysis Needed:** No need for manual code analysis, CRYLOGGER does it for you.
3. **How it Works:** It runs your Android app on the official Android Emulator.
4. **Testing Methods:** It tests your app either by randomly interacting with it (like a Monkey) or by using the actions you perform on the emulator's interface.

So, it's like having a tool that watches your app running on a virtual Android device and checks if it's using encryption properly without you having to dive into the code yourself.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/cf04d187-d29b-4d9c-b797-e426fc1d4982)

CRYLOGGER runs your app by using Monkey or the user-interface events you send to the emulator.

```
adb shell monkey -p your.package.name -v 500
```

For ex, as shown above frameworks and libcore can be changed accordingly to create a new android distribution and to have our emulator a different logging functionality.Likewise many changing logging functionality of the open source android OS and making it their own Android distributions.


![image](https://github.com/ananthan05/Android-Security/assets/140697378/e535534f-cec4-4a5b-88ed-8db9cd0c478e)

It will make logs and specifies the analysis made upon cryptographic functionalities of the application.


![image](https://github.com/ananthan05/Android-Security/assets/140697378/0acd4f00-af27-4a34-a0b1-c50147637f27)

Above is the repositories that contains source codes of the released android versions and by changing the logging functionality of the desired version of android, new distribution is created on our own.
