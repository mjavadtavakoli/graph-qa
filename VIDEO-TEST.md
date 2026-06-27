### Scenario one [1]

#### Steps to reproduce :

1. Register a user.
2. Register the same username again.

#### Actual result :

Server terminates with `peewee.IntegrityError`. (با ریجستری تکراری سرور کرش میکند)

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

###Steps to Reproduce:

Create a JSON file containing an unknown command.
Start the server.
Run the client using the new JSON file.
Observe the server and client responses.

###Expected Result:

The application should reject the unsupported command and return a meaningful error message without stopping the server.

###Actual Result (Current Implementation):

The server throws an unexpected error because the command is not found in the command mapping.
