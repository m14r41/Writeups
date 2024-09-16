## Vulnerability Description

CSRF vulnerability was found in the `profile` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows attackers to trick another user to modify the users detials by crafted HTML page demonstrated to change details via the `edit-profile.php` URL.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /edit-profile.php                                                                        |


## Steps to Reproduce:


Step 1: Login with user first. ( 1st user created `test@gmail.com`). Navigate th Profle page and click on `edit`

Step 2: Navigate th Profle page and click on `edit`

Step 3: Enable intercept in burpsuite and Click on `Update`

Step 4: Right click `Engagement tool` -> `Generate CSRF Poc`

Step 5: Now modify the values of the parameters `fname`, `lname`, and `contact`. Click on `Test in browser` and copy the URL.

Step 6: In incognito login with user second. ( 2nd created user `test2@gmail.com`)

Step 7: Now pate the previous copied URL, It will show `Profile updated sucessfully`

Step 8. Now check the details for user  `test2@gmail.com` has been changed with crafted CSRF.



## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html
- https://portswigger.net/web-security/csrf/preventingt


