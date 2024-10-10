## Vulnerability Description

HTML Injection vulnerability was found in the `/search-result.php` page of the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers to execute arbitrary HTML code via the `searchkey` parameter in a POST HTTP request.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**          | - **Version:** -  V 3.2 <br>- **Affected Code File:** /admin/search-result.php <br>- **Affected Parameter:** searchkey<br>- **Method:** POST                                                                           |


## Steps to Reproduce:

**Step 1:** Click on Admin login

![image](https://github.com/user-attachments/assets/cb9d4284-a525-4f11-af9b-ce36d6d42fda)

**Step 2:** Prove Admin credential to login

![image](https://github.com/user-attachments/assets/14f8d059-e540-49d9-9c9c-0cb198ade472)

**Step 3:** In search bar, provide values `<h1>HTML Injection </h1>` and enable burpsuite to confirm the parameter.

![image](https://github.com/user-attachments/assets/2bb4de79-bbea-4135-b223-e1f339106541)

**Step 4:** Just notice that the payload is `searchkey` parameter, Now forward the request

![image](https://github.com/user-attachments/assets/85bae8be-244a-43aa-867a-93e02112fba6)

**Step 5:** As the request is forwarded notice in the browser, HTML Payload is executed.

![image](https://github.com/user-attachments/assets/ee44be97-a9da-4b8e-a3bd-2170cf03b97d)


## Mitigation/recommendations

- https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html
- https://stackoverflow.com/questions/20855482/preventing-html-and-script-injections-in-javascript


