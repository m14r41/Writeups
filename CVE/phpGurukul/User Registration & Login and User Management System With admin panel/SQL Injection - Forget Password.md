## Vulnerability Description

SQL Injection was found in the `/password-recovery.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command to get unauthorized database access via the `femail` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /password-recovery.php <br>- **Affected Parameter:** femail<br>- **Method:** POST <br> - **Type:**  Time time-based blind                                                        |


## Steps to Reproduce:


Step 1: Select `Already Register` to login

Step 2: Click on `Forgot Password`.

Step 3: Provide any email in `Email address` field and click on `Reset Password` Enable intercept in brupsuite to capture the request.

Step 4: Copy the all request and save in a file. ( Here name is given password-recovery)

Step 5: Now run  `sqlmap` command `python.exe C:\sqlmap\sqlmap.py -r password-recovery.txt --batch --dbs --flush-session`as shown in screenshot.

Step 6: Now notice that `femail` parameter is vulnerable and database is retrived

## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


