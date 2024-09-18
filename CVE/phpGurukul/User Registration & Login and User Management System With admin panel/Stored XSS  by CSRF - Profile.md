## Vulnerability Description

Stored Cross-Site Scripting (XSS) vulnerability by CSRF was found in the `profile.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers to execute arbitrary scripts via the CSRF attack in /http://localhost/loginsystem/profile.php URL.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:**/profile.php <br>- **Affected Parameter:** fname, lname<br>- **Method:** POST                                                                           |


## Steps to Reproduce:

Step 1: Login into application as normal user.

Step 2: Navigate to Profile page.

Step 3: Carft the csrf poc and Cop.

Step 4: Visite webhook.site click -> edit the content and paste copied csrf html

Step 5: Open the url in logged in browser

Step 6: Observe the that csrf is attack is sucessfull and data stored on server.

step 7: Observer the browser message`Profile update sucssfully`

Step 8: Varify the XSS on browser, both xss pyalad given `fname` and `lname` is vulnerable.


## Mitigation/recommendations

- https://portswigger.net/web-security/cross-site-scripting
- https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html


