### Scenario one [1]

#### Steps to reproduce :

1. Register a user.
2. Register the same username again.

#### Actual result :

Server terminates with `peewee.IntegrityError`. (با ریجستری تکراری سرور کرش میکند) bug!

#### Expected result : 

Return a proper error message such as: **"User already exists"**.

[لطفاً برای دانلود ویدیوی سناریوی اول کلیک کنید](https://raw.githubusercontent.com/mjavadtavakoli/graph-qa/main/other/MT-001-crash-server.mov)

---

### Scenario one [2]

#### Steps to reproduce:
Sending a json file with invalid data

#### Actual result :
Preventing the client from sending invalid data in the correct manner(کلاینت از ارسال فایل با داده نا معتبر جلو گیری کرد)



[لطفاً برای دانلود ویدیوی سناریوی دوم کلیک کنید](https://raw.githubusercontent.com/mjavadtavakoli/graph-qa/main/other/MT-002%20-%20Invalid%20JSON.mov)

---

### Scenario one [3]

#### Steps to reproduce :
Sending a json file that does not exist in the project directory

#### Actual result : 
Json file does not exist. (نمایش خطا به درستی)


[لطفاً برای دانلود ویدیوی سناریوی سوم کلیک کنید](https://raw.githubusercontent.com/mjavadtavakoli/graph-qa/main/other/MT-003%20-%20Missing%20File.mov)

---
### Scenario one [4]

### Steps to Reproduce:

1. Send a request with an unsupported command (e.g., `hello`).
2. Observe the server and client responses.

### Actual Result (Current Implementation):

The server crashes with a `KeyError`, and the client receives the raw error message (`'hello'`).(کلاینت جزیات فایل را بدون برسی ارسال کرد برای سرور و سرور پس از برسی برخورد با دستور پشتیبانی نشده از ادامه کار کردن جلو گیری کرد و داون شد) bug!

### Expected Result:

The server should reject the unsupported command, return an appropriate error message, and continue running.


