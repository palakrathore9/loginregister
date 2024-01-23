the provided code represents a Django-based web application for user authentication and profile management. It includes features such as user registration, login, logout, profile display, and profile updates. The project utilizes Django's built-in authentication views, forms, and models to create a secure and functional user authentication system.

video demonstration-https://drive.google.com/file/d/1urLBajjbh60dIHWnb7UEAf7BgA4ZYlJY/view?usp=sharing

section-1

1. Email Verification:

Custom User Model:
To begin with, we create a custom user model in Django with an additional field to track the email verification status. This involves extending the AbstractUser class and adding a boolean field, say is_email_verified.

Registration View:
Next, we create a registration view that manages user creation. In this view, we set the is_active and is_email_verified fields to False for newly registered users. This ensures that users need to verify their email before gaining full access to the application.

Email Sending:
Upon user registration, we send a verification email to the user's provided email address. This email contains a unique tokenized link that the user needs to click for email verification.

Activation View:
The activation view handles the verification link. It verifies the token and updates the user's is_email_verified field to mark the email as verified.

2. Password Update:

Password Reset View:
Django provides a built-in view, PasswordResetView, which sends a password reset email to users. We utilize this view to initiate the password reset process.

Email Sending for Password Reset:
Configuring email settings and templates, we ensure that the password reset email contains a secure link with a unique token. This link allows users to reset their password.

Password Reset Confirmation View:
We create a custom view to handle the password reset link. This view verifies the token and provides users with the ability to update their password securely.

Password Update View:
Finally, we implement a view, possibly through a form or a link with a secure token, that allows users to update their passwords.

to run: 

        cd backend

        pip install -r requirements.txt
        
        python manage.py runserver
        
