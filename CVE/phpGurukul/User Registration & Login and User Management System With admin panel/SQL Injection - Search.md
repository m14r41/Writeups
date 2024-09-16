## Vulnerability Description

SQL Injection was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command  via the `searchkey` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin//search-result.php <br>- **Affected Parameter:** searchkey<br>- **Method:** POST <br> - **Type:**  Time time-based blind and UNION                                                       |


## Steps to Reproduce:


Step 1: Click on `Admin Pannel` to login as admin

Step 2: Provide Admin credential to login.

Step 3: In search bar, provide values `test` and enable burpsuite intercept to capture the request.

Step 4: Copy the all request and save in a file. ( Here name is given search-result.txt)

Step 5: Now run  `sqlmap` command `python.exe C:\sqlmap\sqlmap.py -r search-result.txt -p searchkey  --batch --curent-db`as shown in screenshot.

Step 6: Now notice that `searchkey` parameter is vulnerable with `time-based blind` and `UNION` Type SQL Injection. Current database is shown.

Step 7: Further more table are shown for current database `loginsystem`


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


