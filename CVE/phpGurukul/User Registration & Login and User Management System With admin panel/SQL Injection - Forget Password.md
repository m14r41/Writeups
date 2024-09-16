## Vulnerability Description

SQL Injection was found in the `/password-recovery.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command to get unauthorized database access via the `femail` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /password-recovery.php <br>- **Affected Parameter:** femail<br>- **Method:** POST <br> - **Type:**  Time time-based blind                                                        |


## Steps to Reproduce:


**Step 1:** Select `Already Register` to login

![image](https://github.com/user-attachments/assets/9b76b6b3-2b9f-47f6-94f6-89bebb3cd2a6)

**Step 2:** Click on `Forgot Password`.

![image](https://github.com/user-attachments/assets/c7086c85-24d4-410d-b9dc-7143cc57f405)

**Step 3: **Provide any email in `Email address` field and click on `Reset Password` Enable intercept in brupsuite to capture the request.

![image](https://github.com/user-attachments/assets/ae1c811b-c9dc-4d77-805e-08b22ed40a36)

**Step 4:** Copy the request and save in a file. ( Here name is given password-recovery)

![image](https://github.com/user-attachments/assets/6d5ea0f5-8b2d-409f-b891-4be39825d116)

**Step 5:** Now run  `sqlmap` command `python.exe C:\sqlmap\sqlmap.py -r password-recovery.txt --batch --dbs --flush-session`as shown in screenshot.

![image](https://github.com/user-attachments/assets/ddd7ada5-c993-4a7e-b88b-83a515120fee)

**Step 6:** Now notice that `femail` parameter is vulnerable and database is retrived

![image](https://github.com/user-attachments/assets/57ca6ee5-fd3c-4775-9af4-ae82c1054346)

## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


