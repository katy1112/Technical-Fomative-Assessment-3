# Technical-Fomative-Assessment-3
Mangat, Anakatrina Technical Fomative Assessment 3


# TFA 3 — Forms, Validation, and File Upload

A CodeIgniter 4 web application that demonstrates CRUD operations, form validation, edit/update workflows, and image upload handling for customers and users.

## Project Overview

This project is developed using **CodeIgniter 4**, PHP, MySQL, HTML, and CSS.

The system allows users to:

- Add new customer records
- Validate customer information before saving
- Edit and update customer records
- Add new user records
- Validate username uniqueness and required fields
- Edit and update user records
- Upload user avatar images
- Validate uploaded image type and file size
- Create a display-ready 300x300 avatar thumbnail
- Store only the generated filename in the database
- Display uploaded avatars or a placeholder when no avatar exists

## Technologies Used

- **PHP**
- **CodeIgniter 4**
- **MySQL**
- **HTML5**
- **CSS3**
- **XAMPP**
- **Apache**
- **MySQLi**
- **GD Library** for image processing

## System Features

### Customer Management

The customer module supports:

- Viewing all customers
- Adding a new customer
- Required full name validation
- Required and valid email validation
- Optional phone number
- Editing existing customer records
- Updating customer information

### User Management

The user module supports:

- Viewing all users
- Adding a new user
- Required username validation
- Unique username validation
- Required full name validation
- Valid email validation
- Editing existing user records
- Updating user information

### Avatar Upload

The user edit page supports avatar uploads.

Upload requirements:

- JPG/JPEG or PNG only
- Maximum file size: 2 MB
- Uploaded images are validated before processing
- A unique filename is generated
- The image is processed into a 300x300 display-ready thumbnail
- The prepared image is stored in:

```text
public/uploads/avatars/

Validation

The application uses CodeIgniter 4 validation rules.

Customer Validation
full_name → required
email → required | valid_email
phone → optional
User Validation
username → required | unique
full_name → required
email → required | valid_email
Avatar Validation
uploaded
image file
JPG/JPEG or PNG
maximum 2 MB

Validation errors are displayed on the form and previously entered values are retained using CodeIgniter's old() helper.

Project Structure

Important project folders and files:

tfa3/
│
├── app/
│   ├── Controllers/
│   │   ├── Customers.php
│   │   ├── Users.php
│   │   └── Pages.php
│   │
│   ├── Models/
│   │   ├── CustomerModel.php
│   │   └── UserModel.php
│   │
│   ├── Views/
│   │   ├── customers/
│   │   │   ├── index.php
│   │   │   ├── new.php
│   │   │   └── edit.php
│   │   │
│   │   ├── users/
│   │   │   ├── index.php
│   │   │   ├── new.php
│   │   │   └── edit.php
│   │   │
│   │   └── pages/
│   │
│   └── Config/
│       └── Routes.php
│
├── public/
│   ├── css/
│   │   └── style.css
│   │
│   └── uploads/
│       └── avatars/
│
├── writable/
│
├── .env
└── README.md
Routes
Customers
Method	Route	Purpose
GET	/customers	Display customer list
GET	/customers/new	Display add customer form
POST	/customers/create	Save new customer
GET	/customers/edit/{id}	Display edit customer form
POST	/customers/update/{id}	Update customer
Users
Method	Route	Purpose
GET	/users	Display user list
GET	/users/new	Display add user form
POST	/users/create	Save new user
GET	/users/edit/{id}	Display edit user form
POST	/users/update/{id}	Update user
Database

Database name:

pos_system_tfa3

The database contains two main tables:

customers
id
full_name
email
phone
created_at
users
id
username
full_name
email
created_at
avatar

The avatar column stores only the prepared image filename.

Example:

avatar_abc123.jpg

The actual image is stored inside:

public/uploads/avatars/
Installation and Setup
Requirements

Make sure the following are installed:

XAMPP
PHP 8.2 or higher
Apache
MySQL
CodeIgniter 4
GD PHP extension
Step 1 — Clone the Repository

Clone the project into the XAMPP htdocs folder:

C:\xampp\htdocs\tfa3
Step 2 — Create the Database

Open phpMyAdmin:

http://localhost/phpmyadmin/

Create a database named:

pos_system_tfa3

Import the provided SQL database export:

pos_system_tfa3.sql
Step 3 — Configure the Environment

Update the .env file:

database.default.hostname = localhost
database.default.database = pos_system_tfa3
database.default.username = root
database.default.password =
database.default.DBDriver = MySQLi
database.default.port = 3306

app.baseURL = 'http://localhost/tfa3/'
Step 4 — Enable GD

Make sure the PHP GD extension is enabled in XAMPP.

In php.ini, make sure the GD extension is enabled, then restart Apache.

GD is required for processing uploaded avatar images.

Step 5 — Create the Upload Folder

Make sure this folder exists:

C:\xampp\htdocs\tfa3\public\uploads\avatars
Step 6 — Run the Application

Start:

Apache
MySQL

Then open:

http://localhost/tfa3/
Testing

The following functionality was tested:

Customer
 Add customer
 Required full name validation
 Required email validation
 Valid email format validation
 Form redisplays validation errors
 Previous form values are retained
 Edit customer
 Update customer
User
 Add user
 Required username validation
 Unique username validation
 Required full name validation
 Valid email validation
 Edit user
 Update user
Avatar Upload
 Upload JPG/JPEG image
 Upload PNG image
 Reject unsupported file types
 Reject files larger than 2 MB
 Generate unique filename
 Resize/crop image to 300x300
 Store prepared image in public uploads
 Store only filename in database
 Display uploaded avatar
 Display placeholder when no avatar exists
 Replace previous avatar when a new avatar is uploaded
Security and Validation Practices

The project uses several practices to improve application security and reliability:

Server-side validation using CodeIgniter 4
CSRF protection using csrf_field()
Escaped output using esc()
Unique generated filenames for uploaded images
File type and MIME validation
File size validation
Database allowedFields protection
Uploaded images are processed before being displayed
Only the filename is stored in the database
Author

Katrina Mangat

FEU Diliman
Web and Mobile Design

Academic Project

This project was created as part of the IT0049 Web System Technologies technical formative assessment.

TFA 3 — Making It Editable: Forms, Validation, and File Upload


### 📌 What to do now

Inside:

```text
C:\xampp\htdocs\tfa3
