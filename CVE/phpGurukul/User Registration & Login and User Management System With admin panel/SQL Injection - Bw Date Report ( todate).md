## Vulnerability Description

SQL Injection was found in the `/bwdates-report-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command  via the `todate` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:**/admin/bwdates-report-result.php  <br>- **Affected Parameter:** todate<br>- **Method:** POST <br> - **Type:**  Time time-based blind

## Steps to Reproduce:


Step 1: Click on `Admin Pannel` to login as admin

Step 2: Clikc on `B/w Date Report`.

Step 3: Select the `From Date` and `To Date`, Enable intercept in burpsuite to cpature the request and click on `Submit`

Step 4: Copy the request request and save in a file. ( Here name is given `report-result ( todate - param).txt`)

Step 5: Now run  `sqlmap` command `python.exe C:\sqlmap\sqlmap.py -r "report-result ( todate - param).txt" -p todate --batch --current-db --flush-session`, and observer POST parameter `todate` is vulnerable

Step 6: `searchkey` parameter is vulnerable with `time-based blind` and `UNION` Type SQL Injection. Current database is retrived sucessfully.

Step 7: Further more table are also retrived sucessfully for current database `loginsystem`


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


