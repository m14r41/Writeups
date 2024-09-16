## Vulnerability Description

HTML Injection vulnerability was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers to execute arbitrary HTML code via the `searchkey` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin/search-result.php <br>- **Affected Parameter:** searchkey<br>- **Method:** POST                                                                           |


## Steps to Reproduce:

> How to produce vulnerability

Step 1: Click on Adming login

Step 2: Prove Admin credential to login

Step 3: In search bar, provide values `<h1>HTML Injection </h1>` and enable burpsuite to confirm the parameter.

Step 4: Just notice that payload is `searchkey` parameter, Now forward the request

Step 5: As request is forwarded notice in the browser, HTML Payload is executed.


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html
- https://stackoverflow.com/questions/20855482/preventing-html-and-script-injections-in-javascript


