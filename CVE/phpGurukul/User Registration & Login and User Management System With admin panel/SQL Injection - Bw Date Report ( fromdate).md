## Vulnerability Description

SQL Injection was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command  via the `fromdate` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin/bwdates-report-result.php <br>- **Affected Parameter:** fromdate<br>- **Method:** POST <br> - **Type:**  Time time-based blind                                                    |


## Steps to Reproduce:


**Step 1:** Click on `Admin Pannel` to login as admin

![image](https://github.com/user-attachments/assets/58d0eaa7-363d-4f6c-bf43-e9ce8b45185a)

**Step 2:** Provide admin credential and click on `login`

![image](https://github.com/user-attachments/assets/cde9986d-bb69-4187-8cec-9fd479ffa578)

**Step 3:** Clikc on `B/w Date Report`. Select the `From Date` and `To Date`, Enable intercept in burpsuite to cpature the request and click on `Submit`

![image](https://github.com/user-attachments/assets/a257209a-7f1a-47d5-9089-8b152d39b23d)

**Step 4:** Copy the request request and save in a file. ( Here name is given `report-result ( todate - param).txt`)

![image](https://github.com/user-attachments/assets/24ae0998-11db-4236-8a82-db822b6e9fe8)

**Step 5:** Now run  `sqlmap` command and also specify the parameter `python.exe C:\sqlmap\sqlmap.py -r reports-result.txt -p fromdate --batch --current-db --flush-session`, and observer POST parameter `fromdate` is vulnerable.

![image](https://github.com/user-attachments/assets/36751068-24c0-42bf-8ed2-eed31c4cdf25)

**Step 6:** `fromdate` parameter is vulnerable with `time-based blind` Type SQL Injection. Current database is retrived sucessfully.

![image](https://github.com/user-attachments/assets/15054fac-90c2-4a58-a78e-e09d1c7ff595)

**Step 7:** Further more table are also retrived sucessfully for current database `loginsystem`

![image](https://github.com/user-attachments/assets/22f9d01c-369f-4600-87fb-525d56d8ccd7)


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


