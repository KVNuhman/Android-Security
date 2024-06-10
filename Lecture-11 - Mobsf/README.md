Lecture 11 MobSF Tool 

1. Installing Mobsf Tool in Kali Linux VM

```
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
```

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/d8021792-ce3e-4edb-ac31-2376d44c4310)

2. Setting Up MobSF Tool

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/0d728ce8-27e8-443b-b3eb-a2266f8eade9)

```
`./setup.sh`  
```

Then run to install all the dependencies 

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/1ec8a49f-5daa-4656-9eea-5fe2a5ea977d)

first get into the virtual enviroment using the command 

```
. ./venv/bin/activate

```
![image](https://github.com/ananthan05/Android-Security/assets/140697378/fcee6f89-2ade-4728-a59d-3531f5114482)

The installation is succesful
use the command 
```
bash ./run.sh
```
To run mobsf tool

![image](https://github.com/ananthan05/Android-Security/assets/140697378/eb24f799-4f56-499f-9a64-e67619f97f06)


![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/2bb4d4b8-b5f7-4ab2-9e9b-6bf998bd480d)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/d38618e7-7529-4a89-a795-3b18a1b68d76)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/f9c5fd1f-f7f1-4d52-83b0-f4317fb33c8f)


Static Analysis:

Code Analysis: Scans the application's code for security vulnerabilities, including insecure API usage, hardcoded secrets, and configuration issues.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/b6de43a5-ff68-46d0-872b-e63b0dde64bd)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/db402f65-b26b-4dc3-8f69-d6b8eb8289ff)

list of Activities

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/7beabd24-6882-4486-9eed-94132dfe6c93)

Recent Scans 

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/b3c414aa-c2ce-4239-a7a1-1eea3dea8763)

Application Permissions

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/73775992-ff89-4988-ae08-6287d4cde9ca)

Binary Analysis: Decompiles and disassembles the application binary to identify potential security issues in the compiled code.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/e0c0d973-a56f-4cfd-82aa-41bc6bf1359d)

Manifest Analysis (Android): Analyzes the Android manifest file for permissions, activities, services, and other components to identify potential security misconfigurations.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/9cc852dc-ff51-4a7f-bac6-070715518455)

Code Analysis: 

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/8c69fa73-e9cf-433d-9cbe-49770c7a7667)


Overall Analysis:

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/63fee9b6-71cc-4f33-83c0-ed55657b3afb)
