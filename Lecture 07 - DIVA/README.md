## 7. Input Validation Issues- Part 1

Enter some values in the EditText field.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/49f52f90-b8ee-4629-a826-2a3ade3329bb)

By observing the `MainActivity`, it can be see that the particular functinality uses `SQLInjectionActivity.class`

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/0368569b-01a4-497a-9c30-f2f6fac76db1)

The following piece of codde shows that the fuctionality has a SQL injectino vulnerbaility.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/41b5993b-04e1-478a-ae1b-b4248ec51a2f)

Enter 1' OR 1=1-- so that the above SQL query becomes :
```SQL
SELECT * FROM sqliuser WHERE user ='1' OR 1=1--' 
```

The WHERE clause condition gets evaluated to FALSE or TRUE which is equivalent to TRUE, hence all the records in the database are displayed in the Toast message.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/6c70e466-4e10-4e66-9556-aa3bedcac7cd)

## 8. Input Validation Issues- Part 2

Enter some values in the EditText field.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/44460cb4-c2fb-4c7d-a310-6dd1eb90f8ff)

Enter a sensitive path like `file:///data/data/jakhar.aseem.diva/shared_prefs/jakhar.aseem.diva_preferences.xml`

Which only the application has access to and normal user of the device does not have access to. We can observe that the file contents are displayed in the WebView.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/8fa36937-11f6-4689-8e84-979a6867efb8)

We observe the decompiled source code and open the InputValidation2URISchemeActivity in the JADX.

We observe that the user input value in the EditText field is used directly to load in the WebView without any sanitization or validation.

![image](https://github.com/KVNuhman/Android-Security/assets/46161259/b3be69f9-d4af-4410-ba81-d32fab5941ee)
