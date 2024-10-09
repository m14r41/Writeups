## Vulnerability Description

Reflected Cross-Site Scripting (XSS) vulnerability was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers to execute arbitrary scripts via the `searchkey` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin/search-result.php <br>- **Affected Parameter:** searchkey<br>- **Method:** POST                                                                           |


## Steps to Reproduce:

**Step 1**: Click on Adming login
![image](https://github.com/user-attachments/assets/a03c927d-6531-4d58-ba04-1dc4485f20ff)

**Step 2:** Provide Admin credential to login
![image](https://github.com/user-attachments/assets/0acd5300-e785-4b88-8dcf-5a64e8b571a4)


**Step 3:** In search bar, provide values `<script>alert(1)</script>` and enable burpsuite to confirm the parameter.
![image](https://github.com/user-attachments/assets/7477b21c-3cdc-42e1-a8e8-60c08e958d79)

**Step 4:** Just notice that payload is `searchkey` parameter, Now forward the request

![image](https://github.com/user-attachments/assets/06d5c1f7-0045-4c4c-b48c-4f80c050abe7)

**Step 5:** As request is forwarded notice in the browser, Payload is executed with popup.

![image](https://github.com/user-attachments/assets/f6747319-27f7-41db-b4a7-a186cb9cfaec)


## Mitigation/recommendations

- https://portswigger.net/web-security/cross-site-scripting
- https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html


