# 🏨 Django Hotel Management System

A full-featured hotel management system built using Django, supporting multiple user roles and permissions.

---

## 📁 Project Structure

- **Documents/**: Includes Requirement Analysis, System Design, Object Design, Class Diagram, ER Diagram, and Mockups.
- **Screenshots/**: Contains screenshots of the web application interface.

---

## 👥 User Roles

This system includes **five distinct user types**, each with its own permissions and functionality:

- **Admin**
- **Manager**
- **Receptionist**
- **Staff**
- **Guest**

---

## ⚙️ Setup Instructions

> ⚠️ _Python 3 must already be installed._

### 1. Install Required Packages

```bash
pip install Django==3.1.4
pip install django-phonenumber-field[phonenumbers]
2. Create User Groups and Admin Account
Navigate to the project’s HMS directory and start the shell:

bash
Copy
Edit
cd Django---Hotel-Management-System/HMS
python3 manage.py shell
Then run the following commands one by one in the Python shell:

python
Copy
Edit
from django.contrib.auth.models import Group, User
from accounts.models import Employee

Group.objects.create(name='admin')
Group.objects.create(name='manager')
Group.objects.create(name='receptionist')
Group.objects.create(name='staff')
Group.objects.create(name='guest')

user = User.objects.create_user('admin', password='admin123')
group = Group.objects.get(name="admin")
user.groups.add(group)

admin = Employee(user=user, salary=0)
admin.save()
3. Migrate the Database & Run the Server
bash
Copy
Edit
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py runserver
Visit http://127.0.0.1:8000/ to access the application.

🔐 Login & Role Management
By default, only Guest users can register.

To add employees (Manager, Receptionist, Staff), log in as Admin:

text
Copy
Edit
Username: admin
Password: admin123
Go to the Employee page → Click "Add New Employee" → Fill the form.

💳 Payment Page Disclaimer
The payment screen is non-functional — no real transactions are processed.

It's included to simulate a real booking flow.

A verification code is sent to the user's email after this step.

📧 Email Configuration
Open HMS/settings.py

Scroll to the email section and uncomment the settings

Update with your email credentials to enable email features (e.g., confirmation emails)

📷 Screenshots
Find UI previews inside the Screenshots/ folder.

👤 Author
Harsh Panchal
Bachelor of Computer Science, Carleton University
LinkedIn
GitHub
