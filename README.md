# Smart Online Learning Platform

A full-stack online learning platform that allows users to register, log in, and access courses through a modern web interface. The system is built using React.js for the frontend and Django REST Framework for the backend, with secure JWT-based authentication.

---

## 🚀 Features

- User registration and login using JWT authentication
- Course listing and lesson management
- REST API-based backend architecture
- React frontend integrated with backend APIs
- Clean and scalable project structure

---

## 🛠️ Tech Stack

### Frontend
- React.js
- HTML, CSS, JavaScript
- Axios

### Backend
- Django
- Django REST Framework
- JWT Authentication (SimpleJWT)

### Database
- SQLite (can be upgraded to PostgreSQL / MySQL)

---

## 📂 Project Structure

```
online-learning-platform/
│
├── backend/
│   ├── backend/
│   ├── users/
│   ├── courses/
│   └── manage.py
│
├── frontend/
│   ├── src/
│   │   ├── pages/
│   │   ├── api/
│   │   └── components/
│
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/punithkv/smart-online-learning-platform.git
cd smart-online-learning-platform
```

---

### 2️⃣ Backend Setup
```bash
cd backend
pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

Backend runs at:
```
http://127.0.0.1:8000/
```

---

### 3️⃣ Frontend Setup
```bash
cd frontend
npm install
npm start
```

Frontend runs at:
```
http://localhost:3000/
```

---

## 🔐 Authentication

- JWT-based authentication using SimpleJWT
- Secure login and registration APIs
- Token-based access for protected resources

---

## 🌱 Future Enhancements

- Course enrollment and progress tracking
- Admin dashboard for instructors
- Payment gateway integration
- AI-based course recommendation system
- Certificate generation for completed courses

---

## 📌 Resume Description

**Smart Online Learning Platform (Full-Stack Project)**  
Developed a full-stack online learning platform using React.js and Django REST Framework. Implemented JWT-based authentication, REST APIs for course and lesson management, and a scalable architecture designed for future AI-driven enhancements.

---

## 👨‍💻 Author

**Punith K V**  
- GitHub: https://github.com/punithkv  
- Email: punithkv54@gmail.com
