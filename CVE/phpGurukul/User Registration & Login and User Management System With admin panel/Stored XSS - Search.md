## Vulnerability Description

Reflected Cross-Site Scripting (XSS) vulnerability was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers to execute arbitrary scripts via the `searchkey` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin/search-result.php <br>- **Affected Parameter:** searchkey<br>- **Method:** POST                                                                           |


## Steps to Reproduce:

> How to produce vulnerability

Step 1: Click on Adming login

Step 2: Provide Admin credential to login

Step 3: In search bar, provide values `<script>alert(1)</script>` and enable burpsuite to confirm the parameter.

Step 4: Just notice that payload is `searchkey` parameter, Now forward the request

Step 5: As request is forwarded notice in the browser, Payload is executed with popup.


## Mitigation/recommendations

- https://portswigger.net/web-security/cross-site-scripting
- https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html


