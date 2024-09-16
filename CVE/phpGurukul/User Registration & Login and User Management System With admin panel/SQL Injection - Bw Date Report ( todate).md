## Vulnerability Description

SQL Injection was found in the `/bwdates-report-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command  via the `todate` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:**/admin/bwdates-report-result.php  <br>- **Affected Parameter:** todate<br>- **Method:** POST <br> - **Type:**  Time time-based blind

## Steps to Reproduce:


**Step 1**: Click on `Admin Pannel` to login as admin

![image](https://github.com/user-attachments/assets/a44a8c21-f23b-4795-9cce-7ec150d43141)

**Step 2:** Clikc on `B/w Date Report` and Select the `From Date` and `To Date`, Enable intercept in burpsuite to cpature the request and click on `Submit`

![image](https://github.com/user-attachments/assets/ba3606d6-4be8-47db-affd-059237620cd2)

**Step 3:** Copy the request request and save in a file. ( Here name is given `report-result ( todate - param).txt`)
![image](https://github.com/user-attachments/assets/1ec80a8a-34cb-457f-aad3-f28d86c4ef58)

**Step 4:** Now run  `sqlmap` command `python.exe C:\sqlmap\sqlmap.py -r "report-result ( todate - param).txt" -p todate --batch --current-db --flush-session`, and observer POST parameter `todate` is vulnerable
![image](https://github.com/user-attachments/assets/1c6161b3-4ae8-4f49-9443-8038cc5dc73f)

**Step 6:** `searchkey` parameter is vulnerable with `time-based blind` and `UNION` Type SQL Injection. Current database is retrived sucessfully.
![image](https://github.com/user-attachments/assets/9ef9664a-6d91-4b8a-bbe8-fe1e51ab607c)

**Step 7:** Further more table are also retrived sucessfully for current database `loginsystem`
![image](https://github.com/user-attachments/assets/af73abd2-5c31-477d-acef-ee35ca0d933a)


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


