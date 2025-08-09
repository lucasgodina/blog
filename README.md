# Django Blog Application

A complete blog system built with Django 5, featuring modern functionalities like comments, advanced search, tagging, RSS feeds, and much more.


## 🚀 Features

### ✨ Main Features

- **📝 Post Management**
  - Create, edit, and delete blog posts
  - Draft and publish system
  - SEO-friendly URLs with dates (`/year/month/day/slug/`)
  - Similar posts based on shared tags

- **🏷️ Tagging System**
  - Customizable tags for each post
  - Filter posts by tags
  - Related posts visualization

- **💬 Comment System**
  - Public comments on each post
  - Comment moderation (active/inactive)
  - Comment form with validation

- **📧 Share Posts by Email**
  - Email post sharing functionality
  - Customizable form with optional comments
  - Gmail SMTP integration

- **🔍 Advanced Search**
  - Similarity search using PostgreSQL Trigrams
  - Results ordered by relevance
  - Search in post titles

- **📱 Navigation and UX**
  - Advanced pagination (3 posts per page)
  - Latest posts list
  - Responsive interface with custom CSS

- **🌐 SEO and Feeds**
  - Automatic RSS feed for recent posts
  - XML sitemap for search engines
  - SEO-optimized URLs

- **⚡ Technical Features**
  - Class-based and function-based views
  - Custom managers for published posts
  - Optimized database indexes
  - Full PostgreSQL support

## 🛠️ Technologies Used

- **Backend**: Django 5.0.14
- **Database**: PostgreSQL (with trigram search support)
- **Frontend**: HTML5, CSS3, Django Templates
- **Tags**: Django-taggit
- **Email**: Gmail SMTP
- **Others**: Python-decouple for configuration

## 📋 Prerequisites

- Python 3.8+
- PostgreSQL
- Git

## 🚀 Local Installation and Setup

### 1. Clone the Repository
```bash
git clone https://github.com/lucasgodina/blog.git
cd blog
```

### 2. Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Linux/Mac
# venv\Scripts\activate   # On Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables
```bash
# Copy the example file and edit it
cp .env.example .env
# Edit .env with your actual values
```
**Note:** For Gmail, you need to:
1. Enable 2-factor authentication
2. Generate an App Password (not your regular Gmail password)

### 5. Setup PostgreSQL Database

**Option 1: Local PostgreSQL**
```sql
CREATE DATABASE blog_db;
CREATE USER blog_user WITH PASSWORD 'your_password';
GRANT ALL PRIVILEGES ON DATABASE blog_db TO blog_user;
```

**Option 2: Using Docker**
```bash
docker-compose up -d postgres
```

### 6. Run Migrations
```bash
python manage.py migrate
```

### 7. Create Superuser
```bash
python manage.py createsuperuser
```

### 8. Create PostgreSQL Extension (for search)
Connect to the database and run:
```sql
CREATE EXTENSION pg_trgm;
```

### 9. Run Development Server
```bash
python manage.py runserver
```

The blog will be available at: `http://127.0.0.1:8000/blog/`

## 📁 Project Structure

```
blog/
├── blog/                   # Main application
│   ├── migrations/         # Database migrations
│   ├── static/css/         # CSS files
│   ├── templates/          # HTML templates
│   ├── templatetags/       # Custom template tags
│   ├── models.py          # Models (Post, Comment)
│   ├── views.py           # Blog views
│   ├── forms.py           # Forms
│   ├── feeds.py           # RSS Feeds
│   ├── sitemaps.py        # XML Sitemap
│   └── urls.py            # App URLs
├── django_project/         # Project configuration
│   ├── settings.py        # Main settings
│   └── urls.py            # Main URLs
├── manage.py              # Django command
└── db.sqlite3            # Database (development)
```

## 🎯 System Usage

### Admin Panel
- Access `/admin/` with superuser credentials
- Manage posts, comments, and users
- Moderate comments and configure tags

### Public Features
- **Post list**: `/blog/`
- **Post detail**: `/blog/year/month/day/slug/`
- **Posts by tag**: `/blog/tag/tag-name/`
- **Search**: `/blog/search/`
- **RSS Feed**: `/blog/feed/`
- **Sitemap**: `/sitemap.xml`

## 📖 Credits

**Book**: "Django 5 by Example"  
**Author**: Antonio Melé  
**Publisher**: Packt Publishing  

This is the **first project** from the book, designed to teach Django fundamentals through a practical and complete example.

## 📄 License

This project is for educational purposes based on the material from the mentioned book.

---

⭐ If this project was useful to you, don't forget to star the repository and check out the complete book for more advanced Django projects.