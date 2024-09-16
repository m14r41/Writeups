## Vulnerability Description

SQL Injection was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. Allows remote attackers to execute arbitrary SQL command  via the `searchkey` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin//search-result.php <br>- **Affected Parameter:** searchkey<br>- **Method:** POST <br> - **Type:**  Time time-based blind and UNION                                                       |


## Steps to Reproduce:


**Step 1:** Click on `Admin Pannel` to login as admin
![image](https://github.com/user-attachments/assets/cb6510e4-d0df-4e05-bdf3-0cf6a0d926e4)

**Step 2:** Provide Admin credential to login.
![image](https://github.com/user-attachments/assets/8e2cf6d0-b990-4821-bca7-83d79172575a)

**Step 3:** In search bar, provide values `test` and enable burpsuite intercept to capture the request.
![image](https://github.com/user-attachments/assets/02cbcce7-ef1c-4579-8997-929f25e8cd17)

**Step 4:** Copy the all request and save in a file. ( Here name is given search-result.txt)
![image](https://github.com/user-attachments/assets/3564a10e-4abf-418b-a361-b0cbea1b7734)

**Step 5:** Now run  `sqlmap` command `python.exe C:\sqlmap\sqlmap.py -r search-result.txt -p searchkey  --batch --curent-db`as shown in screenshot.
![image](https://github.com/user-attachments/assets/c50d3812-e402-424e-8e24-020bb549936c)

**Step 6:** Now notice that `searchkey` parameter is vulnerable with `time-based blind` and `UNION` Type SQL Injection. Current database is shown.
![image](https://github.com/user-attachments/assets/1394bc04-a61b-485c-b93a-55fc29ddbc8e)

**Step 7:** Further more table are shown for current database `loginsystem`
![image](https://github.com/user-attachments/assets/56cbcca7-1214-47e2-b96d-cf9728e97deb)


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/sql-injection#how-to-prevent-sql-injection


