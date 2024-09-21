## Vulnerability Description

Stored Cross-Site Scripting (XSS) vulnerability by CSRF was found in the `profile.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers to execute arbitrary scripts via the CSRF attack in /http://localhost/loginsystem/profile.php URL.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:**/profile.php <br>- **Affected Parameter:** fname, lname<br>- **Method:** POST                                                                           |


## Steps to Reproduce:

**Step 1**: Login into application as normal user.
![Screenshot_1](https://github.com/user-attachments/assets/3b8a01fd-44b2-4083-8d96-7a059adf975c)

**Step 2**: Navigate to Profile page.
![Screenshot_2](https://github.com/user-attachments/assets/5233f55f-11a6-4782-9423-10b2b1c4cdb8)

**Step 3**: Carft the csrf poc and Copy.

![Screenshot_3](https://github.com/user-attachments/assets/3fe387df-bd7e-40a7-bd7d-d67fe704adfd)

**Step 4:** Visite webhook.site click -> edit the content and paste copied csrf html
![Screenshot_4](https://github.com/user-attachments/assets/7b035b5b-74f3-48ea-8b25-3c5580e3a06c)

**Step 5**: Open the url in logged in browser
![Screenshot_5](https://github.com/user-attachments/assets/c131a93a-036d-46fb-aaf4-49a94bcd9d03)
**
Step 6**: Observe the that csrf is attack is sucessfull and data stored on server.
![Screenshot_6](https://github.com/user-attachments/assets/67855a92-7863-4a9e-b1f9-11ea77da477d)
![Screenshot_8](https://github.com/user-attachments/assets/2536c358-9888-432f-8924-15a7316b4c20)


**step 7**: Observer the browser message`Profile update sucssfully`
![Screenshot_7](https://github.com/user-attachments/assets/42c3385c-00fd-4761-96e3-f6d11fafad3f)

**Step 8**: Varify the XSS on browser, both xss pyalad given `fname` and `lname` is vulnerable.
![Screenshot_9](https://github.com/user-attachments/assets/2b42e5f9-6c79-4e9d-b774-1aefa81b55df)
![Screenshot_10](https://github.com/user-attachments/assets/b2eff8f6-785e-466c-ae12-4d385a5c1f7d)



## Mitigation/recommendations

- https://portswigger.net/web-security/cross-site-scripting
- https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html


