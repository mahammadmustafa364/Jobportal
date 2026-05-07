# Job Portal - Django

A full-stack web application built with Django that connects job seekers with companies. It supports three user roles: **Admin**, **Company**, and **Applicant**.

---

## Features

### Applicant
- Register and log in
- Browse and search all job listings
- View job details (salary, location, skills, experience required)
- Apply for jobs with resume upload
- Edit profile (name, email, phone, gender, profile picture)

### Company
- Register and log in (requires admin approval)
- Post, edit, and manage job listings
- View all applicants who applied for their jobs
- Edit company profile and logo

### Admin
- Approve or reject company registrations
- View all companies (pending, accepted, rejected)
- View and delete applicants
- Manage all platform data via Django admin panel (`/admin/`)

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3, Django |
| Database | SQLite3 |
| Frontend | HTML, CSS, Bootstrap 4 |
| Auth | Django built-in authentication |
| File storage | Local media files |

---

## Project Structure

```
job-portal-django/
│
├── JobPortal/               # Project config
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── jobs/                    # Main app
│   ├── models.py            # Applicant, Company, Job, Application
│   ├── views.py             # All view functions
│   ├── urls.py              # URL routing
│   ├── admin.py             # Admin registrations
│   ├── templates/           # All HTML templates
│   ├── static/              # Static files
│   └── migrations/          # Database migrations
│
├── manage.py
└── requirements.txt
```

---

## Getting Started

### Prerequisites

- Python 3.8 or higher
- pip

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/your-username/job-portal-django.git
cd job-portal-django
```

**2. Create and activate a virtual environment**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Mac / Linux
source venv/bin/activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Apply migrations**
```bash
python manage.py makemigrations
python manage.py migrate
```

**5. Create a superuser (admin account)**
```bash
python manage.py createsuperuser
```

**6. Run the development server**
```bash
python manage.py runserver
```

Open your browser and visit: **http://127.0.0.1:8000**

---

## URL Reference

| URL | Description |
|---|---|
| `/` | Home page |
| `/signup/` | Applicant registration |
| `/user_login/` | Applicant login |
| `/user_homepage/` | Applicant dashboard |
| `/all_jobs/` | Browse all jobs |
| `/job_detail/<id>/` | Job detail page |
| `/job_apply/<id>/` | Apply for a job |
| `/company_signup/` | Company registration |
| `/company_login/` | Company login |
| `/company_homepage/` | Company dashboard |
| `/add_job/` | Post a new job |
| `/job_list/` | Company's posted jobs |
| `/admin_login/` | Admin login |
| `/all_companies/` | Admin: view all companies |
| `/pending_companies/` | Admin: pending approvals |
| `/admin/` | Django admin panel |

---

## Database Models

- **Applicant** — linked to Django User, stores phone, gender, profile image
- **Company** — linked to Django User, stores company name, status (pending/accepted/rejected)
- **Job** — belongs to a Company, stores title, salary, dates, skills, location
- **Application** — links an Applicant to a Job, stores resume and apply date

---

## Screenshots

> Add screenshots of your app here after running it locally.

---

## Known Issues

- No email verification on signup
- Resume field accepts image files only (should accept PDF/DOC)
- No pagination on job listings

---

## Future Improvements

- Email notifications for application status
- Resume PDF upload support
- Search and filter jobs by location, salary, skills
- Pagination for job listings
- Password reset functionality

---

## Author

**Mahammad Mustafa Ravikala**

---

## License

This project is for educational purposes.
