# Secure University Student Portal (AWS Cognito)

A university is building a centralized student portal that allows thousands of students to log in and access grades, assignments, and learning materials. Professors also log in but require elevated access to manage and upload course records. To maintain privacy and compliance, the system must strictly enforce:

- Multi-Factor Authentication (MFA)
- Strong password policies
- Role-based access control (RBAC)
- This project simulates how a Cloud Security Engineer secures user identities and manages controlled access across different user roles using AWS-native identity services.

## Solution
Designing a secure identity management system using Amazon Cognito, which will handle everything from authentication to access control.

![Alt text](/cognito.jpg)

- User (Student or Professor) accesses the university portal via the frontend app.
- The frontend redirects users to Cognito's hosted login domain.
- Cognito User Pool handles sign-up, login, MFA, and password validation.
- After successful authentication, Cognito App Client issues ID and Access Tokens.
- IAM roles are assigned based on user groups (Student or Professor).
- Users are redirected back to the portal with a valid session.
- CloudWatch monitors login attempts, MFA usage, and potential authentication errors.




---


- ## Amazon Cognito provides a fully managed identity service for authentication and authorization. I've created a User Pool for both Students and Professors, enforce strong password policies, enable MFA, and configure groups for role-based access.
<img width="1908" height="333" alt="Screenshot 2026-01-06 211112" src="https://github.com/user-attachments/assets/cfa2e9b9-bab5-4b7d-8671-68e440f140ea" />
<img width="1900" height="634" alt="Screenshot 2026-01-06 211340" src="https://github.com/user-attachments/assets/bd9b0c14-3c69-40bd-b8b3-6dbc42c73468" />
<img width="1900" height="437" alt="Screenshot 2026-01-06 211243" src="https://github.com/user-attachments/assets/0ec1eda8-31d7-4c7f-9a12-9d8713502eb9" />
<img width="1903" height="387" alt="Screenshot 2026-01-06 211441" src="https://github.com/user-attachments/assets/21a0c607-66b9-471d-81be-878142d8a4dc" />

---

- ## The App Client represents your application (University Portal). It handles authentication requests from the User Pool.

- ## The Cognito-managed domain provides hosted login and logout endpoints for users.
<img width="1912" height="458" alt="Screenshot 2026-01-06 211143" src="https://github.com/user-attachments/assets/eabb7acc-7ea7-47f6-a447-1ca6eb0d25f5" />

---

- ## Now that the User Pool, App Client, and Domain are ready, I've created actual users for the portal. I've created accounts for Students and Professors and placed them into their respective Cognito Groups.

- ## This step simulates how users will be onboarded before integrating with the frontend.
<img width="1896" height="386" alt="Screenshot 2026-01-06 211414" src="https://github.com/user-attachments/assets/de8a2b43-cfbf-4d3f-8d2b-da9f23d43137" />
<img width="1903" height="387" alt="Screenshot 2026-01-06 211441" src="https://github.com/user-attachments/assets/d1de4e59-eccc-4d6d-901d-3d671044e3d3" />


---

- ## Now that I have a Cognito User Pool and App Client configured, I then built the University Portal frontend. I started by creating a simple React app and then integrated Cognito authentication using the official OIDC Quick Setup approach.
<img width="1900" height="411" alt="Screenshot 2026-01-06 211205" src="https://github.com/user-attachments/assets/cae7240a-b00e-46bd-8189-a187aa8c174a" />
<img width="1687" height="293" alt="Screenshot 2026-01-06 211533" src="https://github.com/user-attachments/assets/bdda0d02-4523-47fc-8916-5ee385eeb001" />
<img width="1430" height="756" alt="Screenshot 2026-01-06 052904" src="https://github.com/user-attachments/assets/54fca0dc-4f33-4248-b56e-098b47d13b6a" />
<img width="1677" height="706" alt="Screenshot 2026-01-06 211736" src="https://github.com/user-attachments/assets/928dd055-dfac-4780-af3a-3ac76bff1bfa" />

---

- ## Redirected to the Cognito-hosted login page
Log in with a Student or Professor account
<img width="1890" height="918" alt="Screenshot 2026-01-06 205851" src="https://github.com/user-attachments/assets/74f38f8e-a659-4466-bf5b-be9a68161f04" />

---

- ## Cognito will prompt to set a new password and configure MFA.
<img width="1856" height="904" alt="Screenshot 2026-01-06 210029" src="https://github.com/user-attachments/assets/fb1870d5-7cc1-489e-911c-38ffe8e80da4" />
<img width="1724" height="859" alt="Screenshot 2026-01-06 210123" src="https://github.com/user-attachments/assets/a4ce38da-a45f-485c-8d78-dfc11c24756b" />
<img width="1738" height="901" alt="Screenshot 2026-01-06 210644" src="https://github.com/user-attachments/assets/145612b2-fa0c-48db-b314-8e4d6a740b97" />

- Once MFA is set up, Cognito redirects back with valid JWT tokens

- The University Portal frontend is now connected to Cognito via standards-based OIDC. 

- Students and professors can sign in and manage sessions securely.

---

## AWS Services Used
- Amazon Cognito User Pool – User authentication and group management
- Amazon Cognito App Client – Secure frontend integration
- AWS IAM – Permissions and role mapping for different user groups
- Frontend App (React + OIDC) – University portal interface

---


## Skills Gained
By completing this project, I now understand how to:

- Set up secure authentication flows using Cognito
- Implement role-based access control for different user groups
- Work with MFA and JWT tokens, foundational for cloud security
- Protect APIs with Cognito Authorizers

---


## Conclusion
This project demonstrates real-world cloud security practices, showing how authentication, authorization, and API protection work together to safeguard sensitive data. As a Cloud Security Engineer, these are core skills for building secure cloud applications.






