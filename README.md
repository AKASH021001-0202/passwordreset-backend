﻿# Assign Mentor

This project provides APIs to assign mentors to students and manage mentor-student relationships.

## Getting Started

To get started with the project, follow these steps:



1. Clone the repository:


git clone https://github.com/AKASH021001-0202/passwordreset-backend


2. Install dependencies:

cd passwordreset-backend
npm install



3. Start the server:

npm start

The server will start running on port 8000 by default. You can change the port by modifying the `PORT` environment variable.


## step-by-Step Process
User Requests Password Reset
       |
       V
Generate Random String, Store in DB
       |
       V
Send Reset Link to User's Email
       |
       V
User Clicks Reset Link (with Token)
       |
       V
Verify Token in Database
       |
  [Token Valid?]
  /           \
Yes            No
 |             |
 V             |
Display       Display
Reset         Error:
Password      Invalid Token
Form          Message
 |             |
 V             |
User Submits   |
New Password  |
Form           |
 |             |
 V             V
Update         Redirect /
Password       Display Error
in DB,        Message:
Clear Token    Token Expired
       |
       V
Password Reset Successful


1. **User Request:**
   - The user enters their email on the forget password page.
   - The request is sent to the backend.

2. **Backend Verification:**
   - The backend checks if the user exists in the database.
   - If the user does not exist, an error message is sent back to the user.
   - If the user exists, a random string is generated.

3. **Email Sending:**
   - The random string is sent to the user via email as part of a link.
   - The random string is stored in the database for later verification.

4. **User Clicks Link:**
   - When the user clicks the link in the email, they are directed to the reset password page with the random string as a parameter.

5. **Backend Verification:**
   - The backend verifies the random string from the URL.
   - If the string matches, the user is shown the password reset form.
   - If the string does not match, an error message is sent back to the user.

6. **Password Reset:**
   - The user submits the new password through the form.
   - The new password is stored in the database.
   - The random string used for verification is cleared from the database.

## Endpoints
