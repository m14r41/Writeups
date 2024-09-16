## Vulnerability Description

CSRF vulnerability was found in the `profile` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows attackers to trick another user to modify the users detials by crafted HTML page demonstrated to change details via the `edit-profile.php` URL.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /edit-profile.php                                                                        |


## Steps to Reproduce:


**Step 1:**Login with user first. ( 1st user created `test@gmail.com`). Navigate th Profle page and click on `edit`

![image](https://github.com/user-attachments/assets/18c1f7c3-edef-4ea3-a53d-4b23792a9fb5)

**Step 2:** Enable intercept in burpsuite and Click on `Update`

![image](https://github.com/user-attachments/assets/cac45d86-8ee3-476c-9593-4abb877c360a)


**Step 3:** Right click `Engagement tool` -> `Generate CSRF Poc`

![image](https://github.com/user-attachments/assets/dac8732d-a214-4e11-bbc5-01d0fda27fe9)


**Step 4:** Now modify the values of the parameters `fname`, `lname`, and `contact`. Click on `Test in browser` and copy the URL.

![image](https://github.com/user-attachments/assets/d73ca2a8-d9b8-4351-a1af-abca91a5484f)

**Step 5:** In incognito login with user second. ( 2nd created user `test2@gmail.com`)
![image](https://github.com/user-attachments/assets/5d6b5875-cbb5-4994-9d99-9c62549b7393)

**Step 6:** Now pate the previous copied URL, It will show `Profile updated sucessfully`

![image](https://github.com/user-attachments/assets/2a6281f1-8fc4-4239-bea8-7ca01da8ccd5)

**Step 7**. Now check the details for user  `test2@gmail.com` has been changed with crafted CSRF.

![image](https://github.com/user-attachments/assets/ea734e8f-54be-4cae-82b4-14704d74a220)



## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/csrf/preventingt


