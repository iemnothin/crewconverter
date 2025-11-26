# Crew XLSX Converter – Laravel & React Application

A complete web application for **converting, previewing, standardizing, and exporting crew data** from complex XLSX formats into a unified structure.  
Built with **Laravel REST API** (backend) and **ReactJS** (frontend).

## 📌 Overview

Different shipping agencies use inconsistent XLSX templates for crew data.  
This application automatically:

✔ Extracts crew information  
✔ Standardizes the format into a consistent structure  
✔ Adds ship name based on user selection  
✔ Saves converted data to database  
✔ Exports the cleaned result back to XLSX  

This tool helps crewing departments, maritime HR teams, and ship management companies process crew data faster and more accurately.

## 🚀 Features

### 🔄 1. XLSX File Conversion

Converts messy Excel formats containing:

- Seafarers section  
- Personal Data Seafarers  
- Contact information  
- Emergency contact  
- Bank details  
- PKL / Certificate fields  
- Various inconsistent columns  

Into a standardized structure:

| Field | Description |
|-------|-------------|
| Name | Crew full name |
| Rank | Position |
| Place of Birth | City / birthplace |
| Date of Birth | Date (YYYY-MM-DD) |
| NPWP | Tax ID |
| Full Address | Complete home address |
| ID (KTP) | Indonesian national ID |
| Status | Marital status |
| Place on Board | Assigned vessel area |
| Contact | Phone number |

### 👀 2. Live Preview in Browser

After upload, the converted result is displayed directly in the React interface:

- Editable table preview  
- Ensures correctness before saving  

### 🚢 3. Ship Selection Before Submit

User selects the **ship name** from a dropdown.  
All crew records are assigned the selected ship name.

### 💾 4. Save to Database

Converted data is sent to Laravel backend and stored in the `crews` table.

### 📥 5. Export Back to XLSX

Exports final data in clean XLSX format with:

- Row 1: `Ship: [Ship Name]`  
- Columns: Name, Rank, Place of Birth, Date of Birth, NPWP, Full Address, ID (KTP), Status, Place on Board, Contact  

## 🛠 Tech Stack

### Backend
- Laravel 10  
- Maatwebsite/Laravel-Excel  
- PhpSpreadsheet  
- REST API  

### Frontend
- ReactJS  
- Axios  
- File Upload + Blob download  
- Dynamic table preview  

## 📦 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/username/repo-name.git
cd repo-name
```

---

## ⚙️ Backend Setup (Laravel)

### Install dependencies
```bash
composer install
```

### Copy env & configure DB
```bash
cp .env.example .env
```

### Generate key
```bash
php artisan key:generate
```

### Migrate database
```bash
php artisan migrate
```

### Run server
```bash
php artisan serve
```

---

## 💻 Frontend Setup (React)

```bash
cd frontend
npm install
```

Create `.env`:
```
REACT_APP_API_BASE=http://localhost:8000/api
```

Run:
```bash
npm start
```

---

## 📡 API Endpoints

### POST /api/convert  
Upload XLSX → Convert → Return preview  

### POST /api/submit  
Save converted data to database  

### GET /api/download  
Download cleaned XLSX  

### GET /api/ships  
List ships for dropdown  

---

## 📁 Project Structure

```
/backend (Laravel)
  /app
  /routes/api.php
  /app/Http/Controllers/Api/CrewConvertController.php
  /database/migrations

/frontend (React)
  /src/components/CrewConvert.jsx
  App.js
  .env
```

---

## 🖼 Screenshots (Optional)
Add your screenshots here.

---

## 📄 License
MIT License.

---

## 🙌 Author
**Abim**  
Maritime Software Developer
