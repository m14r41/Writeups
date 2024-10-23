## Vulnerability Description

Directory listing is found in the PHPGurukul User Registration & Login and User Management System V3.2. This vulnerability allows remote attackers attacker to access sensitive file and directories via http://localhost/loginsystem/assets URL.


| **Field**                        | **Details**                                                                                                                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                      |
| **Affected Product Name**        | User Registration & Login and User Management System With admin panel                                                                                                                      |
| **Product Official Website URL** | [https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/](https://phpgurukul.com/user-registration-login-and-user-management-system-with-admin-panel/) |
| **Affected Components**   <br>       | - **Version:** -  V 3.2 <br> - **Affected Directory:** /assets <br> - **Method:** POST                                                                           |


## Steps to Reproduce:

Step 1: Access http://localhost/loginsystem/assets and notice the directory listing.
![image](https://github.com/user-attachments/assets/d4202db7-a52a-4551-b154-18387e6fd262)


Recommendation:

- https://portswigger.net/kb/issues/00600100_directory-listing
- https://cwe.mitre.org/data/definitions/548.html
