## Lecture 9

## 11. Access Control Issues – Part 3

![image](https://github.com/ananthan05/Android-Security/assets/140697378/ac068dec-59ec-49e8-a9d5-b2826c966629)

Let’s Create a PIN and Access the Private Notes via the Generated PIN.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/8c2a297d-f17d-43f4-8817-314d2a9eaa34)

![image](https://github.com/ananthan05/Android-Security/assets/140697378/d2cc6b34-6211-4feb-bec3-8fc1a79e4e8a)

Our Goal is to access the Private Notes without interacting with the application,

![image](https://github.com/ananthan05/Android-Security/assets/140697378/910c101d-de97-4f61-a062-71a2ad9588b0)

2 Files has been logged while creating PIN and Viewing the Private Notes. Analyze the Source code in the JADX.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/ad890fc9-82be-45fe-86a4-22c089a66a82)

![image](https://github.com/ananthan05/Android-Security/assets/140697378/b4b87bd5-1100-4676-8c0d-ec803c927ad4)

## AccessControl3Activity

In our `AccessControl3Activity`, we store our PIN using a `SharedPreferences` object. This PIN is used for authentication.

When the correct PIN is entered, it launches the `AccessControl3NotesActivity` activity. This activity validates the entered PIN before showing the notes via a query to `NotesProvider.CONTENT_URI`. 

The `NotesProvider` is a content provider that dumps all of the notes.

To dump the content provided by `NotesProvider`, you can use the following command in your terminal:

```bash
adb shell content query --uri content://jakhar.aseem.diva.provider.notesprovider/notes/
```
