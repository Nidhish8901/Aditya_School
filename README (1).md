# Aditya School Website Project

This repository contains the complete code for the Aditya School website, a comprehensive platform featuring a public-facing website, a separate admissions form, and a full-featured admin panel for content management.

## Live Demo

- [Visit School Website](https://aditya-school.netlify.app)
- [Access Admin Panel](https://aditya-school.netlify.app/admin.html)

## File Structure

```
aditya-school/
├── index.html         # Multi-page dynamic website
├── admissions.html    # Admission form with validations
└── admin.html         # Admin panel for content management
```

## Features

### Public Website (index.html)

- Multi-page simulation using dynamic content loading.
- Photo and video gallery integration from Supabase Storage.
- Fully responsive design for desktop, tablet, and mobile.
- Interactive UI including lightbox and mobile navigation.

### Admissions Form (admissions.html)

- Full-featured student application form.
- Client-side validation for Aadhaar, mobile number, and pincode.
- Secure submission to Supabase database.

### Admin Panel (admin.html)

- Email/password-based Supabase authentication.
- Admission data table with Excel export using SheetJS.
- Upload, view, and delete images in the photo gallery.
- Add, view, and delete YouTube video links.

## Tech Stack

### Frontend

- HTML5
- Tailwind CSS
- JavaScript

### Backend (Supabase)

- Authentication
- PostgreSQL Database
- Storage Buckets

### Libraries Used

- [Font Awesome](https://fontawesome.com/) - Icon library
- [SheetJS](https://sheetjs.com/) - Excel export functionality

## Setup Instructions

### 1. Create a Supabase Project

- Go to [Supabase](https://supabase.com) and create a new project.
- Save your Supabase project URL and anon public key.

### 2. Configure HTML Files

In `index.html`, `admissions.html`, and `admin.html`, scroll to the bottom and update the following:

```
const SUPABASE_URL = "your-project-url";
const SUPABASE_ANON_KEY = "your-anon-key";
```

### 3. Supabase Setup

#### Tables

Create the following tables with all columns as text unless specified:

- admissions: full_name, admission_class, dob, gender, father_name, mother_name, guardian_name, aadhaar_number, aadhaar_name, address, mobile_number, neighbour_number, email, pincode, mother_tongue, social_category, sub_caste, religion, nationality, bpl_beneficiary, ews_status, cwsn_status, cwsn_category, disability_percentage, pen_number, blood_group, height_cm, weight_kg, previous_school_record

- videos: title, video_id (rename from youtube_id)

#### Buckets

Create two public buckets:

- gallery-photos
- ui-assets

Set Storage Policies:

- Public: SELECT (read)
- Authenticated: INSERT, UPDATE, DELETE

#### Admin User

Go to Authentication > Add User to create a login for admin.html.

### 4. Deployment

Upload the three HTML files to a hosting platform like [Netlify](https://www.netlify.com/) or [Vercel](https://vercel.com/).